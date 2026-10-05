Shape `failed-deploy` (Easy), with the change a Pinecart setting followed by a Rebuild. The
setting was saved at 9:31 am, and a Rebuild of `f2a6c18` started at 9:34 am, after the save, so it
was built with the new notice; but that deploy failed, so yesterday's deploy of the same commit,
built with the old notice, is still Live. Nothing new was pushed, so git, GitHub and Ropewalk show
nothing amiss. A learner who reads only the Live deploy's time against the save time will take
this for `setting-after-build`; the Failed deploy above it is what rules that out.

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
f2a6c18 (HEAD -> main, origin/main) List the items in stock by shelf
3b97e05 Add the pantry's phone number to the footer
a8d40c2 Show a notice when the pantry is closed for a holiday
```

**GitHub**

- Latest commits on `main`: `f2a6c18` List the items in stock by shelf (yesterday 2:40 pm);
  `3b97e05` Add the pantry's phone number to the footer (Monday 11:15 am); `a8d40c2` Show a notice
  when the pantry is closed for a holiday (last Thursday 4:50 pm).
- Open pull requests: none.
- Checks on `f2a6c18`, `3b97e05` and `a8d40c2`: workflow `test-and-deploy`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `f2a6c18` | today 9:34 am | Failed |
| `f2a6c18` | yesterday 2:44 pm | Live |
| `3b97e05` | Monday 11:19 am | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://pantryhours-api.ropewalk.example`, last saved 6 weeks ago.
- `VITE_HOURS_NOTICE` = `Open Mon to Fri, 10 am to 4 pm`, last saved today 9:31 am.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `f2a6c18` | yesterday 2:43 pm | Live |
| `3b97e05` | Monday 11:18 am | Replaced |
| `a8d40c2` | last Thursday 4:54 pm | Replaced |

**The page in the browser**

- Normal load: the notice says "Open Mon to Thu, 10 am to 4 pm".
- Reload that skips the browser's cache: "Open Mon to Thu, 10 am to 4 pm".
- Private window, or another device: "Open Mon to Thu, 10 am to 4 pm".
- The URL with `?v=2` added: "Open Mon to Thu, 10 am to 4 pm".

### q1

- **goal:** `c-find-missing-change`
- **cases:** deploy-failed
- **answer:** A Pinecart deploy of `f2a6c18` at 9:34 am, after the setting was saved at 9:31 am,
  failed, so the previous deploy, yesterday's, built with the old notice, is still Live. Next:
  open that failed deploy on Pinecart and look at what it shows about why it failed, before
  building again.
- **credit:** full for the reason (the deploy that would carry the new setting failed, and the old
  version is still live) and the next step (look at the failed deploy). Finding why it failed is
  not asked for. Half for that reason with the next step missing or wrong, such as pressing
  Rebuild again without looking at the failure, clearing a cache, or pushing an empty commit. None
  for any other reason, including "the setting was saved after the last build, so rebuild", which
  misses the deploy that did build it and failed.
- **tutor note:** if they compare the save time only with the Live deploy and say "rebuild", ask
  what the 9:34 am deploy is and what its status says.
