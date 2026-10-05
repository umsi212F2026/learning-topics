`sam-tinkers` can't push to `hillcrest-webdev/class-apps`, so the entry goes into a fork,
`sam-tinkers/class-apps`, and reaches the original through a pull request whose base is
`hillcrest-webdev/class-apps` `main` and whose head is the fork's branch.
`sam-tinkers/habit-hop` is the app's own repository and plays no part in the route. q1 proposes
pushing a branch to the original, which fails for want of access; q2 reports a pull request that
runs the right way, to agree with; q3 is the open form, with a misspelled field. q2 names the
fork, which gives q1's answer away, so q1 comes first.

### q1

- **goal:** `c-showcase-pr`
- **cases:** where-to-push
- **answer:** No. I can't push to `hillcrest-webdev/class-apps`, so a branch there won't push.
  Fork it into `sam-tinkers`, have the agent add the entry to `apps.json` there (on a branch, or
  on `main`), and push to that fork.
- **credit:** full for turning the proposal down and putting the change in their own copy of the
  class list (a fork under their account), pushed there, on a branch or not. Half for turning it
  down and saying only "a new branch" with no repository named, or for turning it down with no
  place given. None for going along with it, or for their app's repository
  (`sam-tinkers/habit-hop`).
- **tutor note:** if they agree, ask whether they can push to `hillcrest-webdev/class-apps` at
  all.

### q2

- **goal:** `c-showcase-pr`
- **cases:** pr-direction
- **answer:** Yes. The base is the original, `hillcrest-webdev/class-apps` branch `main`, and the
  head is my fork's branch, `sam-tinkers/class-apps` branch `add-habit-hop`, so the change flows
  from the fork into the class list.
- **credit:** full for going along with it. None for calling it wrong, for reversing it, or for
  putting their app's repository anywhere.
- **tutor note:** if they want it reversed, ask which repository should end up with the new
  entry: that one is the base.

### q3

- **goal:** `c-showcase-pr`
- **cases:** failing-check
- **answer:** Have the agent rename `studnet` to `student` in the Habit Hop entry on the same
  branch, `add-habit-hop` in `sam-tinkers/class-apps`, and push. The open pull request picks up
  the new commit and `verify-apps` runs again.
- **credit:** full for fixing the entry on the same branch of their fork and pushing it there.
  Half for "update the pull request" with no word on how. None for opening a new pull request,
  closing this one, or pushing the fix anywhere else.
- **tutor note:** if they say "update the pull request", ask what they would push, and to where.
