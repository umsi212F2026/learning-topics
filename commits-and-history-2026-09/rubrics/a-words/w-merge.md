# Rubric: merge

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
