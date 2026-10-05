Rollcall is a club sign-up sheet. Students browse the clubs' upcoming meetings, sign up for one,
and see a map of where it meets. It lives in one GitHub repository: a React frontend in `client/`
and an Express backend in `server/`, each folder with tests run by `npm test`. Its database is on
a database host outside this plan.

- The backend reads the database's connection string, as `DATABASE_URL`, and the maps service's
  key, as `MAPS_API_KEY`.
- The frontend reads the backend's address, as `VITE_API_URL`.
- Secrets: the database's connection string and the maps service's key.

The frontend is hosted on Pinecart and the backend on Ropewalk. This is what those two hosts do:

- **Pinecart** hosts a built frontend and serves it through its CDN.
  - Linked to a GitHub repository, a branch and a folder, it builds and deploys the frontend on
    every push to that branch. It cannot wait for GitHub checks.
  - Its repository link can be switched off. A deploy then happens only when Pinecart's deploy
    command runs with a Pinecart deploy token, for example as a step in a GitHub Actions workflow.
    Anyone who holds the token can deploy to the site. The deploy command builds the frontend on
    Pinecart from the pushed commit, using the site's settings, then deploys it.
  - Frontend settings are entered on the site's Settings page, which shows when each setting was
    last saved. A build copies their values into the files it produces, which every visitor's
    browser downloads, so a setting changed after a build has no effect until the next build. The
    Rebuild button builds the commit of the site's latest deploy again, using the current
    settings, and deploys it, whether the repository link is on or off.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live or
    Failed. When a deploy fails, the previous one stays live.
- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Its auto-deploy can be switched off ("Auto-deploy: off"); the service stays linked to its
    branch.
  - Each service has a deploy hook: a URL that deploys the latest commit on the linked branch when
    a request is sent to it, whether auto-deploy is on or off. Anyone who has the URL can trigger a deploy.
  - Settings (environment variables) entered on the service's Settings page reach the running
    server and never the browser. Saving one restarts the server with the new value.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Failed, or Skipped (checks failed). When a deploy fails, the previous one stays live.

You asked an agent to make Rollcall's frontend and backend deploy themselves whenever `main` is
pushed to GitHub. It proposed each plan below in a different session, so each question is about
its own plan alone. Answer each question in two or three sentences.

### q1

Plan 1:

1. I'll link Ropewalk to the repository, branch `main`, folder `server/`, and turn on "Wait for
   GitHub checks".
2. I'll put `DATABASE_URL` and `MAPS_API_KEY` on Ropewalk's Settings page.
3. In `server/db.js` I'll write the database's connection string in as the fallback for
   `DATABASE_URL`, so the server still starts if the setting is missing.
4. I'll switch off Pinecart's repository link and add a GitHub Actions workflow that, on every
   push to `main`, runs `npm test` in `client/` and in `server/`, and once both pass, runs
   Pinecart's deploy command with the Pinecart deploy token.
5. On Pinecart's Settings page I'll set `VITE_API_URL` to the backend's address on Ropewalk.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q2

Plan 2:

1. I'll switch off Pinecart's repository link and add a GitHub Actions workflow that, on every
   push to `main`, runs `npm test` in `client/` and in `server/`, and once both pass, runs
   Pinecart's deploy command with the Pinecart deploy token.
2. I'll link Ropewalk to the repository, branch `main`, folder `server/`, and turn on "Wait for
   GitHub checks".
3. I'll put `DATABASE_URL` on Ropewalk's Settings page, and in a `server/.env` file for running
   the server on your machine. The `.gitignore` will list `node_modules` and `.env`.
4. On Pinecart's Settings page I'll set `VITE_API_URL` to the backend's address, and
   `VITE_MAPS_KEY` to the maps service's key, so the meeting map can call the maps service
   straight from the browser without a round trip through the server.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q3

Plan 3:

1. I'll link Pinecart to the repository, branch `main`, folder `client/`, so the frontend deploys
   on every push.
2. I'll link Ropewalk to the repository, branch `main`, folder `server/`, and turn on "Wait for
   GitHub checks".
3. I'll add a GitHub Actions workflow that runs `npm test` in `client/` and in `server/` on every
   push to `main`, and CI will check every push.
4. `DATABASE_URL` and `MAPS_API_KEY` go on Ropewalk's Settings page, and `VITE_API_URL`, the
   backend's address, on Pinecart's.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q4

Plan 4:

1. I'll link Ropewalk to the repository, branch `main`, folder `server/`, and turn on "Wait for
   GitHub checks".
2. I'll put `DATABASE_URL` and `MAPS_API_KEY` on Ropewalk's Settings page, and in a `server/.env`
   file for running the server on your machine. The `.gitignore` will list `node_modules` and
   `.env`.
3. On Pinecart's Settings page I'll set `VITE_API_URL` to the backend's address on Ropewalk.
4. I'll switch off Pinecart's repository link and add a GitHub Actions workflow that, on every
   push to `main`, runs `npm test` in `client/` and in `server/`, and once both pass, runs
   Pinecart's deploy command with the Pinecart deploy token.

Then the agent writes: "I need a Pinecart deploy token for the workflow. Where should I keep it?"

What would you tell the agent?

### q5

Plan 5:

1. I'll switch off Pinecart's repository link.
2. I'll add a GitHub Actions workflow that, on every push to `main`, runs `npm test` in `client/`
   and in `server/`, and once both pass, runs Pinecart's deploy command. The workflow reads the
   Pinecart deploy token from the repository's GitHub secrets, where I'll store it as
   `PINECART_TOKEN`.
3. I'll link Ropewalk to the repository, branch `main`, folder `server/`, and turn on "Wait for
   GitHub checks".
4. `DATABASE_URL` and `MAPS_API_KEY` go on Ropewalk's Settings page.
5. For running the server on your machine, I'll put both in `server/.env`, and the `.gitignore`
   will list `node_modules` and `.env`.
6. On Pinecart's Settings page I'll set `VITE_API_URL` to the backend's address on Ropewalk.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q6

Suppose the agent has carried out plan 5 (Pinecart's repository link off, a workflow that runs
the tests in `client/` and `server/` and then deploys the frontend to Pinecart, and Ropewalk
linked to `main` with "Wait for GitHub checks" on). It says everything is set up, and both hosts'
deploy lists show the latest deploy as Live.

How would you make sure that a push to `main` now reaches the live app, both its frontend and its
backend?

### q7

Suppose the agent has carried out plan 5 (Pinecart's repository link off, a workflow that runs
the tests in `client/` and `server/` and then deploys the frontend to Pinecart, and Ropewalk
linked to `main` with "Wait for GitHub checks" on). It says everything is set up, and both hosts'
deploy lists show the latest deploy as Live.

How would you make sure that a push whose tests fail goes live in neither the frontend nor the
backend?
