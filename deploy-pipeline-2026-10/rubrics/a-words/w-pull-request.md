# Rubric: pull request

What it names: asking, on GitHub, for one branch to be merged into another, where it can be looked
at first. Nearest confusables: merge; push. Synonyms: PR, merge request; given as an answer, either
one names the thing again and says nothing.

### q-pull-request-vs-merge

- **goal:** `w-pull-request`
- **move:** DISTINGUISH
- **answer:** A merge actually brings one branch's commits into another. A pull request is the
  request, on GitHub, for that merge to happen, where the change can be looked at and its checks
  run first. A pull request can be closed without ever being merged, and a merge can happen with
  no pull request at all.
- **credit:** full for the difference that matters: a pull request asks for the merge and holds
  the change where it can be looked at first, and the merge is what actually brings the commits
  in. Half for "a pull request comes before the merge" with nothing on one asking and the other
  doing. None for an incidental difference, such as that a pull request happens on GitHub's
  website and a merge on the command line.

### q-pull-request-vs-push

- **goal:** `w-pull-request`
- **move:** DISTINGUISH
- **answer:** A push sends commits from your machine to a branch on GitHub, and that branch
  changes straight away, with nobody asked. A pull request asks for a branch already on GitHub to
  be merged into another, and nothing changes in the other branch until someone merges it after
  looking. Pushing more commits to a branch with an open pull request updates that pull request.
- **credit:** full for the difference that matters: a push sends commits up to a branch and changes
  it at once, while a pull request asks for one branch to be merged into another and waits for
  that to be looked at and done. Half for "a push uploads and a pull request asks for review" with
  nothing on which branch each one changes. None for an incidental difference, such as that a
  pull request has a title and description.

### q-catch-pull-request-is-live

- **goal:** `w-pull-request`
- **move:** CATCH
- **answer:** Opening a pull request only asks for the fix's branch to be merged into `main`.
  Until someone merges it, `main` is unchanged, so the host, which deploys from `main`, has
  nothing new to deploy.
- **credit:** full for naming the actual error: a pull request is a request to merge, so the fix
  is not on `main`, and not deployed, until the pull request is merged. Half for "it has to be
  merged first" with nothing on `main` staying unchanged until then. None for a different quibble,
  such as that the checks might fail or that they should wait for the deploy to finish.
