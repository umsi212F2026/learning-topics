Shape `uncommitted` (Easy). The agent edited `client/src/pages/Home.jsx` but never committed it, so
nothing new reached GitHub, and both hosts are still serving yesterday's `5c81d2e`. The Thursday
setting is a true red herring: every Pinecart deploy listed was built after it was saved.

Evidence, to be read word for word, one place at a time, only the one asked for.

**git's output on the learner's machine**

`git status`:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   client/src/pages/Home.jsx

no changes added to commit (use "git add" and/or "git commit -a")
```

`git branch --show-current`:

```
main
```

`git log --oneline -3`:

```
5c81d2e (HEAD -> main, origin/main) Let finders attach a photo to a post
b07e93a Sort posts by the date the item was found
9f4a6c1 Add a filter for items found in the library
```

**GitHub**

- Latest commits on `main`: `5c81d2e` Let finders attach a photo to a post (yesterday 5:20 pm);
  `b07e93a` Sort posts by the date the item was found (yesterday 11:02 am); `9f4a6c1` Add a filter
  for items found in the library (Friday 3:44 pm).
- Open pull requests: none.
- Checks on `5c81d2e`, `b07e93a` and `9f4a6c1`: workflow `tests`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `5c81d2e` | yesterday 5:22 pm | Live |
| `b07e93a` | yesterday 11:04 am | Replaced |
| `9f4a6c1` | Friday 3:46 pm | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://campusfinds-api.ropewalk.example`, last saved 5 weeks ago.
- `VITE_CONTACT_EMAIL` = `finds@students.example.edu`, last saved Thursday 4:15 pm.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `5c81d2e` | yesterday 5:24 pm | Live |
| `b07e93a` | yesterday 11:06 am | Replaced |
| `9f4a6c1` | Friday 3:48 pm | Replaced |

**The page in the browser**

- Normal load: the heading says "Lost something?".
- Reload that skips the browser's cache: "Lost something?".
- Private window, or another device: "Lost something?".
- The URL with `?v=2` added: "Lost something?".

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-pushed
- **answer:** The change never left the learner's machine: `git status` shows `Home.jsx` modified
  and not committed, and the newest commit on `main`, here and on GitHub, is yesterday's
  `5c81d2e`, which both hosts are serving. Next: commit the change and push it to `main`, which
  deploys it.
- **credit:** full for the reason (the change was never committed, so it never reached GitHub)
  and the next step (commit it and push it to `main`). Half for that reason with the next step
  missing or wrong, such as committing without pushing, pushing with nothing committed, or pressing
  Pinecart's Rebuild. None for any other reason, such as a cache, a failed deploy or the Thursday
  setting.
- **tutor note:** if they stop at GitHub or the deploy lists saying "nothing new was deployed",
  ask why nothing new reached GitHub. If they say "push" alone, ask what `git status` says is
  waiting to be pushed.
