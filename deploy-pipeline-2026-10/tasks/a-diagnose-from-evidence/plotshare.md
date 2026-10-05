Each question is a different change, on a different day, with its own evidence. Answer each in
two or three sentences.

Plotshare is a community garden's app for requesting a plot and signing up for workdays. Its
React frontend, in the repository's `client` folder, is hosted on Pinecart, and its Express
backend, in the `api` folder, is hosted on Ropewalk; both come from one GitHub repository.
Pinecart is linked to `main` and the `client` folder. Ropewalk is linked to `main` and the `api`
folder, with "Wait for GitHub checks" on. A GitHub Actions workflow runs the frontend's and the
backend's tests on every push, to any branch, as a check called `tests`; it deploys nothing.

What the two hosts do:

- **Pinecart** hosts a built frontend and serves it through its CDN.
  - Linked to a GitHub repository, a branch and a folder, it builds and deploys the frontend on
    every push to that branch. It cannot wait for GitHub checks.
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
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.

The live app is at `https://plotshare.pinecart.app`.

### q1

On Wednesday 14 October at 14:05, your agent changed the button on the plot request form from
"Request a plot" to "Claim a plot" and told you it was done. At 14:40 the live form's button still
says "Request a plot". Here is what each place shows at 14:40.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   client/src/components/PlotRequestForm.jsx

no changes added to commit (use "git add" and/or "git commit -a")
$ git branch --show-current
main
$ git log --oneline -3
0c94af7 (HEAD -> main, origin/main) Show waiting list count
6d1e0b2 Add plot size to plot list
3a7f115 Add plot map
```

**GitHub**

```
Latest commits on main
  0c94af7  Show waiting list count       Tue 13 Oct 16:02  tests: passed
  6d1e0b2  Add plot size to plot list    Mon 12 Oct 11:20  tests: passed
  3a7f115  Add plot map                  Fri 9 Oct 15:48   tests: passed

Open pull requests: none

Checks on 0c94af7
  tests  passed
    Run backend tests     passed (18 passed)
    Run frontend tests    passed (22 passed)
```

**The deploy lists**

```
Pinecart: deploys
  0c94af7  Tue 13 Oct 16:04  Live
  6d1e0b2  Mon 12 Oct 11:22  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Tue 29 Sep 10:30
  VITE_SEASON_BANNER    last saved Mon 12 Oct 09:00

Ropewalk: deploys
  0c94af7  Tue 13 Oct 16:06  Live
  6d1e0b2  Mon 12 Oct 11:24  Replaced
```

**The browser**

```
Normal load of https://plotshare.pinecart.app/request
  Button: "Request a plot"

Reload skipping the browser's cache
  Button: "Request a plot"
```

Why isn't the change showing, and what would you do next?

### q2

On Tuesday 20 October at 09:10, you saved a new value for the setting `VITE_SEASON_BANNER` on
Pinecart's Settings page, changing the banner across the top of every page from "Autumn workday:
Saturday 24 October" to "Autumn workday: Sunday 25 October". At 09:45 the live app's banner
still says "Autumn workday: Saturday 24 October". Here is what each place shows at 09:45.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
8e2b5d1 (HEAD -> main, origin/main) Fix plot map legend
2f60c3e Rename plot request button
0c94af7 Show waiting list count
```

**GitHub**

```
Latest commits on main
  8e2b5d1  Fix plot map legend           Fri 16 Oct 16:40  tests: passed
  2f60c3e  Rename plot request button    Thu 15 Oct 10:02  tests: passed
  0c94af7  Show waiting list count       Tue 13 Oct 16:02  tests: passed

Open pull requests: none

Checks on 8e2b5d1
  tests  passed
    Run backend tests     passed (18 passed)
    Run frontend tests    passed (23 passed)
```

**The deploy lists**

```
Pinecart: deploys
  8e2b5d1  Tue 20 Oct 09:12  Failed
  8e2b5d1  Fri 16 Oct 16:42  Live
  2f60c3e  Thu 15 Oct 10:04  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Tue 29 Sep 10:30
  VITE_SEASON_BANNER    last saved Tue 20 Oct 09:10

Ropewalk: deploys
  8e2b5d1  Fri 16 Oct 16:44  Live
  2f60c3e  Thu 15 Oct 10:05  Replaced
```

