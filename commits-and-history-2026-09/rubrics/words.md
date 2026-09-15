# Rubrics: The words of commits and history

Answers for `tasks/words.md`. **Do not read this before attempting the questions.**

### q-repository-vs-folder

- **type:** free
- **goal:** w-repository
- **move:** DISTINGUISH
- **answer:** an ordinary folder is only a place where files sit, holding their current contents
  and nothing more. A repository is a folder git is keeping track of: git keeps a record of the
  files inside it (the history of commits), so an earlier state of those files can be looked at or
  got back. In a folder that is not a repository, a file that is overwritten or deleted has no
  record to come back from.
- **credit:** full credit for saying that a repository comes with a record or history of what is
  inside it (or that git keeps track of changes to what is inside it), so earlier versions can be
  seen or got back. Also full credit for "git tracks the files in a repository" with no mention of a
  record, a history, or getting anything back; full credit also for "a repository has a hidden .git
  folder". Do not accept incidental differences: that a repository is on GitHub, that it holds code
  rather than documents, that it is shared, or that it is bigger.

### q-scratch-folder-tracked

- **type:** free
- **goal:** w-repository
- **move:** CATCH
- **answer:** the Desktop folder is outside the repository, and git only keeps track of what is
  inside a repository's boundary. Being a copy of a tracked file does not make the copy tracked:
  nothing done to it will be in the repository's commits or can be restored from them.
- **credit:** full credit for saying the copy is outside the repository (outside what git is keeping
  track of), so git is not tracking it. Half credit for "git doesn't track copies" with no reason
  given, because the reason is where the copy is, not that it is a copy. Do not accept a different
  quibble as the error: that they should have committed first, that copying files is bad practice,
  that they need to stage the file, or that the Desktop is a messy place to work.

### q-laptop-copy-folder

- **type:** free
- **goal:** w-repository
- **move:** CATCH
- **answer:** the copy on the laptop is itself a repository, not just a folder of files. It carries
  the history of commits, commits are made there in the first place, and earlier states can be
  restored from it without going to GitHub.
- **credit:** full credit for saying the laptop copy is a repository in its own right, with the
  commits (the history) in it. Full credit for "commits are made on your laptop first" without
  saying the laptop copy holds the history. Do not accept a different quibble as the error: that
  they should push more often, that GitHub is a backup, or that "real" is the wrong word. Do not
  accept "the GitHub one is the copy and the laptop one is the real one", which only reverses the
  mistake: both are repositories.

### q-outside-repo-report

- **type:** free
- **goal:** w-repository
- **move:** INTERPRET
- **answer:** ps1-notes.txt sits outside the boundary of what git is keeping track of for the
  assignments repository, so it cannot go into a commit and git has no record of it. That rules
  out getting an earlier version of ps1-notes.txt back from the repository's history, and rules
  out a restore of the repository protecting or bringing back that file.
- **credit:** full credit needs both halves: (a) the file is not inside the repository, so git has
  no record of it and cannot commit it; (b) one thing that not having it in the commit rules out, such as no earlier version of
  it can come back from the history, or a restore will not touch or protect it. Half credit for
  either half alone. No credit for reading "outside the repo" as the agent lacking permission, the
  file being broken, or the file having been deleted.


### q-commit-vs-save

- **type:** free
- **goal:** w-commit
- **move:** DISTINGUISH
- **answer:** saving writes what is in the editor to the file on disk, replacing that file's previous
  contents, and keeps no earlier version. Committing records the saved state of the repository's
  files as a new point in the history, alongside every earlier point, so you can get back to it
  after the files change again. A commit can only record what has already been saved.
- **credit:** full credit for the difference that matters: saving overwrites the file on disk and
  keeps nothing earlier, while a commit adds a point to the history that can be returned to after
  the files change. Either framing is fine: "save replaces, commit adds a point to go back to", or
  "save is to disk, commit is into a history you can return to". Half credit for an answer that
  names only an incidental difference with some truth in it, such as a commit having a message or
  covering several files, without the going-back. No credit for "committing is permanent saving" or
  "committing is saving to GitHub": commits are made in the repository on the laptop, and sending
  them to GitHub is a separate step.

### q-commit-replaces-last

- **type:** free
- **goal:** w-commit
- **move:** CATCH
- **answer:** a new commit does not replace the earlier one. It is added to the history, and every
  earlier commit stays there, so going back to the last commit is still possible after committing
  again.
- **credit:** full credit for saying commits are added to the history and earlier ones remain, so
  the last commit is still there to go back to. Do not accept a different quibble as the error:
  that they should commit more often (advice, not the mistake), that commits can be undone, or
  anything about pushing.

### q-restore-one-file

- **type:** free
- **goal:** w-commit
- **move:** CATCH
- **answer:** a commit records the whole state of the files, and any single file can be put back
  the way it was at that commit without touching the others. Having four files in one commit does
  not force them to be restored together.
