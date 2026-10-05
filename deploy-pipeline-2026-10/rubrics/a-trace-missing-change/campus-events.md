Shape `stale-cdn` (Hard). `7c35e19` is on `main`, its checks passed, and its Pinecart deploy is
Live, but "Clear CDN cache on deploy" was switched off yesterday evening, so that deploy, about
an hour old, says "CDN cache kept" and the CDN is still serving its copy of the old page. Every
view that goes through that copy shows the old button; only a changed URL is fetched fresh. Two
true red herrings: the failed check on Tuesday's `e0b1c67`, which Pinecart deployed anyway (it
cannot wait for checks) and Ropewalk skipped, both long since replaced; and last week's date
setting, saved before every deploy listed.

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
7c35e19 (HEAD -> main, origin/main) Rename the Add an event button to Post an event
2f9da84 Show events on a campus map
e0b1c67 Group events by day
```

**GitHub**

- Latest commits on `main`: `7c35e19` Rename the Add an event button to Post an event (today
  8:15 am); `2f9da84` Show events on a campus map (yesterday 3:25 pm); `e0b1c67` Group events by
  day (Tuesday 10:40 am).
- Open pull requests: none.
- Checks on `7c35e19` and `2f9da84`: workflow `tests`, passed.
- Checks on `e0b1c67`: workflow `tests`, failed. Step "Run frontend tests" passed. Step "Run
  backend tests" failed: `events.test.js: expected 7 days, received 6`.

**Pinecart's deploy list**

| commit | time | status | |
| ------ | ---- | ------ | - |
| `7c35e19` | today 8:17 am | Live | CDN cache kept |
| `2f9da84` | yesterday 3:27 pm | Replaced | |
| `e0b1c67` | Tuesday 10:42 am | Replaced | |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://campusevents-api.ropewalk.example`, last saved 2 months ago.
- `VITE_DATE_FORMAT` = `weekday-day-month`, last saved last Wednesday 2:20 pm.
- Clear CDN cache on deploy: off, last saved yesterday 6:05 pm.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `7c35e19` | today 8:18 am | Live |
| `2f9da84` | yesterday 3:28 pm | Replaced |
| `e0b1c67` | Tuesday 10:43 am | Skipped (checks failed) |

**The page in the browser**

- Normal load: the button says "Add an event".
- Reload that skips the browser's cache: "Add an event".
- Private window, or another device: "Add an event".
- The URL with `?v=2` added: "Post an event".

### q1

- **goal:** `c-find-missing-change`
- **cases:** cdn-cache
- **answer:** `7c35e19` passed its checks and its Pinecart deploy is Live, but it says "CDN cache
  kept" and is about an hour old, under the CDN's 12 hours; a reload skipping the browser's cache
  and another device both still show "Add an event", while `?v=2` shows "Post an event". So
  Pinecart's CDN is serving its old copy. Next: confirm the new version with a changed URL such as
  `?v=2` (asked for during the trace, or named now), and press Clear CDN cache so every visitor
  gets it. Turning "Clear CDN cache on deploy" back on is welcome, not required.
- **credit:** full for the reason (Pinecart's CDN is serving an old copy) and both parts of the
  next step: seeing the new version through a changed URL such as `?v=2`, whether asked for during
  the trace or named in the answer, and clearing Pinecart's CDN cache. Half for that reason with
  the next step missing or wrong: only one of the two parts, clearing the browser's cache, or
  waiting for the copy to expire. None for any other reason, such as the browser's own cache, the
  failed check on `e0b1c67`, or the date setting.
- **tutor note:** if they say the browser's cache, ask what the reload that skips it and another
  device showed. If they settle on the failed check, ask which commit it is on and what both hosts
  did with the commits after it.
