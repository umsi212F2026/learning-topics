# Designing a workflow

This page is about the choices you make when you design a workflow. It gives the whole layout and then looks closely at two decisions, how to divide a workflow into
steps and who should do each step. Later topics take up the others.

One made-up example runs through the page. A teaching assistant for a programming course grades
about 200 homework submissions each week. Each student's code has to be collected, tested, given
written feedback and a grade, and the grade has to reach the course gradebook. The TA wants a
workflow for this, partly run by programs and partly by an AI agent.

## What people want from a workflow

Start with what the people who rely on the workflow actually care about. These are its **final
goals**. Most workflows answer to some mix of these:

- **Correctness:** the results are right. Every student gets the grade their work earned.
- **Cost:** the work takes little of people's time, and little compute or money.
- **Timeliness:** results arrive quickly, at a minimum before the next assignment is due.
- **Security:** nobody can tamper with it. Students can't change grades.
- **Privacy:** information goes only where it should. One student's code and grade aren't seen
  by another student, or sent somewhere the course didn't agree to.
- **Maintainability:** someone can change the workflow next term without breaking it.
- **Access:** the people who need to use it can.
- **Scale:** it still works when the class size doubles.

You can state a goal positively, as value the workflow produces, or negatively, as value lost
when something goes wrong: a wrong grade, a leaked submission, feedback that arrives after the
next deadline. Use whichever makes the goal easier to think about.

## Design decisions, and their options

Designing a workflow means making a series of **design decisions**. Each has a handful of
**options**:

- how to divide it into steps
- who does each step: a person, an AI agent or a program
- what triggers a run: someone starting it by hand, a schedule, or an event such as a new
  submission arriving
- how state is stored: files, a spreadsheet, a database
- how failures are handled
- what each part is allowed to touch
- where it runs, and who pays for it

This topic covers the first two. The rest come in later topics, one or two at a time.

## Intermediate goals

Final goals are hard to aim at directly. "Make every grade correct" doesn't tell you what to
build. So designers aim at properties that past designers have found reliably help with the final
goals. These are **intermediate goals**. A few you will meet in this course:

- **Steps that can be checked:** a person or a program can confirm that a step's output is right.
- **Inspectable intermediate results:** what each step produced is saved where a person or a
  program can look at it.
- **Steps that are safe to rerun:** running a step twice does no harm.
- **A single source of truth:** each fact is stored in one place, so two copies can't disagree.
- **Least privilege:** each part can touch only what it needs.
- **Failing loudly:** when something goes wrong, someone finds out.

Intermediate goals often serve each other, as well as serving final goals. For example, saving
intermediate results helps make a step checkable.

## Trade-offs

An option rarely advances every goal at once. Having a person read every submission might make
the feedback better, and it costs the TA a whole weekend. Having an agent write the feedback is
fast and cheap, and it means sending student code to the agent's provider. A **trade-off** is
what you see when one option helps some goals and hurts others.

Most of design is arguing about trade-offs, and an argument is only as good as its reasons. "An
agent is cheaper" is true of almost every step, so it doesn't say anything about this step. A
good reason points at something particular to the step: what its input is, what a mistake there
would cost, or what data it handles.

## Design patterns

Some combinations of options turn up again and again, because they work well together. A
**design pattern** is a named set of design choices that are often made together. Three you will
meet in this topic:

- **Checkpoints.** Instead of passing results straight from one step to the next, each step saves
  its output, and the next step reads it from there. Each saved output is a checkpoint. It doesn't
  check anything itself, but it gives a checker, or someone investigating a problem, something to
  look at. Checkpoints are the usual way to get inspectable intermediate results. In the TA's
  workflow, the testing step saves its results to a file and the feedback step reads them from
  there. When a student complains, the TA can open that file and see whether the tests or the
  feedback went wrong.
- **Propose-apply.** An agent decides what should change, and writes that down. A program, which
  behaves the same way every time, makes the change, either when the agent invokes it or after a
  person has approved the proposal.
- **Maker-checker.** When a step is unreliable, a separate step checks its output before anything
  relies on it. The checker is usually a different executor: a person, a program, or another agent
  with different instructions. When the checker is a person, this is often called *human in the
  loop*. In the TA's workflow, step 4 checks step 3.