**The browser**

```
Normal load of https://plotshare.pinecart.app
  Banner: "Autumn workday: Saturday 24 October"

Reload skipping the browser's cache
  Banner: "Autumn workday: Saturday 24 October"
```

Why isn't the change showing, and what would you do next?

### q3

On Thursday 22 October at 13:20, you had your agent change the line at the foot of every page from
"Questions? Email the garden committee" to "Questions? Ask at the tool shed", then commit and push
it. At 14:00 the live app's footer still says "Questions? Email the garden committee". Here is
what each place shows at 14:00.

**Git's output on your machine**

```
$ git status
On branch footer-text
Your branch is up to date with 'origin/footer-text'.

nothing to commit, working tree clean
$ git branch --show-current
footer-text
$ git log --oneline -3
4b9d0e7 (HEAD -> footer-text, origin/footer-text) Change footer text
8e2b5d1 (origin/main, main) Fix plot map legend
2f60c3e Rename plot request button
```

**GitHub**

```
Latest commits on main
  8e2b5d1  Fix plot map legend           Fri 16 Oct 16:40  tests: passed
  2f60c3e  Rename plot request button    Thu 15 Oct 10:02  tests: passed
  0c94af7  Show waiting list count       Tue 13 Oct 16:02  tests: passed

Open pull requests: none

Checks on 4b9d0e7 (branch footer-text)
  tests  passed
    Run backend tests     passed (18 passed)
    Run frontend tests    passed (23 passed)
```

**The deploy lists**

```
Pinecart: deploys
  8e2b5d1  Tue 20 Oct 10:31  Live
  8e2b5d1  Tue 20 Oct 09:12  Failed
  8e2b5d1  Fri 16 Oct 16:42  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Tue 29 Sep 10:30
  VITE_SEASON_BANNER    last saved Tue 20 Oct 09:10

Ropewalk: deploys
  8e2b5d1  Fri 16 Oct 16:44  Live
  2f60c3e  Thu 15 Oct 10:05  Replaced
```

**The browser**

```
Normal load of https://plotshare.pinecart.app
  Footer: "Questions? Email the garden committee"

Reload skipping the browser's cache
  Footer: "Questions? Email the garden committee"
```

Why isn't the change showing, and what would you do next?

### q4

On Tuesday 27 October at 10:40, you saved a new value for the setting `VITE_SEASON_BANNER` on
Pinecart's Settings page, changing the banner from "Autumn workday: Sunday 25 October" to "Bulb
planting: Saturday 7 November". At 11:30 the live app's banner still says "Autumn workday: Sunday
25 October". Here is what each place shows at 11:30.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
7a3c5f9 (HEAD -> main, origin/main) Merge pull request #9 from footer-text
4b9d0e7 Change footer text
8e2b5d1 Fix plot map legend
```

**GitHub**

```
Latest commits on main
  7a3c5f9  Merge pull request #9 from footer-text  Fri 23 Oct 15:00  tests: passed
  4b9d0e7  Change footer text                      Thu 22 Oct 13:21  tests: passed
  8e2b5d1  Fix plot map legend                     Fri 16 Oct 16:40  tests: passed

Open pull requests: none

Checks on 7a3c5f9
  tests  passed
    Run backend tests     passed (18 passed)
    Run frontend tests    passed (23 passed)
```

**The deploy lists**

```
Pinecart: deploys
  7a3c5f9  Tue 27 Oct 10:43  Live      CDN cache kept
  7a3c5f9  Fri 23 Oct 15:02  Replaced  CDN cache kept

Pinecart: Settings
  VITE_API_URL          last saved Tue 29 Sep 10:30
  VITE_SEASON_BANNER    last saved Tue 27 Oct 10:40

Ropewalk: deploys
  7a3c5f9  Fri 23 Oct 15:04  Live
  8e2b5d1  Fri 16 Oct 16:44  Replaced
```

**The browser**

```
Normal load of https://plotshare.pinecart.app
  Banner: "Autumn workday: Sunday 25 October"

Reload skipping the browser's cache
  Banner: "Autumn workday: Sunday 25 October"

Load of https://plotshare.pinecart.app/?v=2
  Banner: "Bulb planting: Saturday 7 November"
```

Why isn't the change showing, and what would you do next?
