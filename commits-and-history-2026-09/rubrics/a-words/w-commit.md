# Rubric: commit

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
