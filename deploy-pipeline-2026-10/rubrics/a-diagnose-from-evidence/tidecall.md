Tidecall's pipeline deploys both parts from the workflow: Pinecart's repository link is off, and
Ropewalk is linked to `main` with "Auto-deploy: off". On a push to `main` the `ci` workflow runs
the tests and, only if they pass, runs Pinecart's deploy command and then calls Ropewalk's deploy
hook. So Ropewalk's list holds only the commits the hook deployed, not every push, and the workflow
runs on pushes to `main` only, so a commit pushed to another branch has no checks. Each question
has exactly one cause, and every other place in its evidence is consistent with it. True red
herrings: in q1 the failed `ci` on the older commit `2a6f0c8`, never deployed and long since
followed by passing ones; in every question a Pinecart setting saved before the Live Pinecart
deploy, which that deploy has picked up (in q1 `VITE_MEETING_POINT`, in q3 and q4 the 08:50 save,
picked up by the 08:53 deploy); in q3 the commit with no checks, which is only because it was not
pushed to `main`; and in q4 the Live Pinecart deploy of the new commit. q2 is a setting saved and
then a Rebuild (shown only as a Pinecart deploy of the same commit timed after the save), so a
changed setting in the setup does not by itself mean `old-build-setting`. The questions' dates run
in order (2, 4, 6 and 10 November) and their evidence agrees across them, but none depends on
another. Difficulty: q1 `unpushed` Easy, q2 `stale-browser` Easy, q3 `unmerged-pr` Medium, q4
`failed-deploy` Easy.

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-pushed
- **answer:** The change was committed but never pushed: `git status` says the branch is ahead of
  `origin/main` by one commit, and `5e7a2d9` is not on `main` on GitHub, so the workflow never ran
  for it and neither host deployed it. Push it (`git push`).
- **credit:** full for naming the unpushed commit as the reason, and pushing as the next step. Half
  for the right reason with the next step missing or wrong (such as committing again, or clicking
  Rebuild). None for a wrong reason, such as the failed check on `2a6f0c8` or a cache.
- **tutor note:** if they blame the failed check, ask which commit it is on and whether the
  commits after it were deployed.

### q2

- **goal:** `c-find-missing-change`
- **cases:** browser-cache
- **answer:** The setting saved at 08:50 was built into the 08:53 Pinecart deploy, which is Live,
  and a reload skipping the browser's cache shows the new line, so the browser is showing its own
  old copy. Reload without the browser's cache; nothing on the hosts needs doing.
- **credit:** full for naming the browser's own old copy as the reason, and reloading without its
  cache as the next step. Half for the right reason with the next step missing or wrong (such as
  clicking Rebuild, or clearing the CDN's cache). None for a wrong reason, such as a setting saved
  after the last build, or the CDN's cache.
- **tutor note:** if they say the frontend needs rebuilding, ask them to compare the setting's save
  time with the time of the Live Pinecart deploy.

### q3

- **goal:** `c-find-missing-change`
- **cases:** not-on-main
- **answer:** The change, `6c2d1a8`, was pushed to the branch `count-me-in` and is waiting in pull
  request #14, which nobody has merged, so it is not on `main` and the workflow never deployed it.
  Merge pull request #14 into `main`.
- **credit:** full for naming the unmerged pull request as the reason, and merging it as the next
  step. Half for the right reason with the next step missing or wrong (such as opening another pull
  request, pushing the branch again, or calling the deploy hook). None for a wrong reason, such as
  missing checks blocking the deploy, or a cache.
- **tutor note:** if they say the commit has no checks so nothing deployed it, ask which branch the
  commit is on and which branch the workflow deploys from.

### q4

- **goal:** `c-find-missing-change`
- **cases:** deploy-failed
- **answer:** The tests passed and the workflow called the deploy hook, but Ropewalk's deploy of
  `d47c2e0` Failed, so the previous backend (`1e9f7b3`) is still Live and still sends the old list
  of beaches; the frontend deployed fine. Look at Ropewalk's failed deploy of `d47c2e0` to see what
  went wrong.
- **credit:** full for naming Ropewalk's failed deploy, with the older backend still live, as the
  reason, and looking at that failed deploy as the next step (finding its cause is not asked for).
  Half for the right reason with the next step missing or wrong (such as clearing a cache, or
  pushing again unchanged). None for a wrong reason, such as failed tests or a cache.
- **tutor note:** if they look only at Pinecart's list, ask where the list of beaches comes from.