- **credit:** full credit for saying one file can be put back as it was at that commit on its own
  (for example, by asking the agent for just task1.py). Do not accept a different quibble as the
  error: that four files should have been four commits, that the commit was too big, or that
  restoring all four would be harmless anyway. Whether it should have been more than one commit is
  a judgment about when to commit, and it is not what is wrong with the sentence.

### q-define-uncommitted

- **type:** free
- **goal:** w-uncommitted
- **move:** DEFINE
- **answer:** changes that have been saved in the files on disk but are not yet recorded in any
  commit: the gap between the files as they are now and the files as the latest commit recorded
  them. No commit holds them, so if the files are overwritten they cannot be got back from the
  history.
- **credit:** full credit for saying the saved files differ from what the last commit recorded (work
  done since the last commit that is not in the history yet). Full credit for "changes that haven't
  been committed" together with a correct consequence (they cannot be restored if lost); no credit for "not committed yet" alone.
  No credit for "unsaved" or "not saved", which is a different gap, between the editor and the disk.
  No credit for "local changes" alone, which is another name for the same thing and not a
  definition.

### q-uncommitted-vs-unsaved

- **type:** free
- **goal:** w-uncommitted
- **move:** DISTINGUISH
- **answer:** unsaved work exists only in the editor: what is on screen differs from the file on
  disk, and an agent, which reads the disk, cannot see it. Uncommitted work has been saved, so the
  agent can see it, but the files on disk differ from what the latest commit recorded, so it is not
  in the history. The first gap is between the editor and the disk; the second is between the disk
  and the last commit. Saving closes the first gap and not the second.
