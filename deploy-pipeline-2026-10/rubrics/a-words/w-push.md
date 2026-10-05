# Rubric: push

What it names: sending your commits from your machine up to GitHub. Nearest confusable: commit.

### q-push-vs-commit

- **goal:** `w-push`
- **move:** DISTINGUISH
- **answer:** A commit records a snapshot of the changes in the repository on your own machine,
  where nobody else sees it. A push sends commits you have already made up to GitHub. Committing
  changes nothing on GitHub; pushing makes nothing new, it only moves existing commits.
- **credit:** full for the difference that matters: a commit is recorded on your own machine, and a
  push sends commits already made from your machine to GitHub. Half for "commit saves, push
  uploads" with nothing on a push carrying commits, or on where each one happens. None for an
  incidental difference, such as that a commit has a message and a push doesn't.

### q-catch-push-before-commit

- **goal:** `w-push`
- **move:** CATCH
- **answer:** A push sends commits, and the new heading isn't in one yet. Saving the file changed
  it on their machine only; until it is committed, there is nothing to push, so it is not on
  GitHub. The commit has to come first.
- **credit:** full for naming the actual error: a push only sends commits, so an uncommitted change
  cannot have been pushed and is not on GitHub. Half for "you have to commit before you push" with
  nothing on a push being what carries commits. None for a different quibble, such as that they
  should test it before pushing, or that they should commit more often.
