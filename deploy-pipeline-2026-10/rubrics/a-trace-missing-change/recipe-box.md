Shape `other-branch` (Medium). The agent committed the change on a new branch, `bigger-photos`,
and pushed that branch, so the commit is on GitHub but not on `main`. The workflow runs only on
pushes to `main`, so no check ran on it, and neither host deployed it; both are serving
Tuesday's `93ac5d2`. The setting saved two weeks ago is a true red herring: every Pinecart deploy
listed was built after it.

Evidence, to be read word for word, one place at a time, only the one asked for.

**git's output on the learner's machine**

`git status`:

```
On branch bigger-photos
Your branch is up to date with 'origin/bigger-photos'.

nothing to commit, working tree clean
```

`git branch --show-current`:

```
bigger-photos
```

`git log --oneline -3`:

```
b4e1f07 (HEAD -> bigger-photos, origin/bigger-photos) Make recipe photos twice as large
93ac5d2 (origin/main, main) Add a cooking-time filter
7e20b6a Let members rate a recipe
```

**GitHub**

- Latest commits on `main`: `93ac5d2` Add a cooking-time filter (Tuesday 6:10 pm); `7e20b6a` Let
  members rate a recipe (Tuesday 2:25 pm); `15d8e3c` Add ingredient lists to the print view
  (Monday 11:50 am).
- Branches: `main` (default); `bigger-photos`, updated today 1:52 pm, 1 commit ahead of `main`.
- Open pull requests: none.
- Checks on `93ac5d2`, `7e20b6a` and `15d8e3c`: workflow `test-and-deploy`, passed.
- Checks on `b4e1f07`: none.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `93ac5d2` | Tuesday 6:14 pm | Live |
| `7e20b6a` | Tuesday 2:29 pm | Replaced |
| `15d8e3c` | Monday 11:54 am | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://recipebox-api.ropewalk.example`, last saved 2 months ago.
- `VITE_CLUB_NAME` = `Second Helpings`, last saved 2 weeks ago.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `93ac5d2` | Tuesday 6:13 pm | Live |
| `7e20b6a` | Tuesday 2:28 pm | Replaced |
| `15d8e3c` | Monday 11:53 am | Replaced |

**The page in the browser**

- Normal load: the recipe photos are the old, small size.
- Reload that skips the browser's cache: small photos.
- Private window, or another device: small photos.
- The URL with `?v=2` added: small photos.

### q1

- **goal:** `c-find-missing-change`
- **cases:** not-on-main
- **answer:** The change was pushed to the branch `bigger-photos`, not to `main`: `git status`
  and `git branch --show-current` say so, and on GitHub `bigger-photos` is one commit ahead of
  `main`. The pipeline deploys only `main`, so nothing ran. Next: get the commit onto `main`,
  through a pull request from `bigger-photos` into `main` that gets merged (or by merging the
  branch into `main` and pushing `main`).
- **credit:** full for the reason (the commit is on GitHub but on another branch, not on `main`)
  and the next step (merge it into `main`, through a pull request or by merging and pushing).
  Half for that reason with the next step missing or wrong, such as pushing `bigger-photos` again,
  pressing Pinecart's Rebuild, or linking Ropewalk to `bigger-photos`. None for any other reason,
  such as the change not being pushed, failed tests or a cache.
- **tutor note:** if they say "it wasn't pushed", ask what `origin/bigger-photos` in the log
  means. If they say "the checks never ran" and stop, ask why no workflow ran on `b4e1f07`.
