Each question is a different change, on a different day, with its own evidence. Answer each in
two or three sentences.

Swapshelf is a neighborhood book-swap app. Its React frontend, in the repository's `frontend`
folder, is hosted on Pinecart, and its Express backend, in the `backend` folder, is hosted on
Ropewalk; both come from one GitHub repository. Pinecart's repository link is off: on every push
to `main`, a GitHub Actions workflow runs the frontend's and the backend's tests in one check
called `test-and-deploy`, and only if they pass does it run Pinecart's deploy command, with the
deploy token kept in the repository's GitHub secrets. Ropewalk is linked to `main` and the
`backend` folder, with "Wait for GitHub checks" on.

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
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). A Live deploy shows as Replaced once a later
    deploy goes live, so only one deploy is Live at a time. When a deploy fails, the previous one
    stays live.

The live app is at `https://swapshelf.pinecart.app`.

### q1

On Thursday 1 October at 10:15, you had your agent change the home page's heading from "Welcome
to Swapshelf" to "Swap a book, take a book", then committed and pushed. At 11:30 the live home
page still says "Welcome to Swapshelf". Here is what each place shows at 11:30.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
a3f9c21 (HEAD -> main, origin/main) Change home heading
7be0d44 Add due date to swap form
51c2e8a Show book covers in list
```

**GitHub**

```
Latest commits on main
  a3f9c21  Change home heading           Thu 1 Oct 10:16   test-and-deploy: failed
  7be0d44  Add due date to swap form     Wed 30 Sep 17:38  test-and-deploy: passed
  51c2e8a  Show book covers in list      Wed 30 Sep 11:01  test-and-deploy: passed

Open pull requests: none

Checks on a3f9c21
  test-and-deploy  failed
    Run backend tests     passed (31 passed)
    Run frontend tests    failed (1 failed, 23 passed)
    Deploy to Pinecart    skipped
```

**The deploy lists**

```
Pinecart: deploys
  7be0d44  Wed 30 Sep 17:41  Live
  51c2e8a  Wed 30 Sep 11:04  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 14 Sep 10:12
  VITE_SUPPORT_EMAIL    last saved Tue 22 Sep 09:30
  VITE_BANNER_TEXT      last saved Mon 28 Sep 18:05

Ropewalk: deploys
  a3f9c21  Thu 1 Oct 10:19   Skipped (checks failed)
  7be0d44  Wed 30 Sep 17:42  Live
  51c2e8a  Wed 30 Sep 11:05  Replaced
```

**The browser**

```
Normal load of https://swapshelf.pinecart.app
  Heading: "Welcome to Swapshelf"

Reload skipping the browser's cache
  Heading: "Welcome to Swapshelf"
```

Why isn't the change showing, and what would you do next?

### q2

On Tuesday 6 October at 09:15, you saved a new value for the setting `VITE_BANNER_TEXT` on
Pinecart's Settings page, changing the banner across the top of every page from "Swap night is
Thursday at 7" to "Swap night is Friday at 6". At 10:00 the live app's banner still says "Swap
night is Thursday at 7". Here is what each place shows at 10:00.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
9d2f6b8 (HEAD -> main, origin/main) Add search by author
4e81a07 Fix date format on swap list
a3f9c21 Change home heading
```

**GitHub**

```
Latest commits on main
  9d2f6b8  Add search by author          Fri 2 Oct 15:24   test-and-deploy: passed
  4e81a07  Fix date format on swap list  Fri 2 Oct 11:50   test-and-deploy: passed
  a3f9c21  Change home heading           Thu 1 Oct 10:16   test-and-deploy: failed

Open pull requests: none

Checks on 9d2f6b8
  test-and-deploy  passed
    Run backend tests     passed (31 passed)
    Run frontend tests    passed (25 passed)
    Deploy to Pinecart    passed
```

**The deploy lists**

```
Pinecart: deploys
  9d2f6b8  Fri 2 Oct 15:29  Live
  4e81a07  Fri 2 Oct 11:55  Replaced

Pinecart: Settings
  VITE_API_URL          last saved Mon 14 Sep 10:12
  VITE_SUPPORT_EMAIL    last saved Tue 22 Sep 09:30
  VITE_BANNER_TEXT      last saved Tue 6 Oct 09:15

Ropewalk: deploys
  9d2f6b8  Fri 2 Oct 15:30  Live
  4e81a07  Fri 2 Oct 11:56  Replaced
```

**The browser**

```
Normal load of https://swapshelf.pinecart.app
  Banner: "Swap night is Thursday at 7"

Reload skipping the browser's cache
  Banner: "Swap night is Thursday at 7"
```

Why isn't the change showing, and what would you do next?

### q3

On Monday 12 October at 09:35, you had your agent change the button on the swap form from "Add
book" to "Offer this book", then committed and pushed. At 11:15 the live swap form's button still
says "Add book". Here is what each place shows at 11:15.

**Git's output on your machine**

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
$ git branch --show-current
main
$ git log --oneline -3
f08a3e5 (HEAD -> main, origin/main) Rename add-book button
2b71c90 Add book condition field
9d2f6b8 Add search by author
```

**GitHub**

```
Latest commits on main
  f08a3e5  Rename add-book button        Mon 12 Oct 09:37  test-and-deploy: passed
  2b71c90  Add book condition field      Fri 9 Oct 16:14   test-and-deploy: passed
  9d2f6b8  Add search by author          Fri 2 Oct 15:24   test-and-deploy: passed

Open pull requests: none

Checks on f08a3e5
  test-and-deploy  passed
    Run backend tests     passed (33 passed)
    Run frontend tests    passed (27 passed)
    Deploy to Pinecart    passed
```

**The deploy lists**

```
Pinecart: deploys
  f08a3e5  Mon 12 Oct 09:42  Live      CDN cache kept
  2b71c90  Fri 9 Oct 16:19   Replaced  CDN cache kept

Pinecart: Settings
  VITE_API_URL          last saved Mon 14 Sep 10:12
  VITE_SUPPORT_EMAIL    last saved Tue 22 Sep 09:30
  VITE_BANNER_TEXT      last saved Tue 6 Oct 09:15

Ropewalk: deploys
  f08a3e5  Mon 12 Oct 09:43  Live
  2b71c90  Fri 9 Oct 16:20   Replaced
```

**The browser**

```
Normal load of https://swapshelf.pinecart.app/swap
  Button: "Add book"

Reload skipping the browser's cache
  Button: "Add book"
```

Why isn't the change showing, and what would you do next?
