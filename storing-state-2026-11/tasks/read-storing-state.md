# What a workflow keeps, and who gets to touch it

The reading on workflow design introduced checkpoints: each step saves its output, and the next
step reads it from there. It left for later the question of how things are stored, and that is
what this page takes up. It doesn't ask you to choose file
formats or databases; your agent can do that. It asks you to decide something your agent can't
work out on its own: who needs to touch each thing the workflow keeps, and how.

Our scenario. The teaching assistant from the last two readings is still grading about 200 homework submissions
a week. Each submission arrives on the course site. A program downloads it. An agent, following a
skill file, drafts a score and feedback. The TA reviews the drafts, changes some, and the grades are
posted.

## What a workflow stores

Everything the workflow has to remember from one step to the next, or from one run to the next, is
its **state**. 

The TA's workflow keeps several things:

- the downloaded submissions;
- the rubric, which the TA wrote and the agent follows;
- a grades sheet, with one row per submission: the drafted score, the TA's final score, and whether
  the grade has been posted;
- the agent's feedback drafts, one per submission;
- a record of each run: when it started, which submissions it handled, and anything that went
  wrong.

For each piece of state that is stored, ask two questions: who touches it, and what kind of access does each of them need?

## Four kinds of access

- **Reading it through.** Someone takes in the whole thing, start to end. For example, the agent reads the
  whole rubric before drafting any feedback.
- **Querying it.** Someone asks for just the records that match, rather than reading everything.
  "Which submissions have a drafted score but no final score yet?" is a **query**. With 200 rows,
  reading through to find the needed rows is fine. With 20,000, you'd rather have a query.
- **Editing it.** Someone changes records that are already there. When the TA raises a drafted
  score from 7 to 8, that is an edit.
- **Append-only.** Someone adds new records and never changes or removes old ones. The classic append-only store is a **log file**. Programs and servers keep logs of what they did,
one line per event, each new line added at the end. Nobody goes back and edits yesterday's lines,
which is what makes a log trustworthy: what it says happened is what happened.

## Who, and which kind

Often several parties access the same data store, and they need different kinds of access. Take the
grades sheet.

- The download program **appends** a row for each new submission.
- The agent's step **edits** a row to fill in the drafted score. (Or, with the propose-apply pattern,
  the agent proposes a score and a program writes it in. Either way, something edits the row.)
- The TA reads it through and **edits** by hand, changing final scores.
- The posting program **queries** it for rows with a final score that haven't been posted, posts
  them, and **edits** each row to mark it posted.

Writing out who needs what kind of access will drive decisions about what technologies and data formats to use. The
TA edits by hand, so the sheet has to be something a person can open and change comfortably. The
posting program queries it, so particular rows have to be easy to find. You can rely on your agent to make reasonable decisions about that once you've clearly specified the access requirements. 

Narrowing access is a decision too. Does the agent need to edit the grades sheet at all, or could
it only append its drafts somewhere and let a program copy them in? The less each party is allowed
to do, the fewer ways things can go wrong. This is the intermediate goal the workflow design
reading called **least privilege**: each part can touch only what it needs.

## When two writers collide

Suppose the posting program runs at noon, and takes a while. It opens the grades sheet, works
through it, and when it finishes it saves the whole sheet back. Meanwhile, at 12:05, the TA opens
the same sheet, changes three final scores, and saves. If the program saves after the TA does, it
writes back its own copy, the one it opened at noon, and the TA's three changes are gone. Nobody
gets an error. The scores are simply wrong.

That is a **race condition**: the result depends on which of two things running at the same time
gets there first. It can happen between a person and a program, or between two runs of the same
workflow, when one run is still going as the next one starts.

A race needs two things: more than one writer at the same time, and at least one of them changing
what is already there. So there are two ways to prevent one.

- **Make the writers append.** If every writer only adds new records, one writer can't wipe out
  another's work. Several runs can add lines to the run record without trouble. This is a big part
  of why logs are append-only.
- **Use storage built for simultaneous edits.** When several writers really do need to edit the same
  records at the same time, the storage has to handle it, so that each change is made whole and
  none is lost. A database does this, and a plain file usually doesn't. Your job is to notice that
  the danger exists and say so. Choosing how to handle it is your agent's.

An alternative to preventing a race is to notice the collision and recover from it. Git is a
familiar example. Two branches can change the same lines of a file. The edits may be days apart,
but they are effectively simultaneous: each was made on a copy that didn't include the other. When
the branches are merged, Git notices the collision and, rather than letting one quietly win the
race, stops with a **merge conflict** and asks the user (or their agent) to resolve it. A merge
conflict is a race detected rather than prevented.

If writes never overlap, because only one writer exists or the writers never run at the same time,
there is no danger, and a simple file is fine.

## One place for each thing

Suppose the final score is in the grades sheet, and also at the top of each feedback draft. The TA
changes a score in the sheet and forgets the draft. Now the two disagree, and nothing says which one
to believe.

The fix is the intermediate goal the workflow design reading named: a **single source of truth**
for each thing, the one place it is kept and changed. Everything else is a copy taken from it. If the feedback draft needs to show the score, it
is filled in from the sheet just before posting, never typed in separately.

## Telling your agent

Once you have decided who gets which kind of access, the storage requirements follow, and you can
hand them to your agent in plain words.

| If you decide... | then the storage has to... |
| --- | --- |
| a person reads or edits it by hand | be something they can open and change in a tool they already use, like a spreadsheet app or a text editor |
| an agent reads it | be plain text, split so the agent can read only the part it needs |
| several writers only append | let each writer add records without touching the ones already there |
| someone queries it | let particular records be found without reading everything |
| several writers edit the same records at once | handle simultaneous edits without losing any |

So instead of "store the grades in JSON," which picks a format before you know what you need, you
might tell your agent: "I'll edit the final scores by hand in a spreadsheet app. The posting
program needs to find unposted rows. Runs may overlap, so make sure two writers can't overwrite
each other's changes." The agent can pick a format and a store that meet those requirements. You
can then check its choice against the list: if it picked a format you can't comfortably edit by
hand, you know to push back.
