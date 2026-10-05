Trailhead is your hiking club's trip board. Its React frontend is in the `client` folder of one
GitHub repository and its Express backend in the `server` folder. Pinecart is linked to the
repository's `main` branch and its `client` folder. Ropewalk is linked to `main` and the `server`
folder, with "Wait for GitHub checks" on, and a GitHub Actions workflow runs the frontend's and the
backend's tests on every push to `main`.

How the two hosts behave:

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

The welcome line at the top of the trip board comes from a frontend setting, `VITE_WELCOME`, on
Pinecart's Settings page. This morning, at about 8:50, you changed it from "Welcome, hikers!" to
"Fall trips are open: sign up by Friday". It is now 10:30 am, and when you open the live site the
welcome line still says "Welcome, hikers!".

### q1

Where would you look first: git's output on your machine, the commit's checks on GitHub, a host's
deploy list, or the page in the browser? You'll be shown what it shows. Keep going until you can
say why the change isn't showing and what you'd do next.
