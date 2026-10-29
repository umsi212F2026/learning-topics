# Designing a workflow

This page is about the choices you make when you design a workflow. It
gives the whole layout and then looks closely at two decisions, how to divide a workflow into
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

- **Inspectable intermediate results:** what each step produced is saved where a person or a
  program can look at it.
- **Steps that are safe to rerun:** running a step twice does no harm.
- **A single source of truth:** each fact is stored in one place, so two copies can't disagree.
- **Least privilege:** each part can touch only what it needs.
- **Failing loudly:** when something goes wrong, someone finds out.

Checking that results are right is an intermediate goal too. Nobody wants checking for its own
sake. They want correct grades, and checking is one way to get them.

## Trade-offs

An option rarely advances every goal at once. Having a person read every submission might make
the feedback better, and it costs the TA a whole weekend. Having an agent write the feedback is
fast and cheap, and it means sending student code to the agent's provider. A **trade-off** is
what you see when one option helps some goals and hurts others.

Most of design is arguing about trade-offs, and an argument is only as good as its reasons. "An
agent is cheaper" is true of almost every step, so it doesn't say anything about this step. A
good reason points at something particular to the step: what its input is, what a mistake there
would cost, what data it handles.

## Design patterns

Some combinations of options turn up again and again, because they work well together. A
**design pattern** is a named set of design choices that are often made together. Two you will
meet in this topic:

- **Each step reads from a store and writes to one.** Instead of passing results straight from
  one step to the next, each step saves its output, and the next step reads it from there.
- **The agent proposes, a program applies.** An agent decides what should change, and writes that
  down; a program, which behaves the same way every time, makes the change.

A pattern is not a rule. It brings its own trade-offs, and part of using one well is knowing what
it costs. Patterns are also useful as names. Telling your agent "use the propose-and-apply
pattern for the gradebook step" says a lot in a few words.

## Dividing a workflow into steps

Suppose the TA's first design has one step: "an agent grades each submission." It might work.
But when a student complains that their grade is wrong, there is nothing to look at except the
grade. Did the code fail its tests, or did the agent misread the results? Nobody can tell.

Here is a better division, with who does each step:

1. Collect the submissions into a folder. (a program)
2. Run the tests on each one, and save the results. (a program)
3. Draft written feedback from the code and its test results. (an AI agent)
4. Review the drafts and settle each grade. (the TA)
5. Post the grades to the gradebook. (a program)

Two rules of thumb produced those boundaries.

**Put a boundary wherever the kind of check changes.** Test results are checked one way: did the
same code get the same results every time? Written feedback is checked another way: a person
reads some of it and asks whether it is fair and accurate. When two parts of the work need
different checks, make them different steps, so each can get its own.

**Put a boundary wherever the executor changes.** The executor is whatever carries out a step: a
program, an agent or a person. Where the work passes from one to another, there is a handoff, and
a handoff is a natural place to stop and look.

**Then save what each step produces.** A boundary helps only if the result at that boundary is
kept. Because step 2 saves the test results, the TA can open them when a student complains and
see whether the tests or the feedback went wrong. Each step can now be checked on its own.

More steps are not always better. Every boundary adds something to save, to name and to keep in
sync. A boundary earns its place when it lets you check something you otherwise couldn't.

## Who does each step

Each step can be done by a person, an AI agent or a program. None is best everywhere. A program
gives the same answer every time and costs almost nothing to run, but it can't use judgment. An
agent can use judgment on messy input, but it can be wrong in ways that look right. A person has
the best judgment and the least time.

The choice for a step comes from the step itself. Take step 3, drafting feedback:

- Its input is code, which an agent can read quickly. For 200 submissions, an agent helps
  timeliness and cost a great deal compared with the TA.
- A mistake there could tell a student about a bug that isn't in their code. That hurts
  correctness, and it is why step 4 has a person review the drafts.
- The data is student work with names attached. Sending it to an agent's provider is a privacy
  question the course has to have settled.

Compare step 5, posting grades. Its input is a list of names and numbers that the TA has
already approved. Nothing about it needs judgment, and a mistake there changes someone's grade.
A program is the clear choice: it applies exactly what was approved, the same way every time.
That is the agent-proposes, program-applies pattern again, with the TA in the middle.

## Putting it to use

When you build a workflow with an agent, you will be making these decisions whether or not you
notice. Naming them helps you make them on purpose, and helps you tell the agent what you want:
"save the test results to a file before the feedback step," "have a script post the grades, not
you." The vocabulary of goals, decisions and patterns will outlast any particular tool you use to
build a workflow.