Named patterns are useful as conversational shorthand. Telling your agent "use the propose-apply
pattern for the gradebook step" says a lot in a few words.

A pattern is not a rule. It became a pattern because it suited many past workflows. It may not
suit yours, so check that the reasons it worked there hold here. You may want only some of its
elements, or a version you've changed to fit.

## Dividing a workflow into steps

Suppose the TA's first design has one step: "an agent grades each submission." It might work.
But when a student complains that their grade is wrong, there is nothing to look at except the
grade. Did the code fail its tests, or did the agent misread the results? Nobody can tell.

Here is a better division, with who does each step:

1. Collect the submissions into a folder. (a program)
2. Run the tests on each one, and save the results. (a program)
3. Draft written feedback and a suggested grade, based on the code and its test results. (an AI agent)
4. Review the drafts and settle each grade. (the TA)
5. Post the grades to the gradebook. (a program)

Two rules of thumb produced those boundaries.

**Put a step boundary wherever the kind of check changes.** The output of the testing step can be
checked mechanically: does every submission have a results file, with a pass or fail for every
test? Written feedback can't be checked that way. A person has to read some of it and ask whether
it is fair and accurate. Or perhaps several agents, each with slightly different instructions,
could read it and assess it. When two parts of the work need different kinds of checks, make them
different steps, so each can get its own check.

**Put a step boundary wherever the executor changes.** The executor is whatever carries out a
step: a program, an agent or a person. Where the work passes from one to another, there is a
handoff, and a handoff is a natural place to stop and look.

More steps are not always better. Every boundary adds something to save, to name and to keep in
sync. A boundary earns its place when it lets you check something you otherwise couldn't, or lets
you give different parts of the work to different executors.

## Who does each step

Each step can be done by a person, an AI agent or a program. None is best everywhere.

A program gives the same answer every time and costs almost nothing to run. And because it does
only what its code says, you can find out exactly where it sends information. But a program can't
use judgment.

An agent can use judgment on messy input. But it can be wrong in ways that look right and can be
more expensive to run than a program. And if the agent runs on cloud providers like OpenAI or
Anthropic or Google, information can leak: transcripts of the interaction may be kept by the
provider, used for training under some terms of service, or exposed in a data breach.

A person may have ultimate accountability for any problems that occur, and thus be unwilling to
delegate authority to take risky actions to agents (or programs). They may also have access to
information that can't be shared with agents. But their time may be scarce. And they may not
reliably make the same judgments time after time, especially if they get exhausted making lots of
them.

The choice for a step will depend on characteristics of the step itself. Take step 3, drafting
feedback:

- Its input is code, which an agent can read quickly. For 200 submissions, an agent helps
  timeliness and cost a great deal compared with the TA.
- A mistake there could tell a student about a bug that isn't in their code. That hurts
  correctness, which is why step 4 has a person review the drafts.
- The input data for the drafter includes a student's submission. If that submission contains
  sensitive information (e.g., a business plan for a startup company the student is developing),
  sending it to an agent's cloud provider may be an undesirable privacy risk.

Compare step 5, posting grades. Its input is a list of names and numbers that the TA has
already approved. Nothing about it needs judgment, and a mistake there changes someone's grade.
A program is the clear choice: it applies exactly what was approved.

Notice that steps 3 and 4 are the maker-checker pattern. And steps 3 and 5 are the propose-apply
pattern. Patterns can combine.

The check at step 4 costs the TA time every week. An alternative is to make step 3 more reliable
while building the workflow. For example, run it on last term's submissions, read every draft, and
revise the agent's instructions until the drafts are good. Then you might let the workflow run
without a review step. That saves time on every run, but it trusts that this week's submissions resemble the samples,
and that the agent still behaves as it did when tested. A check inside the workflow catches
mistakes on inputs nobody tried. Many designs do both: test thoroughly while building, then
review a random sample of each run's output.

## Putting it to use

When you build a workflow with an agent, you will be making these decisions whether or not you
notice. Naming them helps you make them on purpose, and helps you tell the agent what you want:
"save the test results to a file before the feedback step," "have a program post the grades, not
you." The vocabulary of goals, decisions and patterns will outlast any particular tool you use to
build a workflow.
