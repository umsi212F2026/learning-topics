Priya can't push to `lakeside-coders/demo-day`, so the entry belongs on a branch of a fork under
her account (`priya-builds/demo-day`), pushed there; the pull request runs from that branch into
the showcase's `main`; and a failing check is fixed by pushing to the pull request's own branch.
Her app repository, `priya-builds/trail-log`, has no part in it. q1 to q3 each have one wrong step;
q4 has none. The accounts are in this order because a later one shows a sound step that an
earlier one gets wrong (q2 shows the fork q1 lacks; q3 and q4 show the direction q2 reverses).

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. Step 3 goes wrong: the entry was added to her own app repository. The agent
  should have forked `lakeside-coders/demo-day` into her account and added the entry on a branch
  of that fork, pushed there. Step 4 only follows from step 3.
- **credit:** full for naming step 3 and saying the entry should go in her own fork (copy) of the
  showcase, pushed there; naming step 4 counts as full when the fix goes back to where the change
  was made (it should come from a fork of the showcase), and half when the fix stays with step 4
  (open the pull request into the showcase instead). Half for step 3 with a missing or wrong fix.
  None for going along with it, or for naming step 1 or 2.
- **tutor note:** an answer that says "it should have pushed to `lakeside-coders/demo-day`" is a
  wrong fix: she can't push there.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** No. Step 4 goes wrong: the pull request runs backwards. The base should be
  `lakeside-coders/demo-day`, branch `main`, and the head `priya-builds/demo-day`, branch
  `add-trail-log`.
- **credit:** full for naming step 4 and giving the base as the showcase's `main` and the head as
  the fork's `add-trail-log` (saying "swap them" is enough). Half for step 4 with a missing or
  wrong fix. None for going along with it, or for naming step 1, 2 or 3.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** No. Step 5 goes wrong: the fix went into a second pull request. The agent should
  have added the `url` field on `trail-log-entry` and pushed it to her fork, so the open pull
  request picks up the commit and `check-entry` runs again.
- **credit:** full for naming step 5 and saying the fix goes on `trail-log-entry`, the open pull
  request's own branch, pushed to the fork. Half for step 5 with a missing or wrong fix, such as
  "update the first pull request" with no word on how. None for going along with it, or for naming
  any of steps 1 to 4.
- **tutor note:** step 4 is a failure, not a wrong step; a learner who names it has mistaken what
  happened for what was done.

### q4

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** Yes. Every step is sound: fork, branch, push to the fork, a pull request from the
  fork's `add-trail-log` into the showcase's `main`, and the fix pushed to the same branch.
- **credit:** full for going along with it. None for naming any step as wrong.
