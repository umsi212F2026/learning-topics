Shape `unpushed` (Easy). The agent committed the change as `e3d7a90` but never pushed it, so
GitHub's `main` ends at `41bc6f2`, the workflow never ran for the new commit, and both hosts are
serving `41bc6f2`. The failed check on `8a05e1d` is a true red herring: it is an older commit,
fixed by `41bc6f2`, and neither host deployed it.

Evidence, to be read word for word, one place at a time, only the one asked for.

**git's output on the learner's machine**

`git status`:

```
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

`git branch --show-current`:

```
main
```

`git log --oneline -3`:

```
e3d7a90 (HEAD -> main) Tag groups that meet online
41bc6f2 (origin/main) Fix the meeting-day test
8a05e1d Show each group's meeting day
```

**GitHub**

- Latest commits on `main`: `41bc6f2` Fix the meeting-day test (yesterday 11:40 am); `8a05e1d`
  Show each group's meeting day (yesterday 10:05 am); `6f2e0c8` Add course codes to group cards
  (Monday 2:30 pm).
- Open pull requests: none.
- Checks on `41bc6f2` and `6f2e0c8`: workflow `test-and-deploy`, passed.
- Checks on `8a05e1d`: workflow `test-and-deploy`, failed. Step "Run frontend tests" failed:
  `MeetingDay.test.jsx: expected "Tuesdays", received "Tuesday"`. Step "Run backend tests"
  passed. Steps "Deploy frontend to Pinecart" and "Trigger Ropewalk deploy hook" skipped.
- If asked about `e3d7a90`: GitHub has no commit `e3d7a90`.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `41bc6f2` | yesterday 11:44 am | Live |
| `6f2e0c8` | Monday 2:34 pm | Replaced |
| `0d9b3a5` | Monday 9:12 am | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://studycircle-api.ropewalk.example`, last saved 3 weeks ago.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

Auto-deploy: off.

| commit | time | status |
| ------ | ---- | ------ |
| `41bc6f2` | yesterday 11:45 am | Live |
| `6f2e0c8` | Monday 2:35 pm | Replaced |
| `0d9b3a5` | Monday 9:13 am | Replaced |

**The page in the browser**

- Normal load: no group card shows a "Meets online" tag.
- Reload that skips the browser's cache: no tag.
- Private window, or another device: no tag.
- The URL with `?v=2` added: no tag.

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-pushed
- **answer:** The change was committed but never pushed: `git status` says `main` is ahead of
  `origin/main` by one commit, and GitHub's `main` ends at `41bc6f2`, which both hosts are serving.
  Next: push `main`, and the workflow tests and deploys it.
- **credit:** full for the reason (the commit is only on the learner's machine, never pushed to
  GitHub) and the next step (push it to `main`). Half for that reason with the next step missing
  or wrong, such as pressing Pinecart's Rebuild or calling the deploy hook by hand. None for any
  other reason, such as failed tests (the failed check is on the older `8a05e1d`), a failed deploy
  or a cache.
- **tutor note:** if they settle on the failed check, ask which commit it is on and what came
  after it. If they look only at the deploy lists, ask whether GitHub has the new commit at all.
