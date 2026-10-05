Each question is a different change, on a different day, with its own evidence. Answer each in
two or three sentences.

Tidecall is an app where volunteers sign up for beach cleanups. Its React frontend, in the
repository's `web` folder, is hosted on Pinecart, and its Express backend, in the `server` folder,
is hosted on Ropewalk; both come from one GitHub repository. Pinecart's repository link is off,
and Ropewalk is linked to `main` and the `server` folder with "Auto-deploy: off". On every push to
`main`, a GitHub Actions workflow runs the frontend's and the backend's tests in one check called
`ci`, and only if they pass does it run Pinecart's deploy command and then send a request to
Ropewalk's deploy hook. The Pinecart deploy token and the deploy hook's URL are kept in the
repository's GitHub secrets.

What the two hosts do:

- **Pinecart** hosts a built frontend and serves it through its CDN.
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
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced or Failed. A Live deploy shows as Replaced once a later deploy goes live, so only one
    deploy is Live at a time. When a deploy fails, the previous one stays live.
- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Its auto-deploy can be switched off ("Auto-deploy: off"); the service stays linked to its
    branch.
  - Each service has a deploy hook: a URL that deploys the latest commit on the linked branch when
    a request is sent to it, whether auto-deploy is on or off. Anyone who has the URL can trigger a deploy.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.

The live app is at `https://tidecall.pinecart.app`.

### q1

On Monday 2 November at 15:30, you had your agent change the sign-up page's heading from "Join a
cleanup" to "Pick a beach", and it committed the change. At 16:15 the live sign-up page still says
"Join a cleanup". Here is what each place shows at 16:15.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
5e7a2d9 (HEAD -> main) Change sign-up heading
c3b8f01 (origin/main) Add tide times to beach page
91d4e6a Add volunteer count
```

**GitHub**

```
Latest commits on main
  c3b8f01  Add tide times to beach page  Fri 30 Oct 12:10  ci: passed
  91d4e6a  Add volunteer count           Thu 29 Oct 09:45  ci: passed
  2a6f0c8  Add beach photos              Wed 28 Oct 14:22  ci: failed

Open pull requests: none

Checks on c3b8f01
  ci  passed
    Run backend tests        passed (26 passed)
    Run frontend tests       passed (19 passed)
    Deploy to Pinecart       passed
    Call Ropewalk deploy hook  passed
```

**The deploy lists**

```
Pinecart: deploys
  c3b8f01  Fri 30 Oct 12:14  Live
  91d4e6a  Thu 29 Oct 09:49  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 19 Oct 11:05
  VITE_MEETING_POINT    last saved Thu 29 Oct 09:20

Ropewalk: deploys
  c3b8f01  Fri 30 Oct 12:15  Live
  91d4e6a  Thu 29 Oct 09:50  Replaced
```

**The browser**

```
Normal load of https://tidecall.pinecart.app/signup
  Heading: "Join a cleanup"

Reload skipping the browser's cache
  Heading: "Join a cleanup"
```

Why isn't the change showing, and what would you do next?

### q2

On Wednesday 4 November at 08:50, you saved a new value for the setting `VITE_MEETING_POINT` on
Pinecart's Settings page, changing the line under every cleanup from "Meet at the north parking
lot" to "Meet at the boardwalk stairs". At 09:30 the live app still says "Meet at the north
parking lot". Here is what each place shows at 09:30.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
0f8b3c4 (HEAD -> main, origin/main) Add sunscreen reminder
5e7a2d9 Change sign-up heading
c3b8f01 Add tide times to beach page
```

**GitHub**

```
Latest commits on main
  0f8b3c4  Add sunscreen reminder        Tue 3 Nov 17:05   ci: passed
  5e7a2d9  Change sign-up heading        Mon 2 Nov 15:31   ci: passed
  c3b8f01  Add tide times to beach page  Fri 30 Oct 12:10  ci: passed

Open pull requests: none

Checks on 0f8b3c4
  ci  passed
    Run backend tests        passed (26 passed)
    Run frontend tests       passed (20 passed)
    Deploy to Pinecart       passed
    Call Ropewalk deploy hook  passed
```

**The deploy lists**

