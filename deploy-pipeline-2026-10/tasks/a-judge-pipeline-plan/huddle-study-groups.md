Answer each question in two to four sentences.

Huddle is a study-group finder for one university's students. A student finds a group for their
course, joins it, and sees where and when it meets, with the weather forecast for groups that meet
outdoors on the quad, which comes from a weather service. The React frontend is in `client/` and
the Express backend in `server/`, both in one GitHub repository, `huddle-study/finder`, and each
folder has tests that `npm test` runs. The database is on a database host outside this plan.

The backend reads the database's connection string, `HUDDLE_DB`, and the weather service's key,
`FORECAST_KEY`. The frontend reads the backend's address, `VITE_SERVER_URL`. Secrets: the
database's connection string, the weather service's key, and the Pinecart deploy token.

The frontend is hosted on Pinecart and the backend on Ropewalk. This is how they behave:

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
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced or Failed. A Live deploy shows as Replaced once a later deploy goes live, so only one
    deploy is Live at a time. When a deploy fails, the previous one stays live.
- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Settings (environment variables) entered on the service's Settings page reach the running
    server and never the browser. Saving one restarts the server with the new value.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.

You asked an agent to make Huddle deploy itself, frontend and backend, whenever `main` is pushed
to GitHub. It proposed each plan below in a different session. Each question is about its own plan
alone.

### q1

The agent proposes:

1. I'll switch off Pinecart's repository link.
2. I'll add a GitHub Actions workflow, `.github/workflows/deploy.yml`, that runs on every push to
   `main`. It runs `npm test` in `client/` and in `server/`, and once both pass, it runs
   Pinecart's deploy command with the Pinecart deploy token to deploy the frontend.
3. I'll write the token, which Pinecart labels `huddle-ci`, straight into `deploy.yml` as
   `PINECART_TOKEN: pct_...`, so the deploy step always has it and there's nothing else to set
   up.
4. I'll link Ropewalk to `huddle-study/finder`, branch `main`, folder `server/`, and turn on "Wait
   for GitHub checks".
5. I'll enter `HUDDLE_DB` and `FORECAST_KEY` on Ropewalk's Settings page, and `VITE_SERVER_URL` on
   Pinecart's Settings page.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q2

The agent proposes:

1. I'll link Ropewalk to `huddle-study/finder`, branch `main`, folder `server/`, and turn on "Wait
   for GitHub checks".
2. I'll enter `HUDDLE_DB` on Ropewalk's Settings page.
3. On Pinecart's Settings page I'll enter `VITE_SERVER_URL`, the backend's address, and
   `VITE_FORECAST_KEY`, the weather service's key, so the group page can fetch the forecast
   straight from the weather service and the server has less to do.
4. I'll switch off Pinecart's repository link and add a GitHub Actions workflow that runs on every
   push to `main`. It runs `npm test` in `client/` and in `server/`, and once both pass, it runs
   Pinecart's deploy command to deploy the frontend.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q3

The agent proposes:

1. I'll add a GitHub Actions workflow that runs on every push to `main`, so CI will check every
   push. It runs `npm test` in `client/` and in `server/`, and once both pass, it runs Pinecart's
   deploy command to deploy the frontend.
2. I'll switch off Pinecart's repository link, so the workflow is the only way the frontend
   deploys.
3. I'll link Ropewalk to `huddle-study/finder`, branch `main`, folder `server/`, keeping its other
   settings as they are.
4. I'll enter `HUDDLE_DB` and `FORECAST_KEY` on Ropewalk's Settings page, and `VITE_SERVER_URL` on
   Pinecart's Settings page.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q4

The agent proposes:

1. I'll enter `HUDDLE_DB` and `FORECAST_KEY` on Ropewalk's Settings page, and link Ropewalk to
   `huddle-study/finder`, branch `main`, folder `server/`, with "Wait for GitHub checks" on.
2. For running the app on your own machine, I'll put `HUDDLE_DB` and `FORECAST_KEY` in
   `server/.env`, and add `.env` to `.gitignore`, beside `node_modules`.
3. I'll switch off Pinecart's repository link and enter `VITE_SERVER_URL`, the backend's address,
   on Pinecart's Settings page.
4. I'll add a GitHub Actions workflow that runs on every push to `main`. It runs `npm test` in
   `client/` and in `server/`, and once both pass, it runs Pinecart's deploy command to deploy the
   frontend.

I'll need a Pinecart deploy token for the workflow. Where should I keep it?

Would you go along with this plan? And what would you tell the agent about where to keep the
token?

### q5

Suppose the agent has carried out plan 4, keeping the token in the repository's GitHub secrets,
says everything is set up, and both hosts' deploy lists show the latest deploy as Live.

How would you make sure that a push to `main` now reaches the live app, both its frontend and its
backend, and that a push whose tests fail goes live in neither?