- **credit:** full credit for placing both gaps correctly: unsaved means edits in the editor not yet
  written to disk, and uncommitted means saved files that differ from the last commit. Saying the
  agent cannot see unsaved work is a strong addition and is not required. Half credit for getting
  one gap right and leaving the other vague or wrong. No credit for treating them as the same thing,
  for saying uncommitted work is a kind of unsaved work, or for a difference of degree ("uncommitted
  is more serious").

### q-saved-so-committed

- **type:** free
- **goal:** w-uncommitted
- **move:** CATCH
- **answer:** saving writes the work to disk; it does not commit it. Saved work stays uncommitted
  until a commit records it, so having saved every file says nothing about whether anything is
  uncommitted.
- **credit:** full credit for saying saving and committing are different steps, so saved work can
  still be uncommitted. Do not accept a different quibble as the error: that they should also push,
  that their editor may autosave, or that they might have missed a file when saving.

### q-clean-so-editor-safe

- **type:** free
- **goal:** w-uncommitted
- **move:** CATCH
- **answer:** "no uncommitted changes" compares only the saved files on disk with the last commit.
  It says nothing about edits sitting unsaved in the editor, which the agent cannot see. If any
  open file has unsaved edits, those are not in the last commit, so the conclusion does not follow.
- **credit:** full credit for naming the leap: the check covers what is saved on disk, and unsaved
  edits in the editor are invisible to it, so they may not be in the commit. Do not accept a
  different quibble as the error: that the agent might be wrong about there being no uncommitted
  changes, that some files may not be tracked, or that the commit may not have been pushed. An
  answer that doubts the first half of the sentence instead of the leap from disk to editor has not
  found the error.

### q-local-changes-restore

- **type:** free
- **goal:** w-uncommitted
- **move:** INTERPRET
- **answer:** task1.py, as saved on disk, holds changes that no commit recorded. If the restore goes
  ahead, Thursday's version replaces them, and since no commit holds them they cannot be brought
  back afterward. The risk is that you can't get the current task1.py back from the history later, so they
  would need committing (or copying somewhere) first if they matter.
- **credit:** full credit for saying the changes to task1.py will be lost and/or it won't be possible to recover them. No credit for reading "local changes" as unsaved edits
  in the editor, or as changes that are merely on the laptop and not yet on GitHub. Do not require
  anything about the other files.

### q-staging-vs-working-directory

- **type:** free
- **goal:** w-staging-area
- **move:** DISTINGUISH
- **answer:** the working directory is the files as they are saved on disk right now, which is what
  you and your agent edit. The staging area holds what has been marked for inclusion in the next
  commit. A change can be in the working directory without being staged, and then the next commit
  will not include it.
- **credit:** full credit for both: the working directory is the saved files on disk (what gets
  edited, what the agent sees), and the staging area is what is marked to go into the next commit.
  Half credit for one right and the other missing or wrong. No credit for describing the staging
  area as another folder of files you work in, as a backup, or as part of the history (nothing in it
  is committed yet), and no credit for "the working directory is on my laptop and the staging area
  is on GitHub".

### q-staged-so-in-history

- **type:** free
- **goal:** w-staging-area
- **move:** CATCH
- **answer:** staging only marks changes for inclusion in the next commit. Nothing reaches the
  history until a commit is made, so there is no point in the history for this version of task1.py
  yet.
- **credit:** full credit for saying staged is not committed: it is in the history only once a
  commit is made. Do not accept a different quibble as the error: that they should push, that
  staging is an unnecessary step, or that other files should have been staged too.

### q-saved-so-staged

- **type:** free
- **goal:** w-staging-area
- **move:** CATCH
- **answer:** saving puts the edits into the working directory (the file on disk), not into the
  staging area. Staging is a separate step that marks changes for the next commit, and a saved
  change is not staged until someone, usually the agent, stages it.
- **credit:** full credit for saying saving and staging are separate, so a saved change is in the
  working directory and still has to be staged. An answer saying the agent has to stage it first
  has named the error and gets full credit. Do not accept a different quibble as the error: that
  they also need to commit, that their editor may autosave, or that staging is optional.

### q-staged-two-files

- **type:** mcq
- **goal:** w-staging-area
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 confuses staged with committed, and the agent says nothing is committed. 3 reads
  "left out of the staging area" as discarded; the changes are still in the working directory. 4
  ignores the staging area: having changes is not the same as being marked for the next commit.


### q-diff-omits-file

- **type:** free
- **goal:** w-diff
- **move:** CATCH
- **answer:** a diff shows only what differs between the two commits. A file it does not mention is
  the same in both. If notes.md had been deleted, the diff would show it, as every line of the file
  removed.
- **credit:** full credit for saying that a file missing from the diff has not changed between the
  two commits, and a deletion would appear in the diff. Either half alone is enough if it is clearly
  stated as the reason the conclusion is wrong. Do not accept a different quibble as the error: that
  the agent may have made a mistake, that they should look on GitHub, or that the commit message
  would say.

### q-diff-between-commits

- **type:** free
- **goal:** w-diff
- **move:** INTERPRET
- **answer:** between those two commits, task1.py differs in three lines where the ratings file is
  loaded, and nothing else differs. That rules out any other file having changed between Thursday's
  commit and the latest one (they are the same in both), and rules out a change anywhere else in
  task1.py. It says nothing about work done since the latest commit.
- **credit:** full credit for recovering the claim (three lines of task1.py changed between the two
  commits) and at least one thing it rules out (every other file is the same in both commits, or
  the rest of task1.py is unchanged). Half credit for the claim with nothing it rules out. No credit
  for reading it as "the latest commit only contains task1.py" or "only three lines are stored in the
  latest commit": the comparison says what differs, and both commits still hold every file. Saying
  it tells you nothing about uncommitted work is a good addition and is not required.

### q-define-history

- **type:** free
- **goal:** w-history
- **move:** DEFINE
- **answer:** all the commits made in the repository, taken together in order: the record of each
  committed state, with its message, that can be looked back through, compared, and returned to.
- **credit:** full credit for saying it is the repository's commits taken together (the sequence or
  record of committed states). Full credit for "a record of past versions" even if it does not tie those
  versions to commits. No credit for "the log" alone, which is another name for it, and no credit
  for "a record of every change you have made", which would include edits that were never committed.

### q-history-vs-undo

- **type:** free
- **goal:** w-history
- **move:** DISTINGUISH
- **answer:** an editor's undo history captures each edit made to a file in that editor, but it lives
  only in the editor and does not survive an agent rewriting the file. A repository's history holds
  only the moments someone committed, but at each one it holds the state of all the files, it is
  kept in the repository itself, and it survives the editor closing and an agent rewriting files.
- **credit:** full credit for either difference that matters, stated clearly: (a) git's history is
  kept in the repository and survives what undo history does not (an agent rewriting the file, the
  editor closing); or (b) undo history captures each edit as it happens, while git's history has
  only the points someone chose to commit. Half credit for an answer that says only where each lives
  ("one is in the editor, one is in git") with no consequence. No credit for incidental differences
  such as keyboard shortcuts, or git's history having messages.

### q-history-every-change

- **type:** free
- **goal:** w-history
- **move:** CATCH
- **answer:** the history holds only commits. Changes made since this morning's commit are not in
  it, so there is no point in the history for how task1.py looked an hour ago; this morning's commit
  and earlier ones are all that can be returned to.
- **credit:** full credit for saying the history contains only what was committed, so edits since
  the last commit are not in it. Do not accept a different quibble as the error: that the editor's
  undo might still work, that they should commit more often (advice, not the mistake), or that
  GitHub might have a copy.

### q-log-last-commit

