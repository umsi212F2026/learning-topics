`kofi-builds` can't push to `westbrook-devs/demo-shelf`, so the entry goes into a fork,
`kofi-builds/demo-shelf`, and reaches the original through a pull request whose base is
`westbrook-devs/demo-shelf` `main` and whose head is the fork's branch. `kofi-builds/bus-times` is
the app's own repository and plays no part in the route. q1 and q3 are sound proposals to agree
with; q2 is a reversed pull request. A pass on q1 or q3 comes from agreeing, so on its own it is
thin evidence for its case (see `c-showcase-pr`'s note in `goals.md`). q3 names the right
direction, which gives q2's answer away, so q2 comes before it.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** Yes. I can't push to `westbrook-devs/demo-shelf`, so a fork under my account,
  `kofi-builds/demo-shelf`, with the entry on a branch pushed there, is where it should go.
- **credit:** full for going along with it. None for turning it down in favour of the original
  (`westbrook-devs/demo-shelf`) or the app's repository (`kofi-builds/bus-times`). Turning it down
  only to push to the fork's `main` instead of a branch is still the fork, and is full.
- **tutor note:** if they turn it down, ask whether they can push to `westbrook-devs/demo-shelf`,
  and where else a copy of it could live.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** No, it is the wrong way round. The base should be `westbrook-devs/demo-shelf`
  branch `main` and the head `kofi-builds/demo-shelf` branch `add-bus-times`, so the change flows
  from the fork into the original.
- **credit:** full for saying it is wrong and giving base the original repository and its
  `main`, head their fork and the branch with the change; "swap base and head" names that pair
  and counts. None for going along with it, or for their app's repository anywhere.
- **tutor note:** if they agree, ask which repository should end up with the new entry: that one
  is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** Yes. Fixing `apps/bus-times.json` on `add-bus-times` in `kofi-builds/demo-shelf` and
  pushing adds the commit to the open pull request, and `entry-check` runs again on it.
- **credit:** full for going along with it. None for turning it down in favour of a new pull
  request, closing this one, or pushing the fix anywhere else.
- **tutor note:** if they want a new pull request, ask what happens to the open one when a new
  commit is pushed to its branch.
