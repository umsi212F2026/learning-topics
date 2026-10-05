The plainest shapes: three faulty accounts, one per case in case order (`entry-in-app-repo`,
`reversed-pr`, `new-pr-for-fix`), then a `sound` account written around the failing-check step.
`priya-builds` can't push to `eastgate-coders/app-wall`, so the sound route is: fork it into
`priya-builds/app-wall`, push a branch there, open a pull request whose base is
`eastgate-coders/app-wall` `main` and whose head is the fork's branch, and fix a failing check by
pushing to that same branch. `priya-builds/plant-pal` is the app's own repository and plays no
part in the route. Each account is judged on its own. q2 has a sound fork and so answers q1; q3
has a sound fork and pull request and so answers q1 and q2; q4 answers all three; hence this
order.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. Step 3 goes wrong: the entry went into Priya's app repository,
  `priya-builds/plant-pal`, which is not the app wall. The agent should have forked
  `eastgate-coders/app-wall` into her account and pushed the change to that fork,
  `priya-builds/app-wall`. Step 4 only follows from step 3.
- **credit:** full for naming step 3 and saying the change should have gone into a fork of
  `eastgate-coders/app-wall` under her account, pushed there; or for naming step 4 with a fix
  that goes back to it (the pull request should come from a fork of the app wall). Half for
  step 3 with a missing or wrong fix (such as pushing the branch to `eastgate-coders/app-wall`),
  or for step 4 with a fix that stays there (open the pull request in the app wall instead).
  None for agreeing, or for naming step 1 or 2.
- **tutor note:** if they name step 4 and say "open it in the app wall", ask which repository the
  branch would come from, and whether that repository has the app wall's files.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** No. Step 4 goes wrong: the pull request runs backwards. It should be from
  `priya-builds/app-wall` branch `add-plant-pal` into `eastgate-coders/app-wall` branch `main`
  (base the app wall's `main`, head the fork's branch).
- **credit:** full for naming step 4 and saying the pull request should run from the fork's
  `add-plant-pal` into the app wall's `main`, stated in full or as "the other way round". Half
  for step 4 with no direction given or a wrong one (such as one naming
  `priya-builds/plant-pal`). None for agreeing, or for naming step 1, 2 or 3.
- **tutor note:** if they only say step 4 "looks wrong", ask which repository should end up with
  the new entry: that one is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** No. Step 5 goes wrong: the fix went onto a new branch and into a second pull
  request. The agent should have added the `url` on the same branch, `add-plant-pal` in
  `priya-builds/app-wall`, and pushed, so the open pull request picks up the commit and
  `check-app-wall` runs again on it. Step 6 only follows from step 5.
- **credit:** full for naming step 5 and saying the fix should have been pushed to
  `add-plant-pal`, the open pull request's own branch; or for naming step 6 with a fix that goes
  back to step 5 (the fix belonged on the first pull request's branch). Half for step 5 with a
  missing or wrong fix (such as "update the pull request" with no word on how). None for
  agreeing, or for naming step 1, 2, 3 or 4.

### q4

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** Yes. Every step is sound: the fork, the branch pushed to the fork, the pull request
  from the fork's branch into the app wall's `main`, and the fix pushed to the same branch, which
  the open pull request picked up.
- **credit:** full for agreeing. None for naming any step as wrong.
