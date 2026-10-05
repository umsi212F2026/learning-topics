Plotshare's pipeline differs from Swapshelf's: Pinecart is linked to `main` and deploys every push
there on its own, and Ropewalk is linked to `main` with "Wait for GitHub checks" on. The `tests`
workflow runs on every push to any branch but deploys nothing. Every push to `main` reaches both
hosts' lists; a push to another branch reaches neither. Each question has exactly one cause, and
every other place in its evidence is consistent with it. True red herrings: in every question a
Pinecart setting saved before the Live Pinecart deploy, which that deploy has picked up (in q1
`VITE_SEASON_BANNER`, in q3 the 09:10 save, picked up by the 10:31 deploy); and in q3 the older
Failed Pinecart deploy at 09:12, already followed by a Live one. q2 and q4 are a setting saved and
then a Rebuild (shown only as a Pinecart deploy of the same commit timed after the save), so a
changed setting in the setup does not by itself mean `old-build-setting`. The questions' dates run
in order (14, 20, 22 and 27 October) and their evidence agrees across them, but none depends on
another. Difficulty: q1 `uncommitted` Easy, q2 `failed-deploy` Easy, q3 `other-branch` Medium, q4
`stale-cdn` Medium (the browser block shows `?v=2`).

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-pushed
- **answer:** `git status` shows `PlotRequestForm.jsx` modified and not committed: the change is
  only on your machine, so neither GitHub nor either host has it (the latest commit, `0c94af7`, is
  live on both). Commit the change and push it to `main`.
- **credit:** full for naming the uncommitted change as why it isn't live, and committing and
  pushing as the next step. Half for the right reason with the next step missing or wrong (such as
  pushing without committing, or clicking Rebuild). None for a wrong reason, such as a cache or a
  failed deploy.
- **tutor note:** if they say the change was pushed, ask what `git status` lists under "Changes not
  staged for commit".

### q2

- **goal:** `c-find-missing-change`
- **cases:** deploy-failed
- **answer:** After the setting was saved at 09:10, Pinecart built `8e2b5d1` again at 09:12 with
  the new value, and that deploy Failed, so the previous build of `8e2b5d1` (Friday 16 October,
  16:42, with the old banner) is still Live. Look at the failed 09:12 deploy to see what went
  wrong.
- **credit:** full for naming the failed deploy, with the older one still live, as the reason, and
  looking at that failed deploy as the next step (finding its cause is not asked for). Half for
  the right reason with the next step missing or wrong (such as clearing a cache, or waiting).
  None for a wrong reason, such as a setting saved after the last build with no build since, or a
  cache.
- **tutor note:** if they say the frontend was never built after the save, ask what the 09:12 line
  in Pinecart's deploy list is.

### q3

- **goal:** `c-find-missing-change`
- **cases:** not-on-main
- **answer:** The commit `4b9d0e7` was pushed to the branch `footer-text`, not to `main`, so
  neither host, both linked to `main`, deployed it; `main` on GitHub still ends at `8e2b5d1`. Get
  it onto `main`: open a pull request from `footer-text` into `main` and merge it (or merge the
  branch into `main` and push).
- **credit:** full for naming the push to another branch as the reason, and getting the commit
  onto `main` (merging the branch, through a pull request or directly, and pushing) as the next
  step. Half for the right reason with the next step missing or wrong (such as pushing
  `footer-text` again, or clicking Rebuild). None for a wrong reason, such as a failed deploy or a
  cache.
- **tutor note:** if they point at the Failed Pinecart deploy, ask which commit it built and what
  is Live now.

### q4

- **goal:** `c-find-missing-change`
- **cases:** cdn-cache
- **answer:** The setting saved at 10:40 was built into the 10:43 deploy, which is Live, but that
  deploy says "CDN cache kept" and is under an hour old, and a reload skipping the browser's cache
  still shows the old banner while `?v=2` shows the new one, so Pinecart's CDN is serving its old
  copy. Clear Pinecart's CDN cache (the Clear CDN cache button) so every visitor gets the new
  banner.
- **credit:** full for naming the CDN's old copy as the reason, and clearing Pinecart's CDN cache
  as the next step (the browser block already shows the changed URL, so proposing it again is not
  needed). Half for the right reason with the next step missing or wrong (such as clearing the
  browser's cache, clicking Rebuild, or waiting). None for a wrong reason, such as the browser's
  own cache, or a setting saved after the last build.
- **tutor note:** if they say the setting needs a rebuild, ask them to compare the setting's save
  time with the time of the Live Pinecart deploy, and what `?v=2` showed.
