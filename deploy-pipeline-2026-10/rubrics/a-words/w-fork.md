# Rubric: fork

What it names: your own copy, on GitHub, of a repository someone else owns. Nearest confusable: a
clone.

### q-fork-vs-clone

- **goal:** `w-fork`
- **move:** DISTINGUISH
- **answer:** Forking makes a copy of the repository on GitHub, in your own account, which you can
  push to. Cloning makes a copy on your own machine, which still pushes back to the repository it
  was cloned from, one you may have no right to push to. To change someone else's repository you
  usually do both: fork it, then clone your fork.
- **credit:** full for the difference that matters: a fork is a copy on GitHub in your own account,
  and a clone is a copy on your machine. Half for "a fork is yours and a clone isn't" with nothing
  on where each copy lives. None for an incidental difference, such as that forking is a button on
  GitHub and cloning a command.

### q-catch-fork-pushes-to-original

- **goal:** `w-fork`
- **move:** CATCH
- **answer:** A fork is the student's own copy of the showcase. What they push to it changes their
  copy only; the class's showcase is unchanged until they open a pull request from their fork into
  it and it is merged.
- **credit:** full for naming the actual error: a fork is a separate copy, so pushing to it leaves
  the original unchanged until a pull request into the original is merged. Half for "it goes into
  your copy" with nothing on how it reaches the original, or "you need a pull request" with
  nothing on the fork being a separate copy. None for a different quibble, such as that the app
  might fail the showcase's checks.