- **type:** free
- **goal:** w-history
- **move:** INTERPRET
- **answer:** Probably not deleted, though you'd have to check separately for that. None of the work since Thursday is in the history; the latest point that can be
  returned to is Thursday's "Add rating filter to task 1" commit. That rules out getting back any
  in-between version of task1.py from the history, and it means a restore to Thursday's commit would
  lose the work since. The work may still be in the files, uncommitted, but no commit holds it.
- **credit:** full credit for saying it's not necessarily deleted but that if it does get deleted it can't be recovered. No credit for reading the message as
  saying the work since Thursday is already lost or deleted: it says only that none has been
  committed.

### q-define-merge

- **type:** free
- **goal:** w-merge
- **move:** DEFINE
- **answer:** combining two lines of work that went separate ways (your commits and the instructor's)
  into one record, so that the files end up with both sets of changes, and the history keeps both
  lines of commits, joined together.
- **credit:** full credit for saying two lines of work that went separate ways are combined into one,
  with both sides' changes kept. Mentioning the commit that joins them is good and is not required.
  No penalty if they don't mention explicitly that both lines of work are kept, with neither replaced.
No credit for
  "pulling" or "updating", which name the occasion rather than the thing, or for any answer in which
  one side's work replaces the other's.



### q-merge-drops-mine

- **type:** free
- **goal:** w-merge
- **move:** CATCH
- **answer:** a merge combines both lines of work, so the instructor's changes and the student's both
  end up in the files. Nothing is thrown away. Where both changed the same lines, git does not pick
  either side; it stops with a merge conflict so someone can decide.
- **credit:** full credit for saying a merge keeps both sides' changes (combines rather than
  replaces). Mentioning conflicts is a good addition and is not required. Do not accept a different
  quibble as the error: that they should commit before pulling, that the instructor's version is
  probably better, or that a rebase would behave differently.

### q-merge-erased-commits

- **type:** free
- **goal:** w-merge
- **move:** CATCH
- **answer:** a merge keeps both lines of commits. The commits from last week are still in the
  history, alongside the instructor's, with the merge joining the two.
- **credit:** full credit for saying both sides' commits remain in the history after a merge (a merge
  adds, it does not replace). Do not accept a different quibble as the error: that they should check
  GitHub, that they should have pushed first, or that the agent may have done something other than a
  merge. The sentence is about a merge, and what it says a merge does is the mistake.

### q-merged-no-conflicts

- **type:** mcq
- **goal:** w-merge
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 and 3 describe a merge throwing away or setting aside one side's work, which a merge
  does not do. 4 claims too much: "no conflicts" rules out git having to stop over the same lines,
  not the two of you having changed the same file, since changes to different parts of one file
  combine without a conflict.

### q-conflict-vs-error

- **type:** free
- **goal:** w-merge-conflict
- **move:** DISTINGUISH
- **answer:** an error means something failed or went wrong. A merge conflict is git stopping on
  purpose because both sides changed the same lines and it will not choose between the two changes.
  Nothing is broken: the merge is paused, waiting for someone to decide what those lines should say,
  and it can finish once they do.
- **credit:** full credit for saying a conflict is git deliberately stopping so someone can choose
  between two changes to the same lines, and not something having failed or broken. Full credit for
  "a conflict needs someone to decide" without saying it is not a failure. Half credit for "nothing is
  broken" without saying why git stopped. No credit for "a conflict is a kind of error that happens
  when two people edit a file", or for incidental differences such as the wording or colour of the
  message.

### q-conflict-different-files

- **type:** free
- **goal:** w-merge-conflict
- **move:** CATCH
- **answer:** changes to different files do not conflict: git combines them on its own. A merge
  conflict needs both sides to have changed the same lines of the same file, so these two changes
  could not by themselves cause one.
- **credit:** full credit for saying different files combine without a conflict, because a conflict
  needs both sides changing the same lines. Do not accept a different quibble as the error: that
  they should have pulled sooner, that README.txt should not be edited, or that the agent should
  have rebased.

### q-git-picks-newer

- **type:** free
- **goal:** w-merge-conflict
- **move:** CATCH
- **answer:** git does not choose between two changes to the same lines, by date or in any other way.
  That is exactly where it stops: a merge conflict is the place git refuses to choose, and someone
  has to decide, either a person or their agent.
- **credit:** full credit for saying git does not pick a side but stops and leaves the choice to a
  person (or to the agent, with the person). An answer saying git cannot tell which is newer counts
  only if it also says git stops instead of choosing. Do not accept a different quibble as the error:
  that the instructor's change should win, that conflicts are rare, or that "newer" is hard to
  define.


### q-what-makes-conflict

- **type:** mcq
- **goal:** w-merge-conflict
- **move:** DEFINE
- **answer:** 2
- **credit:** 1 is two different files, which combine on their own. 3 is a file only one side has,
  which comes in without a conflict. 4 involves the editor, not a merge: unsaved edits are invisible
  to git and are not one of the two changes a conflict is between.
