The secrets are `DATABASE_URL` (the database's connection string) and `MAPS_API_KEY`; the
backend's address, `VITE_API_URL`, is not a secret and belongs in a Pinecart setting. Each plan has
one fault or none:

- Plan 1 (`committed-secret`): step 3 writes the connection string into `server/db.js`.
- Plan 2 (`frontend-secret`): step 4 puts the maps key in a Pinecart setting.
- Plan 3 (`tests-beside`, Pinecart linked): step 1 links Pinecart to `main`, so the frontend
  deploys every push whatever the workflow's tests say. Ropewalk does wait.
- Plan 4 (token question): sound except that the token's place is open.
- Plan 5 (`sound`): nothing to change.

Plans 1 and 2 say the workflow runs Pinecart's deploy command "with the Pinecart deploy token"
without saying where the token is kept, so that plan 4's question isn't answered before it is
asked. A learner who points this out on plan 1 or 2 is making a remark beyond the question: it is
neither credited nor counted, unless they say to keep the token in the workflow file, which
cancels the credit.

### q1

- **goal:** `c-set-up-auto-deploy`
- **cases:** secret-in-repo
- **answer:** No. Step 3 writes the database's connection string into `server/db.js`, which is
  committed, so the secret ends up in the repository. Drop the fallback: the value is already on
  Ropewalk's Settings page, and for local runs it can go in a `server/.env` that `.gitignore`
  covers.
- **credit:** full for naming step 3 (the connection string written into `server/db.js`) and
  asking for it to be taken out, with the value kept in Ropewalk's settings or in a `.env` file
  that `.gitignore` covers; a reason is welcome, not required. Half for naming step 3 with no
  workable change, or a vague one ("keep it safe", "hide it"), or for moving it to a `.env` file
  with nothing said about keeping that file out of git. None for agreeing, or for objecting only
  to other steps.
- **tutor note:** if they accept the fallback because it only runs when the setting is missing,
  ask afterwards who can read `server/db.js` once it is pushed.

### q2

- **goal:** `c-set-up-auto-deploy`
- **cases:** frontend-secret
- **answer:** No. Step 4 puts the maps key in a Pinecart setting, and the build copies it into
  files every visitor's browser downloads. Take `VITE_MAPS_KEY` out of Pinecart; have the frontend
  ask the backend for the map, and the backend call the maps service with `MAPS_API_KEY` from
  Ropewalk's Settings page.
- **credit:** full for naming the maps key in Pinecart's settings (step 4) and asking for the maps
  service to be called through the backend, with the key in Ropewalk's settings; a reason is
  welcome, not required. Half for naming that step with no workable change, or a vague one
  ("don't expose it"), or a change that still leaves the key in the frontend's build (such as
  passing it from GitHub secrets into the build). None for agreeing, or for objecting only to
  other steps, including `VITE_API_URL` in Pinecart's settings, which is not a secret.
- **tutor note:** if they agree because the key "is only in a setting, not in the code", ask
  afterwards what the build does with a setting's value.

### q3

- **goal:** `c-set-up-auto-deploy`
- **cases:** no-test-gate
- **answer:** No. The workflow runs the tests, but Pinecart is linked to `main` (step 1), so it
  deploys the frontend on every push whatever the tests say. Switch off Pinecart's repository link
  and have the workflow run Pinecart's deploy command once the tests pass, with the token in the
  repository's GitHub secrets. Ropewalk already waits for the checks.
- **credit:** full for naming that the frontend's deploy (Pinecart linked to `main`) doesn't wait
  for the tests and asking for it to wait; naming the means (link off, workflow deploys after the
  tests) is welcome, not required. Half for the right step with no workable change, or a vague
  one, or a means the roster rules out (turning on "Wait for GitHub checks" for Pinecart). None
  for agreeing ("CI checks every push"), for asking only for tests to be added as if none ran, or
  for objecting only to Ropewalk's step, which already waits.
- **tutor note:** if they agree on the strength of step 3, ask afterwards what Pinecart does with
  a push whose tests have failed.

### q4

- **goal:** `c-set-up-auto-deploy`
- **cases:** deploy-token
- **answer:** Keep it in the repository's GitHub secrets (Actions secrets), for example as
  `PINECART_TOKEN`, and have the workflow read it from there, never written into the workflow
  file.
- **credit:** full for the repository's GitHub secrets (Actions secrets), read by the workflow.
  Half for "somewhere secret, not in the file" with no place named. None for the workflow file, a
  `.env` file, a Pinecart setting, the chat, or Ropewalk's settings (which reach the running
  server, not the workflow).

### q5

- **goal:** `c-set-up-auto-deploy`
- **cases:** sound-plan
- **answer:** Yes, as it stands. The secrets are on Ropewalk's Settings page, the local
  `server/.env` is covered by `.gitignore`, only the backend's address is in a Pinecart setting,
  the token is in GitHub secrets, and both parts wait for the tests.
- **credit:** full for agreeing, with or without harmless remarks. No half credit. None for asking
  to change a sound step into a faulty one (committing `.env`, linking Pinecart to `main`, turning
  "Wait for GitHub checks" off, moving a secret into a Pinecart setting or the token into the
  workflow file), or for refusing on a wrong ground (such as "the `.env` file shouldn't exist at
  all", or "a token shouldn't be kept on GitHub").

### q6

- **goal:** `c-set-up-auto-deploy`
- **cases:** confirm-live
- **answer:** Push a small change that shows in the live app only once both parts have deployed
  it, such as a new line of text the page gets from the backend (a new route or field in
  `server/`, shown by a matching change in `client/`), then open the live app in the browser and
  see the new text there.
- **credit:** full for pushing a small change that shows in the live app only once both parts have
  deployed it (new text the page gets from the backend, or a frontend change together with the
  backend change it relies on) and seeing it in the live app in the browser. Half for a change
  that shows once only one part has deployed it (a frontend-only change, or a backend change
  checked only by calling the backend directly), for pushing a change and checking only the
  deploy lists or the agent's report, or for opening the live app without pushing anything new.
  None for taking the agent's word or the Live status.

### q7

- **goal:** `c-set-up-auto-deploy`
- **cases:** confirm-gate
- **answer:** Push a change that makes a test fail, together with something visible from each part
  (new text in the page itself, and new text the page gets from the backend), then open the live
  app and see that it shows neither; afterwards fix or revert the change.
- **credit:** full for pushing a change that makes a test fail together with something visible
  from each part, seeing that the live app shows neither, then fixing or reverting it. Half for a
  failing push whose visible change comes from one part only, or for watching only the red check
  or the deploy lists. None for reading the hosts' settings or asking the agent.
- **tutor note:** if they say they would check that Ropewalk's deploy list shows Skipped, ask
  afterwards what that tells them about the frontend.
