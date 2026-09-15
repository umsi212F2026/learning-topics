# Rubrics: Commit and restore

Answers for `tasks/commit-and-restore.md`. **Do not read this before attempting the questions.**

### q-ask-restore-commit

- **type:** free
- **goal:** c-commit-recovery-point
- **answer:** a request in plain words that names the target commit so the agent cannot pick a
  different one (by its message, "Add rating filter to task 1", or by asking the agent to find the
  commit with that message) and asks for every file in the repository to be put back to how it was
  at that commit, deleted file included. For example: "Put every file in my assignments repository
  back to exactly how it was at last Thursday's commit, 'Add rating filter to task 1', including any
  file that has been deleted since." A strong answer also asks the agent first to say whether
  anything is uncommitted, and afterward to say which commit the files now match.
- **credit:** full credit needs both: (a) the commit identified unambiguously, and (b) all the files
  put back to their state at that commit, not one file and not "my changes". Half credit for one of
  the two, for example "go back to an earlier version" with no commit named, or the commit named but
  only task1.py asked for. Full credit for "revert to last Thursday's commit" or "restore last Thursday's commit."
  Half credit at most for "undo that commit" or "revert that commit": those
  ask to take away the changes that commit made, which is a different request from going back to it
  ("revert to that commit", in the ordinary sense of going back to it, is fine). A git command is also fine, but don't expect those. Do not require the uncommitted check or the confirmation, and do not mark down informal
  wording.

### q-ask-commit-open-edits

- **type:** free
- **goal:** c-commit-recovery-point
- **answer:** save the file (every open file) first, because the agent reads the files on disk and
  cannot see what is unsaved in the editor; then ask the agent to commit everything that is saved,
  with a message that says what the work does. For example: "I've saved everything. Commit all my
  saved changes with the message 'Filter task 1 to movies with at least 50 ratings', and tell me
  when the commit has been made." A strong answer also asks the agent to confirm nothing is left
  uncommitted.
- **credit:** full credit needs both: saving before the request (as a step, or said in the request),
  and a clear request to commit the saved work. Half credit for a clear commit request that never
  mentions saving, since the version on screen may not be the version on disk. No credit for "save
  it to git" or "back it up" with no request for a commit. Do not require particular message wording
  or the confirmation.

### q-restore-reply-vague

- **type:** free
- **goal:** c-commit-recovery-point
- **answer:** no, it does not show that. It never says which commit the files now match ("back to
  normal" could mean the latest commit, not Thursday's, and "reverted your recent changes" is not the
  same as going back to Thursday), and it mentions only task1.py, not every file, so the deleted file
  and any other changed file may not be back. To check, open the files that had changed or been
  deleted since Thursday, not only task1.py, and see whether their contents are what they were at
  Thursday's commit. Or ask the agent for more details.
- **credit:** full credit needs that the reply does not establish the request was done, with at
  least one concrete reason (no commit named, "normal" is not Thursday's commit, or only task1.py is
  mentioned when every file was asked for). No credit for accepting the
  reply because it says "Done".

### q-commit-reply-staged

- **type:** free
- **goal:** c-commit-recovery-point
- **answer:** no. Staging only marks the changes for the next commit; nothing has been committed, and
  there is no new point in the history yet. Next, ask the agent to make the commit now, with a
  message, and to confirm it has been made.
- **credit:** full credit for "no" because staged is not committed, together with a next step that
  asks for the commit. Half credit for "no" with a next step but no reason, or with the reason and
  no next step. No credit for "yes", or for "no" on some other ground (such as the agent not having
  pushed).

### q-lost-after-restore

- **type:** mcq
- **goal:** c-commit-recovery-point
- **answer:** 1
- **credit:** changes that were saved and never committed are in no commit, so once the restore
  replaces them nothing in the repository holds them. 2 is exactly what the restore brings back. 3
  comes back too, because Tuesday's commit contains that file. 4 is in an earlier commit, which stays
  in the history and can still be restored.


### q-good-moment-commit

- **type:** free
- **goal:** c-commit-recovery-point
- **answer:** yes. The work is saved and in a known good state, it is one thing that a single message
  describes without needing "and" (something like "Get task 1 producing the correct top-ten list"),
  and a commit now is a point to come back to if the task 2 experiment goes badly.
- **credit:** full credit for "yes" with at least one of these reasons: task 1 is a working state
  worth being able to get back to; the experiment on task 2 is risky and a commit lets you return to
  here; the work is one thing that one message can describe. Half credit for "yes" with no reason, or
  with only a general one such as "commit often". No credit for "no", and no credit for a reason
  based on size ("it's enough work now", "wait until there's more"), since size is not the rule.

