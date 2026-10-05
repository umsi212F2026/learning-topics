Trailhead is a hiking club's trip sign-up sheet, shaped like your Problem Set 3 app: a React
frontend in `client/` and an Express backend in `server/`, in one GitHub repository, each folder
with tests run by `npm test`. The frontend is on Pinecart and the backend on Ropewalk, two
made-up hosts.

How it deploys: Pinecart's repository link is off. On every push to `main`, a GitHub Actions
workflow with one job, `test-and-deploy`, runs `npm test` in `client/` and in `server/`, and if
both pass, runs Pinecart's deploy command with the deploy token kept in the repository's GitHub
secrets. Ropewalk is linked to the repository's `main` branch and its `server/` folder, with
"Wait for GitHub checks" on.

What the two hosts do, as their docs say:

**Pinecart** hosts a built frontend and serves it through its CDN.

- Its repository link can be switched off. A deploy then happens only when Pinecart's deploy
  command runs with a Pinecart deploy token, for example as a step in a GitHub Actions workflow.
  Anyone who holds the token can deploy to the site. The deploy command builds the frontend on
  Pinecart from the pushed commit, using the site's settings, then deploys it.
- Frontend settings are entered on the site's Settings page, which shows when each setting was
  last saved. A build copies their values into the files it produces, which every visitor's
  browser downloads, so a setting changed after a build has no effect until the next build. The
  Rebuild button builds the commit of the site's latest deploy again, using the current
  settings, and deploys it, whether the repository link is on or off.
- Its CDN keeps a copy of each page for up to 12 hours. The setting "Clear CDN cache on deploy"
  is on for a new site; with it off, a deploy leaves the CDN's copies in place, and the deploy
  list says "CDN cache kept" beside that deploy. The Clear CDN cache button clears it at any time.
  A request for a page whose address differs, even only after a `?`, is fetched fresh from the
  latest deploy.
- Its deploy list shows each deploy with its commit, its time and its status: Building, Live or
  Failed. When a deploy fails, the previous one stays live.

**Ropewalk** runs a long-running backend, such as an Express server.

- Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
  that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
  commit only once every check on that commit has passed, and skip the commit if one fails. A
  commit with no checks on it is deployed straight away, as if the setting were off.
- Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
  Failed, or Skipped (checks failed). When a deploy fails, the previous one stays live.

The frontend has two settings on Pinecart's Settings page: `VITE_API_URL`, the backend's address,
and `VITE_MEET_POINT`, the meeting place the home page shows after "Meet at".

Each question below is a different change, on a different day, with what git, GitHub, the two
hosts and the browser showed at the time. Deploy lists are newest first. Answer each in two or
three sentences.

### q1

On Tuesday, October 6, you added a line to the sign-up form that says how many places are left on
the trip ("12 places left"). You committed it and pushed it at 16:40. At 17:15 the live sign-up
form still has no such line.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

$ git branch --show-current
main

