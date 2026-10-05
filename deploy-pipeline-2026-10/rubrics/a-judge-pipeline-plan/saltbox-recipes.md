The second shape in each rotation: slot 1 `unignored-env`, slot 3 `tests-beside` with Pinecart
linked to `main`, slot 4 Ropewalk deployed through its hook. Plans 2 and 4 use Ropewalk's deploy
hook, so the hook's URL is in the secrets list and the roster's auto-deploy and hook bullets are
quoted; the CDN bullet is left out, since "Clear CDN cache on deploy" is on for a new site and no
question turns on it.

Every plan has exactly one fault or none. Outside its fault, each plan deploys the backend a sound
way: plans 1 and 3 have Ropewalk wait for GitHub checks (the workflow is the check it waits for),
and plan 2 has the workflow call the hook once the tests pass. Plans 1 to 3 leave where the Pinecart deploy
token and the hook's URL are kept unsaid (plan 3 needs neither). A remark there about where to keep
either is neither credited nor counted, unless it puts the token or the hook's URL in the workflow
file or another committed file, which cancels the question's credit. The same holds for any remark
beyond what a question asks that would put a secret into the repository or a Pinecart setting, or
stop a deploy waiting for the tests.

### q1

- **goal:** `c-set-up-auto-deploy`
- **cases:** secret-in-repo
- **answer:** Not as it stands. Step 5's `.gitignore` lists only `node_modules`, so the
  `server/.env` from step 4, holding the connection string and the AI key, is committed with
  everything else and the secrets end up in the repository. Add `.env` to `.gitignore` (or keep
  the secrets out of `server/.env`, on Ropewalk's Settings page only, where step 3 already puts
  them).
- **credit:** full for naming that `server/.env` would be committed because `.gitignore` doesn't
  list it (step 4 or step 5, so long as the answer says the file gets committed) and asking for a
  change that removes it: `.env` added to `.gitignore`, or the secrets kept only in Ropewalk's
  settings. A reason is welcome, not required. Half for naming the `.env` file or the
  `.gitignore` with no workable change, or a vague one ("make sure it's secure"). None for
  agreeing, or for objecting only to sound steps (putting the secrets in a local `.env` for
  running the app at home is sound once git ignores it).
- **tutor note:** if they agree because step 3 already puts the secrets on Ropewalk, ask what
  `git add .` picks up when `.gitignore` lists only `node_modules`.

### q2

- **goal:** `c-set-up-auto-deploy`
- **cases:** frontend-secret
- **answer:** Not as it stands. Step 5 puts the AI service's key in a Pinecart setting, and
  Pinecart's build copies it into the files every visitor's browser downloads, so anyone can read
  it. Keep the key, as `SWAP_AI_KEY`, on Ropewalk's Settings page, and have the "Suggest a swap"
  button ask the backend, which calls the AI service with the key.
- **credit:** full for naming the AI key in Pinecart's settings (step 5) and asking for the outside
  service to be called through the backend, with the key in Ropewalk's settings. A reason is
  welcome, not required. Half for naming the key in Pinecart's settings with no workable change
  (only "take the key out", leaving the button with no way to work, or "keep it safe"). None for
  agreeing, for objecting only to sound steps (`VITE_BACKEND_URL` in Pinecart's settings is sound:
  the backend's address is not a secret; the hook call in step 3 is sound), or for moving the key
  into a committed file.
- **tutor note:** if they accept "answer faster", ask who else can read a value that ends up in
  the files every visitor's browser downloads.

### q3

- **goal:** `c-set-up-auto-deploy`
- **cases:** no-test-gate
- **answer:** Not as it stands. Pinecart is linked to `main` (step 1), and Pinecart cannot wait
  for GitHub checks, so it deploys the frontend on every push whatever the tests in step 4 say;
  only Ropewalk waits. Switch off Pinecart's repository link and have the workflow run Pinecart's
  deploy command once the tests pass.
- **credit:** full for naming that the frontend deploys without waiting for the tests (Pinecart
  linked to `main`, step 1) and asking for it to wait, for example Pinecart's link off and the
  workflow deploying the frontend once the tests pass; saying how is welcome, not required, so
  "make the frontend's deploy wait for the tests" is full. Half for naming the right step with no
  workable change, such as having Pinecart wait for GitHub checks, which the roster rules out, or
  switching off Pinecart's link with nothing to deploy the frontend afterwards. None for agreeing,
  for asking only for tests to be added as if none ran, or for objecting only to sound steps
  (Ropewalk waiting for the workflow's check is sound).
- **tutor note:** "CI will check every push" is the bait. If they agree, ask what Pinecart does
  with a push whose tests fail. If they say "turn on Wait for GitHub checks", ask which host that
  setting belongs to.

### q4

- **goal:** `c-set-up-auto-deploy`
- **cases:** sound-plan, deploy-token
- **answer:** Yes, go along with it: the secrets are only in Ropewalk's settings and a local
  `server/.env` that `.gitignore` covers, Pinecart holds only the backend's address, and both
  parts deploy only from the workflow once the tests pass (Pinecart's link off, Ropewalk's
  auto-deploy off and called through its hook). Tell the agent to keep the token in the
  repository's GitHub secrets (Actions secrets), where the workflow reads it, not in the workflow
  file.
- **credit:** one ruling for the question: full only when the answer meets what each case below
  asks for full, half when it meets at least half on each but not full on both, and none
  otherwise.
  - `sound-plan`: full for agreeing, with or without harmless remarks (saying the hook's URL
    belongs in GitHub secrets too is one). None for asking to change a sound step into a faulty
    one, or for refusing it on a wrong ground (such as "the `.env` file shouldn't exist at all",
    "`VITE_BACKEND_URL` is a secret", or "Ropewalk won't deploy with auto-deploy off").
  - `deploy-token`: full for the repository's GitHub secrets (Actions secrets), read by the
    workflow. Half for "somewhere secret, not in the file" with no place named. None for the
    workflow file, a `.env` file, a Pinecart setting, or the chat.
  So a wrong place for the token fails the question however the plan itself is judged, and so
  does putting the hook's URL in the workflow file.
- **tutor note:** if they object that Ropewalk will never deploy with auto-deploy off, ask what
  the request to the deploy hook in step 5 does.

### q5

- **goal:** `c-set-up-auto-deploy`
- **cases:** confirm-live, confirm-gate
- **answer:** Push a small change that shows only once both parts have deployed it, such as a new
  line of text under each suggested swap that the page gets from the backend, wait for both
  deploys, and open the live app in the browser to see the new text there. Then push a change
  that makes a test fail, along with something visible from each part (new text in the page itself
  and new text the page gets from the backend), see that the live app shows neither (or see on the
  deploy lists that neither host made a new deploy of the commit), and then fix or revert it.
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
    deploy lists, when Ropewalk's list shows no deploy of the commit (with its auto-deploy off,
    nothing but the hook deploys it; a Skipped (checks failed) entry would do as well) and
    Pinecart's list shows no new deploy. The rule against trusting the hosts' word belongs to
    `confirm-live` alone. Half for seeing it for one part only (a failing push whose visible change
    comes from one part only, or checking one host's deploy list), or for watching only the red
    check. None for reading the hosts' settings or asking the agent.
- **tutor note:** if they check the backend's change by visiting the backend's address directly,
  ask whether that shows the frontend has deployed too.
