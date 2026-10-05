The first shape in each rotation: slot 1 `committed-secret`, slot 3 `ungated-watch`, slot 4
Ropewalk waiting for checks. No plan uses Ropewalk's deploy hook, so the hook's URL is not in the
secrets list and the roster's hook and auto-deploy bullets are not quoted; the CDN bullet is left
out too, since "Clear CDN cache on deploy" is on for a new site and no question turns on it.

Every plan has exactly one fault or none. Plans 1 and 2 deploy the frontend the sound way
(Pinecart's link off, a workflow running `npm test` in `client/` and `server/` and then Pinecart's
deploy command) and Ropewalk waits for GitHub checks; the workflow is the check it waits for.
Plans 1 to 3 leave where the Pinecart deploy token is kept unsaid (plan 3 needs none). A remark
there about the token's place is neither credited nor counted, unless it puts the token in the
workflow file or another committed file, which cancels the question's credit. The same holds for
any remark beyond what a question asks that would put a secret into the repository or a Pinecart
setting, or stop a deploy waiting for the tests.

### q1

- **goal:** `c-set-up-auto-deploy`
- **cases:** secret-in-repo
- **answer:** Not as it stands. Step 5 writes the database's connection string into
  `server/db.js`, which is committed, so the secret is in the repository. Drop the fallback: the
  value lives only on Ropewalk's Settings page (step 4 already puts it there), and in a local
  `server/.env` that `.gitignore` covers if it is needed for running on their own machine.
- **credit:** full for naming step 5 (the connection string written into `server/db.js`) and
  asking for a change that removes it: the value kept only in Ropewalk's settings, or in a `.env`
  file that `.gitignore` covers. A reason is welcome, not required. Half for naming step 5 with
  no workable change, or a vague one ("keep it safe", "hide it"). None for agreeing, or for
  objecting only to sound steps.
- **tutor note:** the reason attached to step 5 ("so the server still starts if the setting is
  ever missing") is the bait. If they accept it, ask where `server/db.js` ends up after a push and
  who can read it there.

### q2

- **goal:** `c-set-up-auto-deploy`
- **cases:** frontend-secret
- **answer:** Not as it stands. Step 4 puts the maps service's key in a Pinecart setting, and
  Pinecart's build copies it into the files every visitor's browser downloads, so anyone can read
  it. Keep `MAPS_KEY` on Ropewalk's Settings page and have the frontend get the map through the
  backend, which calls the maps service with the key.
- **credit:** full for naming the maps key in Pinecart's settings (step 4) and asking for the
  outside service to be called through the backend, with the key in Ropewalk's settings. A reason
  is welcome, not required. Half for naming the key in Pinecart's settings with no workable change
  (only "take the key out", leaving the map with no way to work, or "keep it safe"). None for
  agreeing, for objecting only to sound steps (`VITE_API_URL` in Pinecart's settings is sound: the
  backend's address is not a secret), or for moving the key into a committed file.
- **tutor note:** if they say only "don't put the key there", ask how the map on the trip page
  gets drawn once the key is gone from the frontend.

### q3

- **goal:** `c-set-up-auto-deploy`
- **cases:** no-test-gate
- **answer:** Not as it stands. Nothing runs the tests, and nothing makes either deploy wait for
  them: Pinecart deploys every push to `main`, and Ropewalk keeps "Wait for GitHub checks" off.
  Add a workflow that runs `npm test` in `client/` and `server/` on every push, and make both
  deploys wait for it, for example Pinecart's link off with the workflow deploying the frontend
  once the tests pass, and Ropewalk's "Wait for GitHub checks" on.
- **credit:** full for asking for the tests to be run (a workflow running `npm test`) and for both
  parts to be made to wait for them; saying how each part waits is welcome, not required, so "run
  the tests, and make both deploys wait for them" is full. Half for making only one part wait; for
  a way of waiting the roster rules out for a part (Pinecart waiting for GitHub checks); for
  turning on "Wait for GitHub checks" with no tests running (a commit with no checks deploys
  straight away); or for asking only for the tests to be run, with nothing made to wait for them.
  None for agreeing, or for objecting only to sound steps.
- **tutor note:** step 4 is the plan's selling point. If they agree, ask what happens to a push
  whose tests would fail. If they ask for "Wait for GitHub checks" on both, ask what Pinecart can
  wait for.

### q4

- **goal:** `c-set-up-auto-deploy`
- **cases:** sound-plan, deploy-token
- **answer:** Yes, go along with it: the secrets are only in Ropewalk's settings and a local
  `server/.env` that `.gitignore` covers, Pinecart holds only the backend's address, and both
  parts wait for the tests. Tell the agent to keep the token in the repository's GitHub secrets
  (Actions secrets), where the workflow reads it, not in the workflow file.
- **credit:** credited per case.
  - `sound-plan`: full for agreeing, with or without harmless remarks. None for asking to change a
    sound step into a faulty one, or for refusing it on a wrong ground (such as "the `.env` file
    shouldn't exist at all", or "`VITE_API_URL` is a secret").
  - `deploy-token`: full for the repository's GitHub secrets (Actions secrets), read by the
    workflow. Half for "somewhere secret, not in the file" with no place named. None for the
    workflow file, a `.env` file, a Pinecart setting, or the chat.
  A wrong place for the token loses `deploy-token` only and leaves `sound-plan` as the rest of the
  answer earns it.
- **tutor note:** if they put the token in `server/.env` because that is where the other secrets
  went, ask whether the workflow, running on GitHub, can read a file that `.gitignore` keeps out
  of the repository.

### q5

- **goal:** `c-set-up-auto-deploy`
- **cases:** confirm-live, confirm-gate
- **answer:** Push a small change that shows only once both parts have deployed it, such as new
  text on the trip page that the page gets from the backend, wait for both deploys, and open the
  live app in the browser to see the new text there. Then push a change that makes a test fail,
  along with something visible from each part (new text in the page itself and new text the page
  gets from the backend), see that the live app shows neither, and then fix or revert it.
- **credit:** credited per case; the answer may cover the two in either order.
  - `confirm-live`: full for pushing a small change that shows in the live app only once both
    parts have deployed it (new text the page gets from the backend, or a frontend change together
    with the backend change it relies on) and seeing it in the live app in the browser. Half for a
    change that shows once only one part has deployed it (a frontend-only change, or a backend
    change checked only by calling the backend directly), for pushing a change and checking only
    the deploy lists or the agent's report, or for opening the live app without pushing anything
    new. None for taking the agent's word or the Live status.
  - `confirm-gate`: full for pushing a change that makes a test fail together with something
    visible from each part, and seeing that the live app shows neither, then fixing or reverting
    it. Half for a failing push whose visible change comes from one part only, or for watching
    only the red check or the deploy lists (Ropewalk showing the commit Skipped, Pinecart showing
    no new deploy). None for reading the hosts' settings or asking the agent.
- **tutor note:** if they stop at the deploy lists, ask what a visitor to the site would see, and
  how they would know it came from the new commit.
