# Rubric: branch protection

What it names: GitHub rules that stop anyone pushing straight to a branch such as main. Nearest
confusable: a private repository. Synonym: ruleset; given as an answer, it names the thing again
and says nothing.

### q-branch-protection-vs-private

- **goal:** `w-branch-protection`
- **move:** DISTINGUISH
- **answer:** Making a repository private decides who can see it at all. Branch protection decides
  how changes may reach one branch: nobody pushes straight to `main`, so changes come in through a
  pull request, often only once its checks pass. A public repository can have branch protection,
  and in a private one with no protection every collaborator can push straight to `main`.
- **credit:** full for the difference that matters: privacy is about who can see the repository,
  and branch protection is about how changes may reach a branch, stopping pushes straight to it.
  Half for "branch protection is about one branch and privacy about the whole repository" with
  nothing on seeing versus changing. None for an incidental difference, such as that one is in a
  different part of GitHub's settings.

### q-catch-protection-hides-code

- **goal:** `w-branch-protection`
- **move:** CATCH
- **answer:** Branch protection says nothing about who can read the repository. It stops pushes
  straight to `main`; whether outsiders can read the code depends on whether the repository is
  public or private.
- **credit:** full for naming the actual error: branch protection controls how changes reach
  `main`, not who can see the code, which is what making the repository private does. Half for
  "that's what private is for" with nothing on what branch protection does instead. None for a
  different quibble, such as that outsiders can't push anyway.
