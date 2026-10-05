Recipe Box lets the members of your cooking club save and share recipes. Its React frontend is in
the `client` folder of one GitHub repository and its Express backend in the `server` folder. A
GitHub Actions workflow runs on every push to `main`: it runs the frontend's and the backend's
tests, and if they pass, it runs Pinecart's deploy command with the Pinecart deploy token, which
is kept in the repository's GitHub secrets. Pinecart's repository link is off. Ropewalk is linked
to the repository's `main` branch and its `server` folder, with "Wait for GitHub checks" on.

How the two hosts behave:

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
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.

Two weeks ago you changed the club name shown in the page header, on Pinecart's Settings page.
Today, at about 1:45 pm, your agent made the photo on each recipe's page twice as large, and told
you the change was committed and pushed to GitHub. It is now 3:30 pm, and the photos on the live
site are still the old, small size.

### q1

Where would you look first: git's output on your machine, the commit's checks on GitHub, a host's
deploy list, or the page in the browser? You'll be shown what it shows. Keep going until you can
say why the change isn't showing and what you'd do next.
