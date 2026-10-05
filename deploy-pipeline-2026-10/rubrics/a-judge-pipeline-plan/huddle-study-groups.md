The third shape in each rotation: slot 1 `token-in-workflow`, slot 3 `tests-beside` with
Ropewalk's "Wait for GitHub checks" off, slot 4 Ropewalk waiting for checks. No plan uses
Ropewalk's deploy hook, so the hook's URL is not in the secrets list and the roster's hook and
auto-deploy bullets are not quoted; the CDN bullet is left out too, since "Clear CDN cache on
deploy" is on for a new site and no question turns on it.

Every plan has exactly one fault or none. Every plan deploys the frontend through a workflow that
runs `npm test` in `client/` and `server/` and then Pinecart's deploy command, with Pinecart's link
off. Plans 2 and 3 leave where the Pinecart deploy token is kept unsaid; plan 1's fault is the
token's place. A remark on plans 2 and 3 about the token's place is neither credited nor counted,
unless it puts the token in the workflow file or another committed file, which cancels the
question's credit. The same holds for any remark beyond what a question asks that would put a
secret into the repository or a Pinecart setting, or stop a deploy waiting for the tests.

### q1

- **goal:** `c-set-up-auto-deploy`
- **cases:** secret-in-repo, deploy-token
- **answer:** Not as it stands. Step 3 writes the Pinecart deploy token into `deploy.yml`, which
  is committed, so anyone who can read the repository can deploy to the site. Put the token in the
  repository's GitHub secrets (Actions secrets) and have the workflow read it from there.
- **credit:** one ruling for both cases alike: full for naming step 3 (the token written into the
  workflow file) and asking for the token to go in the repository's GitHub secrets, read by the
  workflow. A reason is welcome, not required. Half for naming step 3 with no workable change: a
  vague one ("keep it somewhere safe", "hide it"), or a place the workflow can't read or that is
  no safer (a `.env` file that `.gitignore` covers, which never reaches GitHub; a Pinecart
  setting; another committed file). None for agreeing, or for objecting only to sound steps.
- **tutor note:** "nothing else to set up" is the bait. If they agree, ask who can read
  `deploy.yml` and what they could do with the token. If they move the token to a git-ignored
  `.env`, ask how the workflow, running on GitHub, would read it.

### q2

- **goal:** `c-set-up-auto-deploy`
- **cases:** frontend-secret
- **answer:** Not as it stands. Step 3 puts the weather service's key in a Pinecart setting, and
  Pinecart's build copies it into the files every visitor's browser downloads, so anyone can read
  it. Keep the key, as `FORECAST_KEY`, on Ropewalk's Settings page, and have the group page get
  the forecast through the backend, which calls the weather service with the key.
