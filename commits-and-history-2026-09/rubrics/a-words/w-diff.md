# Rubric: diff

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
