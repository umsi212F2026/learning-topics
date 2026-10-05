Trailhead's pipeline is the gated one: the workflow deploys the frontend only after `npm test`
passes in both folders, and Ropewalk waits for GitHub checks. Each question is one shape with one
cause, and all four evidence blocks agree with it. Shapes and questions:

- q1: `red-check` (case `tests-failed`, Easy). A frontend change whose client test fails.
- q2: `setting-after-build` (case `old-build-setting`, Medium). `VITE_MEET_POINT` saved Oct 9,
  14:10; the latest Pinecart deploy is Oct 8, 17:24.
- q3: `stale-cdn` without `?v=2` in the browser block (case `cdn-cache`, Hard). Its Settings page
  shows `VITE_MEET_POINT` saved before the latest deploys, which have picked it up, so a setting on
  the page does not by itself point at q2's cause.

Red herrings, all true: older deploys in each list, and in q3 a red cross on `6b0d9c4` (Oct 12)
whose fix, `2a77e18`, passed and deployed. Finding out why a deploy or a test failed is not asked
for. The learner names the reason and the next step; naming the means (which button, which
command) is welcome, not required unless the credit line says so.

### q1

- **goal:** `c-find-missing-change`
- **cases:** tests-failed
- **answer:** The commit reached `main`, but its tests failed (`npm test` in `client/` has a
  failing test), so the workflow never ran Pinecart's deploy command and Ropewalk skipped the
  commit. The live app is still `9b3f1a4`. Next: make the tests pass (fix the code or the test the
  change broke) and push again.
- **credit:** full for the failed tests as the reason the change never deployed, and making the
  tests pass and pushing as the next step. Half for the right reason with the next step missing
  or wrong (pressing Rebuild, deploying by hand, turning "Wait for GitHub checks" off, or removing
  the test step). None for a wrong reason, such as a failed deploy, a cache, or the change not
  being pushed.
- **tutor note:** Rebuild would build `9b3f1a4` again, the commit of the latest deploy, so it
  cannot bring this change live. A learner who reads Ropewalk's Skipped row as a failed deploy has
  the wrong reason: Skipped means it never tried.

### q2

- **goal:** `c-find-missing-change`
- **cases:** old-build-setting
- **answer:** The setting was saved at Oct 9, 14:10, after the latest build (Pinecart's deploy of
  `d81e4b0` at Oct 8, 17:24). A build copies settings into the files it produces, so the live
  frontend still has `North Gate` baked in. Next: build the frontend again, with Pinecart's Rebuild
  button or a new push to `main`.
- **credit:** full for the setting having been changed after the last build, and rebuilding the
  frontend (Rebuild, or a push that deploys) as the next step. Half for the right reason with the
  next step missing or wrong (clearing the CDN's or the browser's cache, waiting, saving the
  setting again, or restarting Ropewalk). None for a wrong reason, such as the CDN or the browser
  serving an old copy, or the change not being on `main`.
- **tutor note:** the trap is reading two identical browser views and a Live deploy as a cache. The
  dates settle it: no deploy is newer than the save. If the learner says the setting belongs in
  the code or in Ropewalk, ask what the Settings page's save time and the deploy times say.

### q3

- **goal:** `c-find-missing-change`
- **cases:** cdn-cache
- **answer:** `e52a7f3` passed its checks and Pinecart deployed it at 09:13, under an hour ago,
  with "CDN cache kept", and a reload that skips the browser's cache still shows "Sign up", so
  Pinecart's CDN is serving its old copy of the page. Next: load the page with a changed address,
  such as adding `?v=2`, to see that the new version is there, then clear Pinecart's CDN cache so
  every visitor gets it.
- **credit:** full for the CDN serving an old copy, with both next steps: a changed URL such as
  `?v=2` to see the new version, and clearing Pinecart's CDN cache. Half for the right reason with
  either step missing, or with a wrong step instead (clearing the browser's cache, a private
  window, or waiting up to 12 hours). None for a wrong reason, such as the browser's own copy (the
  cache-skipping reload rules it out), a failed deploy, or the tests.
- **tutor note:** clearing the CDN by turning "Clear CDN cache on deploy" back on and then
  rebuilding or pushing also clears it, and counts as clearing. A learner who points at the red
  cross on `6b0d9c4` has taken a true red herring: it is an older commit, fixed by `2a77e18`.
