The gallery is a single list, `apps.json`, rather than a file per app. `theo-makes` can't push to
`riverside-hack-club/gallery`, so the entry goes into a fork, `theo-makes/gallery`, and reaches the
original through a pull request whose base is `riverside-hack-club/gallery` `main` and whose head
is the fork's branch. `theo-makes/recipe-box` is the app's own repository and plays no part in the
route. Every proposal here is faulty: q1 puts the entry in the app's repository, and q3 closes the
pull request to start again. q2 names the fork, which gives q1's answer away, so q1 comes first.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. The entry belongs in the gallery's `apps.json`, not in my app's repository, and I
  can't push to the gallery itself. Fork `riverside-hack-club/gallery` into `theo-makes`, have the
  agent add the entry to `apps.json` there (on a branch, or on `main`), and push to that fork.
- **credit:** full for turning the proposal down and putting the change in their own copy of the
  gallery (a fork under their account), pushed there, on a branch or not. Half for turning it
  down and saying only "a new branch" with no repository named, or for turning it down with no
  place given. None for going along with it, or for the original (`riverside-hack-club/gallery`)
  as the place to push.
- **tutor note:** if they say "a new branch", ask which repository the branch is in and whether
  they can push to it.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. 1 is reversed; 3 takes the head from the fork's `main`, which
  lacks the entry, since it was pushed to `add-recipe-box`; 4 runs inside the fork, so the gallery never gets the entry.
- **tutor note:** if they choose 1, ask which repository should end up with the new entry: that
  one is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** No. Have the agent fix the `link` in the Recipe Box entry on the same branch,
  `add-recipe-box` in `theo-makes/gallery`, and push. The open pull request picks up the new
  commit and `lint-gallery` runs again; there is no need for a fresh one.
- **credit:** full for turning the proposal down and fixing the entry on the same branch of their
  fork and pushing it there. Half for turning it down and saying only "update the pull request"
  with no word on how. None for going along with it, for any other new pull request, or for
  pushing the fix anywhere else.
- **tutor note:** if they agree, ask what happens to the open pull request when a new commit is
  pushed to its branch.
