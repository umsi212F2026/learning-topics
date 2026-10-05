The plainest form of each step: one open question per case, in route order. `mara-codes` can't
push to `northfield-cs/showcase`, so the change goes into a fork, `mara-codes/showcase`, and
reaches the original through a pull request whose base is `northfield-cs/showcase` `main` and
whose head is the fork's branch. `mara-codes/study-buddy` is the app's own repository and plays
no part in the route. q2 and q3 name where the change went, so a learner who skipped q1 can
still answer them; that gives q1's answer away, which is why q1 comes first.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** In a copy of the showcase under my own account: fork `northfield-cs/showcase` into
  `mara-codes`, have the agent add `apps/study-buddy.json` there (on a branch, or on `main`), and
  push to that fork.
- **credit:** full for making the change in their own copy of the showcase (a fork under their
  account) and pushing it there, on a branch or not. Half for "a new branch" with no repository
  named. None for the original (`northfield-cs/showcase`) or for their app's repository
  (`mara-codes/study-buddy`).
- **tutor note:** if they say "a new branch", ask which repository the branch is in and whether
  they can push to it.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** Base: `northfield-cs/showcase`, branch `main`. Head: `mara-codes/showcase`, branch
  `add-study-buddy`.
- **credit:** full for base the original repository and its `main`, and head their fork and the
  branch with the change. None for the pair reversed, or for their app's repository anywhere.
- **tutor note:** if they reverse it, ask which repository should end up with the new entry: that
  one is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** Have the agent add the missing `url` field to `apps/study-buddy.json` on the same
  branch, `add-study-buddy` in `mara-codes/showcase`, and push. The open pull request picks up
  the new commit and `validate-entries` runs again.
- **credit:** full for fixing the entry on the same branch of their fork and pushing it there.
  Half for "update the pull request" with no word on how. None for opening a new pull request,
  closing this one, or pushing the fix anywhere else.
- **tutor note:** if they say "update the pull request", ask what they would push, and to where.
