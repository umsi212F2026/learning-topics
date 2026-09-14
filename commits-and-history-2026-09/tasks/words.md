# The words of commits and history

**Intended goals:** `w-repository`, `w-commit`, `w-uncommitted`, `w-staging-area`, `w-diff`,
`w-history`, `w-merge` and `w-merge-conflict`.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes an AI coding agent, imagine it is working in one of your own course repositories.

### q-repository-vs-folder

Your assignments live in a folder on your laptop, and that folder is also a git repository. What
separates a repository from an ordinary folder?

### q-scratch-folder-tracked

A classmate says: "I made a new folder called scratch on my Desktop and copied task1.py into it to
try something out. Git will track my changes to it there too, since it's the same file as the one
in my assignments repository." What is wrong with what they said?

### q-laptop-copy-folder

A classmate says: "My real repository is the one on GitHub. The copy on my laptop is just a folder
with the files in it, and the commits are only kept on GitHub." What is wrong with what they said?

### q-outside-repo-report

You ask your agent to commit your work, and it replies: "I can't include ps1-notes.txt in the
commit: it's in your Documents folder, outside the assignments repo." What is the agent telling
you, and what does that rule out?

### q-define-commit

Say what a commit is, in your own words.

### q-commit-vs-save

Saving a file and committing it both have something to do with keeping your work. What is the
difference between them?

### q-commit-replaces-last

A classmate says: "I don't want to commit yet. If I commit now, the new commit replaces my last
one, and then I can't go back to how things were at that last commit." What is wrong with what
they said?

### q-restore-one-file

A classmate says: "The agent put task1.py, task2.py, notes.md and results.json all in one commit.
So if I only want task1.py back the way it was at that commit, I'm stuck restoring all four files."
What is wrong with what they said?

### q-define-uncommitted

Your agent tells you that some of your work is uncommitted. Say what "uncommitted" means, in your
own words.

### q-uncommitted-vs-unsaved

What is the difference between work that is unsaved and work that is uncommitted?

### q-saved-so-committed

A classmate says: "I hit save on every file before I closed my laptop, so none of my work is
uncommitted." What is wrong with what they said?

### q-clean-so-editor-safe

An agent says: "There are no uncommitted changes in your repository, so everything you can see in
your editor right now is in your last commit." What is wrong with what it said?

### q-local-changes-restore

You ask your agent to put your files back to Thursday's commit, and it replies: "Before I do that:
task1.py has local changes that aren't in any commit. Should I go ahead?" What is the agent telling
you, and what does it rule out?

### q-staging-vs-working-directory

What is the difference between the staging area and the working directory?

### q-staged-so-in-history

A classmate says: "I had the agent stage my changes to task1.py, so they're in the history now, as
a point I can go back to." What is wrong with what they said?

### q-saved-so-staged

A classmate says: "Once I save a file in my editor, it's in the staging area, ready for the next
commit." What is wrong with what they said?

### q-staged-two-files

Your agent says: "I've staged task1.py and notes.md. results.json has changes too, but I left it
out of the staging area. Nothing is committed yet." Which of these is true right now?

1. If a commit is made now, it will include the changes to task1.py and notes.md but not the changes to results.json.
2. task1.py and notes.md are now in the history, and results.json is not.
3. The changes to results.json have been thrown away.
4. If a commit is made now, it will include all three files, because all three have changes.

### q-diff-vs-status

Your agent can tell you the status of your repository, or it can show you a diff. What is the
difference between what those two tell you?

### q-diff-is-commit

A classmate, looking at a commit on GitHub, says: "The red and green lines are what this commit
contains. Git only stores the lines that changed." What is wrong with what they said?

### q-diff-omits-file

A classmate says: "The diff between Thursday's commit and my latest commit doesn't mention notes.md
anywhere, so notes.md must have been deleted." What is wrong with what they said?

### q-diff-between-commits

Your agent says: "I compared your commit from Thursday with your latest commit. The only
differences are in task1.py: three lines changed near the top, where the ratings file is loaded."
What is being claimed, and what does it rule out?

### q-define-history

In git, what is a repository's history?

### q-history-vs-undo

Your editor keeps an undo history, and a git repository has a history. What is the difference
between them?

### q-history-every-change

A classmate says: "I haven't committed since this morning, but that's fine. Git's history records
every change I make, so I can go back to how task1.py looked an hour ago." What is wrong with what
they said?

### q-log-last-commit

It is Sunday, and you have been working on task1.py since Thursday. Your agent says: "Your log
shows the last commit was on Thursday afternoon, 'Add rating filter to task 1'. Nothing has been
committed since." What does that tell you about the work you have done since Thursday, and what
does it rule out?

### q-define-merge

In this course you pull the instructor's updates into repositories where you have already made
commits of your own, and when that happens git does a merge. Say what a merge is.

### q-merge-vs-rebase

When you pull the instructor's updates into work you have already committed, an agent may ask
whether to merge or to rebase. What is the difference between the two?

### q-merge-drops-mine

A classmate says: "Merging the instructor's updates means git takes their version of the files and
throws away mine." What is wrong with what they said?

### q-merge-erased-commits

A classmate says: "After the agent merged the instructor's updates, the commits I made last week
aren't in the history anymore. The merge replaced them with the instructor's commits." What is
wrong with what they said?

### q-merged-no-conflicts

Your agent says: "I pulled the instructor's updates and merged them with your two commits from this
week. No conflicts." Which of these does that tell you?

1. Your two commits and the instructor's updates are now combined, and git did not have to stop anywhere for lines you both changed.
2. The instructor's updates replaced your two commits.
3. Your two commits were set aside so that the instructor's updates could go in cleanly.
4. The instructor did not change any file that you changed.

### q-conflict-vs-error

While pulling the instructor's updates, your agent reports a merge conflict. How is a merge
conflict different from an error?

### q-conflict-different-files

A classmate says: "We got a merge conflict because, since my last pull, the instructor changed
README.txt and I changed task1.py." What is wrong with what they said?

### q-git-picks-newer

A classmate says: "Don't worry about merge conflicts. When two changes hit the same lines, git just
keeps whichever change is newer." What is wrong with what they said?

### q-conflict-report

Your agent says: "Pulling the instructor's updates stopped with a conflict in task1.py. You and the
instructor both changed the lines that load the ratings file. Everything else came in without
trouble. Do you want to keep your version of those lines, the instructor's, or combine them?" What
is the agent telling you, and what does it rule out?

### q-what-makes-conflict

Which of these would produce a merge conflict when you pull the instructor's updates?

1. You changed task1.py, and the instructor changed README.txt.
2. You and the instructor both changed the same line of task1.py, in different ways.
3. The instructor added a new file, task3.py, that you do not have.
4. You have task1.py open in your editor with unsaved edits while the agent pulls.
