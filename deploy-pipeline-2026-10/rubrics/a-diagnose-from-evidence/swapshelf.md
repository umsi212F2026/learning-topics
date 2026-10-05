Swapshelf's pipeline is the sound one in roster terms: Pinecart's repository link is off and the
`test-and-deploy` workflow deploys the frontend only after the tests pass; Ropewalk is linked to
`main` with "Wait for GitHub checks" on, so it deploys a commit only once `test-and-deploy` has
passed. Every push to `main` reaches Ropewalk's list, frontend-only changes included. Each
question has exactly one cause, and every other place in its evidence is consistent with it.
True red herrings: the failed check on `a3f9c21` in q2's GitHub block (an older commit), and in
every question a Pinecart setting saved before the latest deploy, which that deploy has picked
up. The questions' dates run in order (1, 6 and 12 October) and their evidence agrees across
them, but none depends on another. Difficulty: q1 `red-check` Easy, q2 `setting-after-build`
Medium, q3 `stale-cdn` Hard (the browser block has no `?v=2`).

### q1

- **goal:** `c-find-missing-change`
- **cases:** tests-failed
- **answer:** The frontend tests failed on `a3f9c21`, so the workflow never ran Pinecart's deploy
  command (no Pinecart deploy for that commit) and Ropewalk skipped it; the live app is still
  `7be0d44`. Look at the failing frontend test, make the tests pass, and push again.
- **credit:** full for naming the failed tests as why neither host deployed the commit, and
  making the tests pass and pushing as the next step. Half for the right reason with the next step
  missing or wrong (such as clicking Rebuild, or pushing again unchanged). None for a wrong reason,
  such as a failed deploy or a cached page.
- **tutor note:** if they say the deploy failed, ask whether Pinecart's list holds any deploy of
  `a3f9c21` at all.

### q2

- **goal:** `c-find-missing-change`
- **cases:** old-build-setting
- **answer:** `VITE_BANNER_TEXT` was saved on Tuesday 6 October at 09:15, after the latest build
  (`9d2f6b8`, deployed Friday 2 October at 15:29), and a build copies settings into its files, so
  the live frontend still carries the old value. Build the frontend again: Pinecart's Rebuild
  button, or a push to `main`.
- **credit:** full for naming the setting saved after the last build as the reason, and building
  the frontend again (Rebuild, or a push) as the next step. Half for the right reason with the next
  step missing or wrong (such as clearing a cache, or waiting). None for a wrong reason, such as
  the browser's or the CDN's cache.
- **tutor note:** if they blame a cache, ask them to compare the setting's save time with the
  time of the Live Pinecart deploy.

### q3

- **goal:** `c-find-missing-change`
- **cases:** cdn-cache
- **answer:** `f08a3e5` passed its checks and its Pinecart deploy is Live, but that deploy says
  "CDN cache kept" and is under 12 hours old, and a reload skipping the browser's cache still
  shows the old button, so Pinecart's CDN is serving its old copy. Load the page with a changed
  URL, such as `https://swapshelf.pinecart.app/swap?v=2`, to see that the new button is there, then
  clear Pinecart's CDN cache (the Clear CDN cache button) so every visitor gets it.
- **credit:** full for naming the CDN's old copy as the reason, and both changing the URL (such as
  adding `?v=2`) to see the new version and clearing Pinecart's CDN cache. Half for the right
  reason with the next step missing or wrong: only one of the two steps, clearing the browser's
  cache, or waiting. None for a wrong reason, such as the browser's own cache or a failed deploy.
- **tutor note:** if they say the browser's cache, ask what the reload that skips it showed.
