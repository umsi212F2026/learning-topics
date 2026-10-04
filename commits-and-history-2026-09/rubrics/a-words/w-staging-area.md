# Rubric: staging area

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
