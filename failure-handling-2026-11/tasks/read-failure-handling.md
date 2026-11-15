# When a step goes wrong

The reading on workflow design listed two intermediate goals that we take up now. The first is idempotency, whether a step, or the whole workflow, is safe to run again if it completed only partially the first time. The second is whether, when a step makes a mistake, it fails silently or loudly. Fixing any problem you find will mostly be your agent's work, once you can say what worries you.

Our scenario. The teaching assistant from the last three readings is still grading about 200 homework submissions a week. A program downloads each submission and runs its tests. An agent, following a skill file, drafts a score and feedback for each one, and its score goes into the grades sheet. The TA reviews the drafts, changes some, and a program posts the final grades to the course site.

## Two places a failure can be

Some failures stop things. The download program can't reach the course site, and it halts with an error. The test runner hits a submission that crashes it. Failures like these are annoying, but at least they are visible: the run didn't finish, and someone can see that it didn't.

Other failures don't stop anything. The agent misreads the test results and drafts full credit for code that failed half its tests, with confident, friendly feedback to match. Nothing crashed. The run finished. The grades sheet has a score in every row. Only the score is wrong.

The first kind raises the question of rerunning: the run stopped, so what happens when you start it again? The second kind raises the question of noticing: nothing stopped, so who will find out? A workflow with an agent in it has more of the second kind, because an agent's mistakes are often substantive ones: they look right but don't make sense when you think about them more closely.

## When a run stops partway

Suppose the drafting step stops after 120 of the 200 submissions, because the laptop went to sleep. The obvious fix is to run the step again from the start. Whether that is safe depends on what the step does to things that are already there. Here are three ways it can go wrong.

- **Items done a second time.** If the step adds a new row to the grades sheet for each submission it drafts, a rerun adds a second row for each of the first 120. Now some submissions have two drafted scores. Worse, if a step does something visible outside the workflow, a rerun does that twice too. For example, the posting program could email the same student two notices.
- **A store left half-written.** The step stopped while it was writing submission 121's feedback, so that file holds the first half of a paragraph. If the rerun skips any submission that already has a feedback file, it skips 121, and the half-written feedback goes on to the TA as if it were finished.
- **A different outcome replacing one already used.** By the time anyone notices the run stopped, the TA has already reviewed the first 50 drafts and changed some of the scores. A rerun asks the agent again, and the agent writes new drafts. Its new drafts overwrite the old ones. Now the sheet shows scores and feedback the TA never saw, in rows already marked as reviewed.

A step that can be run again without any of these problems is **idempotent**: running it twice leaves things the same as running it once. A step can be idempotent even when its executor is not predictable. The agent may give a different answer every time it is asked, but a step that skips any submission already drafted never asks it twice.

Three elements can contribute to idempotency: the process checks what is already done and skips it; it writes each result whole or not at all, so nothing is ever half-written; and it never replaces a result that something later has already used. The first of these has a trap. The test for "already done" has to be one the stopped run can't fool. "There is a feedback file" is fooled by a half-written file. "There is a feedback file, and the grades sheet marks it finished" is not, provided the step marks it finished only after the file is complete.

## Would anyone notice?

A **silent failure** is a mistake that nothing reports, so the run looks as if it worked. There are two reasons a mistake goes unnoticed, and they hold whoever does the step: a program, an agent, or a person.

- **The step could tell, but nobody hears.** The test runner can't build submission 87, so it writes "build failed" to a log file and moves on to 88. The step knew something went wrong and said so, but only in a log that nobody reads. A step that says nothing at all is worse: the download program can't open one submission, skips it, and the student simply never gets a grade.
- **The result looks right, and nothing checks it.** The agent's full credit for failing code is an example. It is a plausible score, in the right place, with feedback that reads well. Unless something compares it with the test results, nobody will know.

A check only helps if it looks at the thing that went wrong. Suppose the TA adds a program that confirms every row in the grades sheet has a drafted score (the sheet has a row for every submission, whether or not it was downloaded). That check is worth having: it would catch the skipped submission. It would not catch the full credit, because that is a legitimate score (just wrong for this student). A mistake is noticed only if the run stops, or if some check or some person's review would catch this particular mistake.

The TA's own review is a check too, and the same question applies to it. A TA who reads each draft's feedback but not anything from the student's work being graded will catch feedback that is rude or confusing, and miss a score that disagrees with the tests.

## Failing loudly

The workflow design reading put the intermediate goal this way: when something goes wrong, someone finds out. A step that does this **fails loudly**. It reports a problem where a person will see it, when they will see it.

Failing loudly doesn't have to mean stopping. If one submission won't build, there is no reason to hold up the other 199. The test runner can carry on, and add the submission to a short list of problems that the TA sees before reviewing anything. Stopping at the first sign of trouble is a different idea, usually called failing fast. It is the right choice when going on would make things worse, as when the posting program can't confirm which grades are already posted. A step could fail fast and still fail silently, if it stops and nobody looks.

For mistakes that look right, failing loudly means adding something that would catch them: a program that flags any drafted score above 6 for a submission that failed more than half its tests, or a review that puts the test results beside the score.

## Telling your agent

Once you have judged a step, you can tell your agent what worries you in plain words, and let it choose how to fix it.

| If you find... | you might tell your agent... |
| --- | --- |
| a rerun would do some items twice | "Make this step idempotent: if I run it again after it stops, it should skip what's already done." |
| a rerun could trust a half-written result | "Write each result so it is either complete or not there at all." |
| a rerun would replace results I've already reviewed | "Never overwrite a draft once it's marked reviewed." |
| a step could tell something went wrong, but nobody would hear | "Fail loudly: put every item you skip on a list I'll see before I start reviewing." |
| a step's result could be wrong and look right | "Add a check that compares each drafted score with its test results, and flag the ones that disagree." |

Your agent can do the rest, hopefully. You can then check what it built against what you asked for: run the step twice and see whether anything doubled, or feed it an input you know is bad and see whether you hear about it.
