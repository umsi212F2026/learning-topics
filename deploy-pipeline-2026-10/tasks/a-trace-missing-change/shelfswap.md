Shelfswap is a used-textbook board for one campus: students list the textbooks they want to sell,
and others browse them by course code. Its React frontend is in `client/` and its Express backend
in `server/`, in one GitHub repository, and each folder has tests run by `npm test`. The frontend
is hosted on Pinecart and the backend on Ropewalk.

How it deploys: Pinecart's repository link is off. A GitHub Actions workflow runs on every push to
`main`: it runs `npm test` in `client/` and in `server/`, and once both pass, it runs Pinecart's
deploy command with the deploy token kept in the repository's GitHub secrets. Ropewalk is linked
to the repository, the `main` branch and the `server/` folder, with "Wait for GitHub checks" on.

What the two hosts do, as their docs describe them:

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
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live or
    Failed. When a deploy fails, the previous one stays live.
- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Failed, or Skipped (checks failed). When a deploy fails, the previous one stays live.

At about 3:40 this afternoon, Tuesday October 6, you changed the button on Shelfswap's home page
so that it says "List a textbook" instead of "Post a book". The change is in
`client/src/components/PostButton.jsx`. It is now 4:30, and the live app's button still says
"Post a book".

### q1

Where would you look first: git's output on your machine, the commit's checks on GitHub, a host's
deploy list, or the page in the browser? You'll be shown what it shows. Keep going until you can
say why the change isn't showing and what you'd do next.