$ git log --oneline -3
c7d2e10 (HEAD -> main, origin/main) Show places left on sign-up form
9b3f1a4 Sort trips by date
5e8d2c7 Add trip leader's name to trip page
```

**GitHub**

- Latest commits on `main`: `c7d2e10` Show places left on sign-up form (Oct 6, 16:40), red cross;
  `9b3f1a4` Sort trips by date (Oct 5, 10:58), green check.
- Open pull requests: none.
- Checks on `c7d2e10`: `test-and-deploy` failed.
  - Run `npm test` in `client/`: failed, 1 failed, 23 passed.
  - Run `npm test` in `server/`: not run.
  - Deploy frontend to Pinecart: not run.

**Deploy lists**

Pinecart:

| commit | time | status |
| ------ | ---- | ------ |
| `9b3f1a4` | Oct 5, 11:02 | Live |
| `5e8d2c7` | Oct 3, 19:31 | Live |

Pinecart's Settings page:

| setting | last saved |
| ------- | ---------- |
| `VITE_API_URL` | Sep 14, 10:20 |
| `VITE_MEET_POINT` | Sep 30, 18:05 |

Ropewalk:

| commit | time | status |
| ------ | ---- | ------ |
| `c7d2e10` | Oct 6, 16:44 | Skipped (checks failed) |
| `9b3f1a4` | Oct 5, 11:03 | Live |
| `5e8d2c7` | Oct 3, 19:32 | Live |

**Browser**

- Normal load of the sign-up form: no "places left" line.
- Reload that skips the browser's cache: no "places left" line.

Why isn't the change showing, and what would you do next?

### q2

On Friday, October 9, the club moved its meeting place. At 14:10 you changed `VITE_MEET_POINT` on
Pinecart's Settings page from `North Gate` to `Boathouse` and saved it. At 15:00 the live home
page still says "Meet at North Gate".

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

$ git branch --show-current
main

$ git log --oneline -3
d81e4b0 (HEAD -> main, origin/main) Fix typo in footer
3fa90c1 Add packing list to trip page
c7d2e10 Show places left on sign-up form
```

**GitHub**

- Latest commits on `main`: `d81e4b0` Fix typo in footer (Oct 8, 17:20), green check;
  `3fa90c1` Add packing list to trip page (Oct 7, 12:45), green check.
- Open pull requests: none.
- Checks on `d81e4b0`: `test-and-deploy` passed.

**Deploy lists**

Pinecart:

| commit | time | status |
| ------ | ---- | ------ |
| `d81e4b0` | Oct 8, 17:24 | Live |
| `3fa90c1` | Oct 7, 12:49 | Live |

Pinecart's Settings page:

| setting | last saved |
| ------- | ---------- |
| `VITE_API_URL` | Sep 14, 10:20 |
| `VITE_MEET_POINT` | Oct 9, 14:10 |

Ropewalk:

| commit | time | status |
| ------ | ---- | ------ |
| `d81e4b0` | Oct 8, 17:25 | Live |
| `3fa90c1` | Oct 7, 12:50 | Live |

**Browser**

- Normal load of the home page: "Meet at North Gate".
- Reload that skips the browser's cache: "Meet at North Gate".

Why isn't the change showing, and what would you do next?

### q3

On Tuesday, October 13, you changed the sign-up button's text from "Sign up" to "Count me in".
You committed it and pushed it at 09:10. At 10:05 the live sign-up button still says "Sign up".

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

$ git branch --show-current
main

$ git log --oneline -3
e52a7f3 (HEAD -> main, origin/main) Change sign-up button text
2a77e18 Fix date test
6b0d9c4 Add trip dates to trip list
```

**GitHub**

- Latest commits on `main`: `e52a7f3` Change sign-up button text (Oct 13, 09:10), green check;
  `2a77e18` Fix date test (Oct 12, 15:48), green check; `6b0d9c4` Add trip dates to trip list
  (Oct 12, 15:20), red cross.
- Open pull requests: none.
- Checks on `e52a7f3`: `test-and-deploy` passed.

**Deploy lists**

Pinecart:

| commit | time | status |
| ------ | ---- | ------ |
| `e52a7f3` | Oct 13, 09:13 | Live, CDN cache kept |
| `2a77e18` | Oct 12, 15:51 | Live, CDN cache kept |

Pinecart's Settings page:

| setting | last saved |
| ------- | ---------- |
| `VITE_API_URL` | Sep 14, 10:20 |
| `VITE_MEET_POINT` | Oct 9, 14:10 |

Ropewalk:

| commit | time | status |
| ------ | ---- | ------ |
| `e52a7f3` | Oct 13, 09:14 | Live |
| `2a77e18` | Oct 12, 15:52 | Live |
| `6b0d9c4` | Oct 12, 15:24 | Skipped (checks failed) |

**Browser**

- Normal load of the sign-up form: the button says "Sign up".
- Reload that skips the browser's cache: the button says "Sign up".

Why isn't the change showing, and what would you do next?
