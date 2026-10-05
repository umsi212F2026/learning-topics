Shapes `new-unrelated-repo` and `reversed-pr`, then a `sound` account written around the
where-to-push step. `tomas-ships` can't push to `harborview-makers/arcade`, so the sound route is:
fork it into `tomas-ships/arcade`, push a branch there, open a pull request whose base is
`harborview-makers/arcade` `main` and whose head is the fork's branch, and fix a failing check by
pushing to that same branch. `tomas-ships/bus-buddy` is the app's own repository and plays no part
in the route, and `tomas-ships/arcade-entry` in q1 is a new repository with no tie to the arcade.
Each account is judged on its own. q2 has a sound fork and so answers q1; q3 has a sound fork and
pull request and so answers q1 and q2; hence this order.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. Step 3 goes wrong: the agent made a brand-new repository,
  `tomas-ships/arcade-entry`, which is not a copy of the arcade, and pushed the entry there. It
  should have forked `harborview-makers/arcade` into Tomas's account, as `tomas-ships/arcade`, and
  pushed a branch with the entry to that fork, ready for a pull request into the arcade.
- **credit:** full for naming step 3 and saying the change should have gone into a fork of
  `harborview-makers/arcade` under his account, pushed there. Half for step 3 with a missing or
  wrong fix (such as pushing to `harborview-makers/arcade` directly, or to
  `tomas-ships/bus-buddy`). None for agreeing, or for naming step 1 or 2.
- **tutor note:** if they agree, ask what `tomas-ships/arcade-entry` has in common with the arcade
  besides a file name.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** No. Step 4 goes wrong: base and head are swapped, so the pull request asks to merge
  the arcade's `main` into Tomas's branch. The base should be `harborview-makers/arcade` branch
  `main` and the head `tomas-ships/arcade` branch `bus-buddy-entry`.
- **credit:** full for naming step 4 and saying the base should be the arcade's `main` and the head
  the fork's `bus-buddy-entry`, stated in full or as "the other way round". Half for step 4 with no
  direction given or a wrong one (such as one naming `tomas-ships/bus-buddy`). None for agreeing,
  or for naming step 1, 2 or 3.
- **tutor note:** if they only say step 4 "looks off", ask which repository should end up with the
  new entry: that one is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** Yes. Every step is sound: the change was made on a branch of the fork,
  `tomas-ships/arcade`, and pushed there, not to the arcade or to `tomas-ships/bus-buddy`; the pull
  request runs from the fork's branch into the arcade's `main`; and the fix was pushed to the same
  branch, which the open pull request picked up.
- **credit:** full for agreeing. None for naming any step as wrong.
- **tutor note:** a learner who calls step 3's check of `origin` unnecessary has not named a wrong
  step; ask whether the push itself went to the right place.
