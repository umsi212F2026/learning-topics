Shapes `new-unrelated-repo` (ending at the wrong step, with no pull request) and
`fix-on-wrong-branch`, then a `sound` account written around the pull-request step. `june-makes`
can't push to `cedar-hall-cs/demo-day`, so the sound route is: fork it into
`june-makes/demo-day`, push a branch there, open a pull request whose base is
`cedar-hall-cs/demo-day` `main` and whose head is the fork's branch, and fix a failing check by
pushing to that same branch. `june-makes/recipe-roulette` is the app's own repository and plays no
part in the route, and `june-makes/demo-day-entry` in q1 is a new repository with no tie to the
demo day list. Each account is judged on its own. q2 has a sound fork and so answers q1; q3 has a
sound fork and a fix pushed to the pull request's own branch, and so answers q1 and q2; hence this
order.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. Step 3 goes wrong: the agent made a brand-new repository,
  `june-makes/demo-day-entry`, which is not a copy of the demo day list, and pushed the entry
  there. It should have forked `cedar-hall-cs/demo-day` into June's account, as
  `june-makes/demo-day`, and pushed a branch with the entry to that fork, ready for a pull request
  into the original.
- **credit:** full for naming step 3 and saying the change should have gone into a fork of
  `cedar-hall-cs/demo-day` under her account, pushed there. Half for step 3 with a missing or wrong
  fix (such as pushing to `cedar-hall-cs/demo-day` directly, adding the file to
  `june-makes/recipe-roulette`, or "now open a pull request from `june-makes/demo-day-entry`").
  None for agreeing, or for naming step 1 or 2.
- **tutor note:** a learner who says "nothing is wrong yet, it just hasn't opened the pull request"
  has agreed; ask where that pull request would come from and what it would hold.

### q2

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** No. Step 5 goes wrong: the fix went to `main` in the fork, but the pull request comes
  from `add-recipe-roulette`, so it never sees the fix and `check-entries` still fails. The agent
  should have added the `url` on `add-recipe-roulette` in `june-makes/demo-day` and pushed there,
  so the open pull request picks up the commit and the check runs again.
- **credit:** full for naming step 5 and saying the fix should have been pushed to
  `add-recipe-roulette`, the pull request's own branch. Half for step 5 with a missing or wrong fix
  (such as opening a new pull request from the fork's `main`, or "update the pull request" with no
  word on how). None for agreeing, or for naming step 1, 2, 3 or 4. Saying that step 2's entry
  was missing its `url`, alongside naming step 5, is true and harmless: neither credited nor
  counted against them, and not naming a sound step as wrong.
- **tutor note:** if they agree, ask which branch the pull request in step 3 comes from, and which
  branch step 5 pushed to.

### q3

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** Yes. Every step is sound: the fork, the branch pushed to the fork, the pull request
  with base `cedar-hall-cs/demo-day` `main` and head `june-makes/demo-day` `add-recipe-roulette`,
  and the fix pushed to the same branch, which the open pull request picked up.
- **credit:** full for agreeing. None for naming any step as wrong. Saying that step 2's entry
  was missing its `url` while agreeing to the route is true and harmless: neither credited nor
  counted against them, and not naming a step as wrong.
- **tutor note:** a learner who calls step 3 backwards has swapped base and head; ask which
  repository the base names and which should end up with the new entry.
