# Rubric: history

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
- **answer:** no, or at least the message does not say so. It says only that nothing has been
  committed since Thursday, so none of the work since then is in the history: the latest point that
  can be returned to is Thursday's "Add rating filter to task 1" commit. The work may well still be
  in task1.py, uncommitted, but if it were lost now the history could not bring it back.
- **credit:** full credit for "no" (or "not necessarily") because the message is only about
  commits: the work since Thursday is uncommitted, so it is not in the history, and it may still be
  in the files. "No, it's only uncommitted" earns full credit. Saying that the history could not
  bring the work back if it were lost is welcome and is not required. Half credit for "no" with no
  reason, or with a reason that is not about commits, such as "the agent would have said so". No
  credit for reading the message as saying the work since Thursday is already lost or deleted: it
  says only that none has been committed.
