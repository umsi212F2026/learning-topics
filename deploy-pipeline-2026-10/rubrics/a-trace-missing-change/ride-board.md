Shape `unmerged-pr` (Medium). The agent put the change on a branch, `offer-a-seat`, pushed it and
opened pull request #14 into `main`. The pull request's tests passed, but nobody has merged it, so
the commit is not on `main`, the workflow's deploy steps never ran for it, and both hosts are
serving Monday's `c6a20d9`. The learner's machine is back on `main`, so git's output shows nothing
amiss.

Evidence, to be read word for word, one place at a time, only the one asked for.

**git's output on the learner's machine**

`git status`:

```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

`git branch --show-current`:

```
main
```

`git log --oneline -3`:

```
c6a20d9 (HEAD -> main, origin/main) Show the departure town on each ride
58f1b3e Let drivers edit a ride
d90e47a Add a sign-in page
```

**GitHub**

- Latest commits on `main`: `c6a20d9` Show the departure town on each ride (Monday 3:15 pm);
  `58f1b3e` Let drivers edit a ride (Monday 10:20 am); `d90e47a` Add a sign-in page (last Friday
  2:05 pm).
- Open pull requests: #14 "Change the Offer a ride button to Offer a seat", from `offer-a-seat`
  into `main`, opened yesterday 4:06 pm from your account, one commit, `7a3f52b`. "All checks
  have passed." "This branch has no conflicts with the base branch." Not merged; no reviews or
  comments.
- Checks on `7a3f52b`: workflow `test-and-deploy`, passed. Steps "Run frontend tests" and "Run
  backend tests" passed. Steps "Deploy frontend to Pinecart" and "Trigger Ropewalk deploy hook"
  skipped.
- Checks on `c6a20d9`, `58f1b3e` and `d90e47a`: workflow `test-and-deploy`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `c6a20d9` | Monday 3:19 pm | Live |
| `58f1b3e` | Monday 10:24 am | Replaced |
| `d90e47a` | last Friday 2:09 pm | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://rideboard-api.ropewalk.example`, last saved 3 weeks ago.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

Auto-deploy: off.

| commit | time | status |
| ------ | ---- | ------ |
| `c6a20d9` | Monday 3:20 pm | Live |
| `58f1b3e` | Monday 10:25 am | Replaced |
| `d90e47a` | last Friday 2:10 pm | Replaced |

**The page in the browser**

- Normal load: the button says "Offer a ride".
- Reload that skips the browser's cache: "Offer a ride".
- Private window, or another device: "Offer a ride".
- The URL with `?v=2` added: "Offer a ride".

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-on-main
- **answer:** The change is waiting in pull request #14, from `offer-a-seat` into `main`, which
  nobody has merged, so it never reached `main` and the workflow never deployed it. Its passing
  checks only ran the tests. Next: merge the pull request (after looking it over), and the push to
  `main` tests and deploys it.
- **credit:** full for the reason (the change is in an open pull request that hasn't been merged,
  so it isn't on `main`) and the next step (merge the pull request). Half for that reason with the
  next step missing or wrong, such as opening another pull request, re-running the checks,
  pressing Pinecart's Rebuild or calling the deploy hook by hand. None for any other reason, such
  as the change not being pushed, failed tests or a cache.
- **tutor note:** if they stop at git's output saying everything is pushed, ask where the agent
  might have put the commit if not on `main`. If they read the passing checks as "deployed", ask
  what the two skipped steps mean.
