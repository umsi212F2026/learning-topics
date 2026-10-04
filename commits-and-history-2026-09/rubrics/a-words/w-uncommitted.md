# Rubric: uncommitted

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