- **credit:** full for naming the weather key in Pinecart's settings (step 3) and asking for the
  outside service to be called through the backend, with the key in Ropewalk's settings. A reason
  is welcome, not required. Half for naming the key in Pinecart's settings with no workable change
  (only "take the key out", leaving the forecast with no way to load, or "keep it safe"). None for
  agreeing, for objecting only to sound steps (`VITE_SERVER_URL` in Pinecart's settings is sound:
  the backend's address is not a secret), or for moving the key into a committed file.
- **tutor note:** if they accept "the server has less to do", ask where the key ends up once
  Pinecart has built the frontend.

### q3

- **goal:** `c-set-up-auto-deploy`
- **cases:** no-test-gate
- **answer:** Not as it stands. Ropewalk keeps its other settings as they are, so "Wait for GitHub
  checks" stays off and it deploys the backend on every push to `main` whatever the tests say;
  only the frontend waits for them. Turn on "Wait for GitHub checks" for Ropewalk.
- **credit:** full for naming that the backend deploys without waiting for the tests (Ropewalk
  linked with "Wait for GitHub checks" left off, step 3) and asking for it to wait, for example
  turning that setting on, or switching off Ropewalk's auto-deploy and having the workflow call its
  deploy hook once the tests pass; saying how is welcome, not required, so "make the backend's
  deploy wait for the tests" is full. Half for naming the right step with no workable change
  ("check Ropewalk's settings"). None for agreeing, for asking only for tests to be added as if
  none ran, or for objecting only to sound steps (the workflow deploying the frontend once the
  tests pass is sound).
- **tutor note:** "so CI will check every push" is the bait. If they agree, ask what Ropewalk does
  with a push whose tests fail, and what "keeping its other settings as they are" leaves "Wait for
  GitHub checks" at.

### q4

- **goal:** `c-set-up-auto-deploy`
- **cases:** sound-plan, deploy-token
- **answer:** Yes, go along with it: the secrets are only in Ropewalk's settings and a local
  `server/.env` that `.gitignore` covers, Pinecart holds only the backend's address, and both
  parts wait for the tests. Tell the agent to keep the token in the repository's GitHub secrets
  (Actions secrets), where the workflow reads it, not in the workflow file.
- **credit:** one ruling for the question: full only when the answer meets what each case below
  asks for full, half when it meets at least half on each but not full on both, and none
  otherwise.
  - `sound-plan`: full for agreeing, with or without harmless remarks. None for asking to change a
    sound step into a faulty one, or for refusing it on a wrong ground (such as "the `.env` file
    shouldn't exist at all", or "`VITE_SERVER_URL` is a secret").
  - `deploy-token`: full for the repository's GitHub secrets (Actions secrets), read by the
    workflow. Half for "somewhere secret, not in the file" with no place named. None for the
    workflow file, a `.env` file, a Pinecart setting, or the chat.
  So a wrong place for the token fails the question however the plan itself is judged.
- **tutor note:** if they put the token in `server/.env` because that is where the other secrets
  went, ask whether the workflow, running on GitHub, can read a file that `.gitignore` keeps out
  of the repository.

### q5

- **goal:** `c-set-up-auto-deploy`
- **cases:** confirm-live, confirm-gate
- **answer:** Push a small change that shows only once both parts have deployed it, such as a new
  line on a group's page that the page gets from the backend, wait for both deploys, and open the
  live app in the browser to see the new text there. Then push a change that makes a test fail,
  along with something visible from each part (new text in the page itself and new text the page
  gets from the backend), see that the live app shows neither (or see on the deploy lists that
  Ropewalk skipped the commit and Pinecart made no new deploy), and then fix or revert it.
- **credit:** one ruling for the question: full only when the answer meets what each case below
  asks for full, half when it meets at least half on each but not full on both, and none
  otherwise. The answer may cover the two in either order.
  - `confirm-live`: full for pushing a small change that shows in the live app only once both
    parts have deployed it (new text the page gets from the backend, or a frontend change together
    with the backend change it relies on) and seeing it in the live app in the browser. Half for a
    change that shows once only one part has deployed it (a frontend-only change, or a backend
    change checked only by calling the backend directly), for pushing a change and checking only
    the deploy lists or the agent's report, or for opening the live app without pushing anything
    new. None for taking the agent's word or the Live status.
  - `confirm-gate`: full for pushing a change that makes a test fail and seeing that neither part
    deploys it, then fixing or reverting it. Either kind of evidence is full: the live app, when
    the push carries something visible from each part and the live app shows neither; or the
    deploy lists, when Ropewalk's list shows the commit Skipped (checks failed), or no Ropewalk
    deploy of it, and Pinecart's list shows no new deploy. The rule against trusting the hosts'
    word belongs to `confirm-live` alone. Half for seeing it for one part only (a failing push
    whose visible change comes from one part only, or checking one host's deploy list), or for
    watching only the red check. None for reading the hosts' settings or asking the agent.
- **tutor note:** if they plan a failing push that changes only the frontend, ask how they would
  know the backend held it back too.
