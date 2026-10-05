Shape `setting-after-build` (Medium). `VITE_NOTICE` was saved yesterday at 5:02 pm, and the
latest Pinecart deploy, the Live one, was built yesterday at 11:24 am, before the save. Nothing
has been pushed or rebuilt since, so the live frontend still carries the old notice in every
view. Git, GitHub and Ropewalk show nothing amiss.

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
d58c0a3 (HEAD -> main, origin/main) Show the minutes left on each machine
9b27e61 Add the second-floor laundry room
40f7ad8 Remember which hall you picked
```

**GitHub**

- Latest commits on `main`: `d58c0a3` Show the minutes left on each machine (yesterday 11:20 am);
  `9b27e61` Add the second-floor laundry room (Monday 4:45 pm); `40f7ad8` Remember which hall you
  picked (Monday 9:30 am).
- Open pull requests: none.
- Checks on `d58c0a3`, `9b27e61` and `40f7ad8`: workflow `test-and-deploy`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `d58c0a3` | yesterday 11:24 am | Live |
| `9b27e61` | Monday 4:49 pm | Replaced |
| `40f7ad8` | Monday 9:34 am | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://spincycle-api.ropewalk.example`, last saved 3 weeks ago.
- `VITE_NOTICE` = `All machines are working`, last saved yesterday 5:02 pm.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

Auto-deploy: off.

| commit | time | status |
| ------ | ---- | ------ |
| `d58c0a3` | yesterday 11:25 am | Live |
| `9b27e61` | Monday 4:50 pm | Replaced |
| `40f7ad8` | Monday 9:35 am | Replaced |

**The page in the browser**

- Normal load: the notice says "Dryer 3 is out of order".
- Reload that skips the browser's cache: "Dryer 3 is out of order".
- Private window, or another device: "Dryer 3 is out of order".
- The URL with `?v=2` added: "Dryer 3 is out of order".

### q1

- **goal:** `c-find-missing-change`
- **cases:** old-build-setting
- **answer:** `VITE_NOTICE` was saved yesterday at 5:02 pm, after the Live Pinecart deploy was
  built at 11:24 am, and nothing has been built since. A build copies settings into its files, so
  the live frontend still has the old notice. Next: build the frontend again, with Pinecart's
  Rebuild button or a push to `main`.
- **credit:** full for the reason (the setting was saved after the last build, so the live build
  still carries the old value) and the next step (build the frontend again: Rebuild, or a push).
  Half for that reason with the next step missing or wrong, such as clearing a cache, waiting,
  saving the setting again, or calling Ropewalk's deploy hook. None for any other reason, such as
  the browser's or the CDN's copy, or a failed deploy.
- **tutor note:** if they blame a cache, ask them to compare the setting's save time with the
  time of the Live Pinecart deploy.
