Shape `stale-browser` (Medium), with the change a Pinecart setting followed by a Rebuild. The
setting was saved at 8:51 am, and a Rebuild of `1e8b4f3` at 8:53 am built it with the new welcome
line and went Live, clearing the CDN's cache as it did. The learner's own browser is showing its
old copy: any view that doesn't use that copy shows the new line. Nothing new was pushed, so git,
GitHub and Ropewalk show nothing amiss.

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
1e8b4f3 (HEAD -> main, origin/main) Show each trip's distance in miles
c94d27a Add a waitlist when a trip is full
6a0f5e9 Let trip leaders cancel a trip
```

**GitHub**

- Latest commits on `main`: `1e8b4f3` Show each trip's distance in miles (yesterday 7:10 pm);
  `c94d27a` Add a waitlist when a trip is full (yesterday 1:30 pm); `6a0f5e9` Let trip leaders
  cancel a trip (Sunday 5:05 pm).
- Open pull requests: none.
- Checks on `1e8b4f3`, `c94d27a` and `6a0f5e9`: workflow `tests`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `1e8b4f3` | today 8:53 am | Live |
| `1e8b4f3` | yesterday 7:12 pm | Replaced |
| `c94d27a` | yesterday 1:32 pm | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://trailhead-api.ropewalk.example`, last saved 4 weeks ago.
- `VITE_WELCOME` = `Fall trips are open: sign up by Friday`, last saved today 8:51 am.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `1e8b4f3` | yesterday 7:14 pm | Live |
| `c94d27a` | yesterday 1:34 pm | Replaced |
| `6a0f5e9` | Sunday 5:08 pm | Replaced |

**The page in the browser**

- Normal load: the welcome line says "Welcome, hikers!".
- Reload that skips the browser's cache: "Fall trips are open: sign up by Friday".
- Private window, or another device: "Fall trips are open: sign up by Friday".
- The URL with `?v=2` added: "Fall trips are open: sign up by Friday".

### q1

- **goal:** `c-find-missing-change`
- **cases:** browser-cache
- **answer:** The new setting is live: Pinecart's Live deploy, at 8:53 am, was built after the
  8:51 am save, with "Clear CDN cache on deploy" on. A reload that skips the browser's cache (or a
  private window, another device, or `?v=2`) shows the new line, so the learner's browser is
  showing its own old copy. Next: reload without the browser's cache.
- **credit:** full for the reason (the learner's browser is showing its own old copy of the page)
  and the next step (reload without the browser's cache). Half for that reason with the next step
  missing or wrong, such as pressing Rebuild or clearing Pinecart's CDN cache. None for any other
  reason, such as the setting saved after the last build, the CDN's copy, or a failed deploy.
- **tutor note:** if they say the setting needs a rebuild, ask them to compare the save time with
  the time of the Live Pinecart deploy. If they say the CDN, ask what "Clear CDN cache on deploy"
  is set to and what a reload skipping the browser's cache shows.