```
Pinecart: deploys
  0f8b3c4  Wed 4 Nov 08:53  Live
  0f8b3c4  Tue 3 Nov 17:09  Replaced
  5e7a2d9  Mon 2 Nov 16:24  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 19 Oct 11:05
  VITE_MEETING_POINT    last saved Wed 4 Nov 08:50

Ropewalk: deploys
  0f8b3c4  Tue 3 Nov 17:10  Live
  5e7a2d9  Mon 2 Nov 16:25  Replaced
```

**The browser**

```
Normal load of https://tidecall.pinecart.app
  Under each cleanup: "Meet at the north parking lot"

Reload skipping the browser's cache
  Under each cleanup: "Meet at the boardwalk stairs"
```

Why isn't the change showing, and what would you do next?

### q3

On Friday 6 November at 11:00, you had your agent change the button on each beach's card from
"Sign up" to "Count me in", and push the change. At 11:40 the live beach cards still say "Sign
up". Here is what each place shows at 11:40.

**Git's output on your machine**

```
$ git status
On branch count-me-in
Your branch is up to date with 'origin/count-me-in'.

nothing to commit, working tree clean
$ git branch --show-current
count-me-in
$ git log --oneline -3
6c2d1a8 (HEAD -> count-me-in, origin/count-me-in) Change beach card button
0f8b3c4 (origin/main, main) Add sunscreen reminder
5e7a2d9 Change sign-up heading
```

**GitHub**

```
Latest commits on main
  0f8b3c4  Add sunscreen reminder        Tue 3 Nov 17:05   ci: passed
  5e7a2d9  Change sign-up heading        Mon 2 Nov 15:31   ci: passed
  c3b8f01  Add tide times to beach page  Fri 30 Oct 12:10  ci: passed

Open pull requests
  #14  Change beach card button   count-me-in into main   opened Fri 6 Nov 11:03

Checks on 6c2d1a8
  none
```

**The deploy lists**

```
Pinecart: deploys
  0f8b3c4  Wed 4 Nov 08:53  Live
  0f8b3c4  Tue 3 Nov 17:09  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 19 Oct 11:05
  VITE_MEETING_POINT    last saved Wed 4 Nov 08:50

Ropewalk: deploys
  0f8b3c4  Tue 3 Nov 17:10  Live
  5e7a2d9  Mon 2 Nov 16:25  Replaced
```

**The browser**

```
Normal load of https://tidecall.pinecart.app
  Beach card button: "Sign up"

Reload skipping the browser's cache
  Beach card button: "Sign up"
```

Why isn't the change showing, and what would you do next?

### q4

On Tuesday 10 November at 14:00, you had your agent change the backend so that the list of beaches
it sends the page includes a new one, Gull Point, then commit and push. At 14:45 the live beach
list still shows only North Beach, Driftwood Cove and Pier Steps. Here is what each place shows at
14:45.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
d47c2e0 (HEAD -> main, origin/main) Add Gull Point beach
1e9f7b3 Merge pull request #14 from count-me-in
6c2d1a8 Change beach card button
```

**GitHub**

```
Latest commits on main
  d47c2e0  Add Gull Point beach                     Tue 10 Nov 14:02  ci: passed
  1e9f7b3  Merge pull request #14 from count-me-in  Fri 6 Nov 15:30   ci: passed
  6c2d1a8  Change beach card button                 Fri 6 Nov 11:02   no checks

Open pull requests: none

Checks on d47c2e0
  ci  passed
    Run backend tests        passed (27 passed)
    Run frontend tests       passed (20 passed)
    Deploy to Pinecart       passed
    Call Ropewalk deploy hook  passed
```

**The deploy lists**

```
Pinecart: deploys
  d47c2e0  Tue 10 Nov 14:06  Live
  1e9f7b3  Fri 6 Nov 15:34   Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 19 Oct 11:05
  VITE_MEETING_POINT    last saved Wed 4 Nov 08:50

Ropewalk: deploys
  d47c2e0  Tue 10 Nov 14:07  Failed
  1e9f7b3  Fri 6 Nov 15:35   Live
  0f8b3c4  Tue 3 Nov 17:10   Replaced
```

**The browser**

```
Normal load of https://tidecall.pinecart.app/beaches
  Beaches: North Beach, Driftwood Cove, Pier Steps

Reload skipping the browser's cache
  Beaches: North Beach, Driftwood Cove, Pier Steps
```

Why isn't the change showing, and what would you do next?
