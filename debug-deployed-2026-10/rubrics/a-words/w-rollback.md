# Rubric: rollback

If the learner misses a question here, set a DEFINE or INTERPRET move for rollback live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A rollback puts the last working deploy back in place on the host: an earlier version, already
built, serves again, and the repository is not touched. The confusables are a redeploy, which
deploys again, normally the same latest code; and a git revert, a new commit in the repository that
undoes a change, which reaches visitors only once it is pushed, built and deployed. "Roll back" is
the same thing as a verb and is not a confusable. Tallowcloud is a made-up host.

### q1

- **goal:** `w-rollback`
- **move:** DISTINGUISH
- **answer:** A rollback puts the earlier, working deploy back, so visitors get the last version
  that worked. A redeploy deploys again, normally the same latest code, so the broken version would
  come back up.
- **credit:** full for naming which version ends up serving: the last working one after a
  rollback, the current (broken) code again after a redeploy. Half for only one half, such as "a
  rollback goes back to the old version" with nothing on what a redeploy deploys. None for an
  incidental difference alone, such as which button is where, or which is faster.
- **tutor note:** a learner who knows a host can redeploy an older commit has a point; ask what a
  redeploy of the latest deploy would serve.

### q2

- **goal:** `w-rollback`
- **move:** CATCH
- **answer:** A rollback only changes which deploy the host serves; it doesn't touch the code in
  the repository. The broken commit is still on main, so the next push builds and deploys it again
  along with the new features.
- **credit:** full for naming that a rollback happens on the host and leaves the repository as it
  was, so the next push brings the broken change back. Half for "the commit is still there" without
  saying what follows when they push. None for a different quibble alone, such as that they should
  tell the team first, or should write a test.

### q3

- **goal:** `w-rollback`
- **move:** DISTINGUISH
- **answer:** A rollback happens on the host: it puts an earlier deploy back in place at once,
  with no new build, and leaves the repository as it was. A git revert happens in the repository:
  a new commit that undoes the change, which visitors only get once it is pushed, built and
  deployed, and which keeps the bad change out of later pushes.
- **credit:** full for naming where each happens and what follows: the rollback changes what the
  host serves and not the code, the revert changes the code and reaches visitors only through a new
  deploy. Half for only one half, such as "a revert changes the code" with nothing on the rollback.
  None for an incidental difference alone, such as that one is a button and the other a command.
