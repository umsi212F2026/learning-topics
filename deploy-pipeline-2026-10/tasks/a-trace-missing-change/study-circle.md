Study Circle helps students in the same course find a study group. Its React frontend is in the
`client` folder of one GitHub repository and its Express backend in the `server` folder. Pinecart's
repository link is off, and Ropewalk is linked to the repository's `main` branch and its `server`
folder with "Auto-deploy: off". A GitHub Actions workflow runs on every push to `main`: it runs the
frontend's and the backend's tests, and if they pass, it runs Pinecart's deploy command with the
Pinecart deploy token and then sends a request to Ropewalk's deploy hook. The token and the hook's
URL are kept in the repository's GitHub secrets.

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

Yesterday, at about 4:30 pm, your agent added a "Meets online" tag to the card of every group that
meets on video, and told you it had committed the change. It is now 9:00 am, and no group card on
the live site shows the tag, not even for groups you know meet online.

### q1

Where would you look first: git's output on your machine, the commit's checks on GitHub, a host's
deploy list, or the page in the browser? You'll be shown what it shows. Keep going until you can
say why the change isn't showing and what you'd do next.
