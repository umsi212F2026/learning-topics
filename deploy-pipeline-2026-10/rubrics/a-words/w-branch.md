# Rubric: branch

What it names: a separate line of commits that can grow without changing main. Nearest
confusable: a fork.

### q-branch-vs-fork

- **goal:** `w-branch`
- **move:** DISTINGUISH
- **answer:** A branch is another line of commits inside the same repository. A fork is a whole
  separate copy of a repository, on GitHub, in your own account. So making a branch needs a
  repository you can push to, while a fork gives you a repository of your own, in which you then
  make branches.
- **credit:** full for the difference that matters: a branch lives inside one repository, and a
  fork is a new repository, a copy of the whole thing in your own account. Half for "a fork is a
  copy and a branch isn't" with nothing on a branch being inside the same repository. None for an
  incidental difference, such as that forks are for big changes and branches for small ones.

### q-catch-branch-shares-main

- **goal:** `w-branch`
- **move:** CATCH
- **answer:** A branch is a separate line of commits. Commits on `try-dark-mode` grow that branch
  and leave `main` as it was; they reach `main` only if the branch is merged into it.
- **credit:** full for naming the actual error: commits on a branch don't change `main`, which
  stays as it was until the branch is merged into it. Half for "that's not what a branch is"
  with nothing on main being left unchanged. None for a different quibble, such as the branch's
  name or that they should push it.
