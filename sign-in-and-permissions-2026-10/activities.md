# Activities: sign in and permissions

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-set-up-sign-in` | work with an agent to add sign-in through Google or GitHub to an app, on localhost and on the live app | Given an agent's plan for adding sign-in through Google or GitHub to a described app whose frontend and backend are on separate hosts, says which steps are theirs to do and what they would change before agreeing to it. It passes when they say that they register the app with the provider themselves, which gives them a client ID and a client secret; give the provider a redirect URL for localhost and another for the live app; put the client secret into the backend host's settings themselves rather than hand it to the agent, while the client ID may go in the frontend; catch a plan that asks the provider for more of the user's account than the app needs, such as their repositories when the app only shows their name; and go along with a plan in which the backend trades the code the provider sends back for who the user is, and keeps the provider's id for that user rather than a password. And, told that the client secret has been pushed to a public repository, they say to get a new one from the provider, put it where the old one was, and delete or disable the old one at the provider, and that deleting it from the repository does not fix it. |
| `c-review-permissions` | work with an agent to give an app levels of who may do what, and confirm that the server enforces them | Given a table of who may do what in a described app and an agent's plan for enforcing it, says what they would change before agreeing to it, and how they would confirm afterwards that the rules hold. It passes when they catch a table that leaves out something one of its levels could try to do, such as deleting, or leaves out someone who isn't signed in at all; catch a plan that enforces a rule only in React, such as hiding the Edit button from everyone but the owner; catch a plan that checks sign-in on most routes but leaves one that changes data unchecked; catch a plan in which the server takes the user's word for who they are, such as a user id the frontend sends with the request, rather than the session; go along with a plan that checks every rule on the server against the signed-in user and keeps the provider's id for each user, not a password; and say which requests would confirm the rules, rather than what the page shows, and what each should get back: a request to a protected path with no sign-in is refused with 401, and a second account, signed in, is refused the owner's actions with 403. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-mdn-sign-in`, `a-read-github-oauth-flow` | |
| `c-set-up-sign-in` | `a-critique-sign-in-plan`, `a-reply-to-sign-in-agent`, `a-sort-sign-in-steps` | |
| `c-review-permissions` | `a-critique-permissions-plan`, `a-contrast-permission-plans` | |

---

## Activities

### `a-read-mdn-sign-in`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** three free pages, no account, read in this order as one sitting. All three opened
  2026-10-07.
  1. **Read first:** MDN Web Docs, "Authentication" (last modified May 11, 2026),
     https://developer.mozilla.org/en-US/docs/Web/Security/Authentication. Read the opening
     paragraphs and Session management. Skim Authentication methods. About 500 words. What it
     gives: authentication as verifying that someone "is who they claim to be"; why signed-in
     users are a target; and a session as the website keeping a user signed in "by setting a
     cookie that contains a secret session identifier".
  2. **Then:** MDN Web Docs, "Federated identity" (last modified June 22, 2026),
     https://developer.mozilla.org/en-US/docs/Web/Security/Authentication/Federated_identity. Read
     the opening (before OpenID Connect), the one paragraph under OpenID Connect, and
     Authentication flow. In Authentication flow, skip the `code_challenge` and `code_verifier`
     bullets and the hashing check, and skim the last step's signature check: how tokens are built
     and signed is past this topic's depth. Skip everything from Security features on. About 1,000
     words. What it gives: the identity provider (IdP) and the website relying on it; OIDC as
     "built on top of the OAuth 2.0 authorization framework"; the client ID and client secret the
     site must have before anything starts; `redirect_uri` as "the URL to which the IdP will
     deliver the authorization code"; `scope` as "which sets of user data the RP wishes to
     access"; and the site's server trading the code, with its client secret, for who the user is.
  3. **Last:** OWASP Top 10:2025, "A01:2025 Broken Access Control",
     https://top10.owasp.org/2025/A01_2025-Broken_Access_Control. Read Description, and from How to
     prevent only its opening sentence and the next three bullets. Skip the rest. About 400 words.
     What it gives: access control as keeping users from acting "outside of their intended
     permissions"; the common failures (editing someone else's record by its id, an API "with
     missing access controls for POST, PUT, and DELETE", acting "without being logged in"); and
     that access control "is only effective when implemented in trusted server-side code".
  About 1,900 words: 12 minutes of reading, 20 with the stops and the close. Words in place:
  authentication, session, identity provider, OAuth, client secret, redirect URL (as
  `redirect_uri`), scope, and authorization (OWASP's "access control" and "permissions"; MDN calls
  OAuth an "authorization framework"). Role appears in OWASP's list as "roles". Not in the three
  pages: 401, 403 and rotate; the tutor brings them in at the stops. MDN describes OpenID Connect,
  which is what Google sign-in uses; GitHub sign-in is plain OAuth, so there is no ID token, and the
  backend instead uses the access token to ask GitHub's API who the user is. The tutor says so at
  stop 1.
- **verified:** 2026-10-07
- **learner does:** reads the three pages in order with Part B of Problem Set 3 in mind (an app
  whose single basic-auth password gives way to sign-in through Google or GitHub). Stops twice and
  answers before reading on; "I don't know yet" is an honest answer:
  1. After MDN's two pages: **sketches sign-in as four boxes, the browser, the React frontend on
     its static host, the Express backend on its server host, and the provider**, and draws the
     trips between them in order, marking where the client ID, the client secret, the redirect URL
     and the code each travel, and which box ends up remembering that the user is signed in.
  2. After OWASP: writes a three-row who-may-do-what table for a made-up app the tutor names (for
     example, a club events board), with a column for someone not signed in, and marks which
     OWASP failure would break each row if the server didn't check it.
  Then the close, about 5 minutes, with the sketch, the table and the reading still beside them:
  two quick rehearsals, neither judged, each answered in a sentence or two (see the generator).
  Then answers the question the tutor puts: with your sketch and the reading beside you, could you
  now attempt these two things for real: reviewing your agent's plan for sign-in through Google or
  GitHub and saying what you would do yourself and change, and reviewing its plan for who may do
  what and saying which requests would show the rules hold?
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you put the client secret in the browser box; who could read it there?"). At stop 1,
  says what the GitHub difference is (no ID token; the backend calls GitHub's API for the user),
  that the user's provider id is what the backend keeps, not a password, and that registering the
  app with the provider is the learner's own job, done in the provider's developer settings, which
  is where the client ID and client secret come from. At stop 2, brings in 401 and 403 from MDN's
  status pages, https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/401 and
  https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/403, quoting the 401 page: "a
  403 is returned when a request contains valid credentials, but the client does not have
  permissions to perform a certain action"; and brings in rotate from GitHub's "About removing
  sensitive data from a repository",
  https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository:
  for a leaked secret, "as a first step you need to revoke and/or rotate that secret". Says how
  tokens are signed, and defending a live app against abuse (session 14), are out of scope. At the
  close, sets the two rehearsals from the generator below and grades neither; if an answer shows a
  misunderstanding (a hidden button counting as a rule; deleting a pushed secret from the
  repository as the fix), explains it once and moves on. Then puts the readiness question as
  written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops,
  the rehearsals, or whether the tutor thinks they are ready. A plain yes to both parts is
  `criterion: met`. A hedge on either part, with no plain no, is `criterion: unclear`: explain the
  hedged part once more and put the question again; a second hedge stays `unclear`, and the tutor
  offers an activity on that capability, or the session 13 class. A plain no to either part is
  `criterion: not met`: record it, ask what is missing, and offer to go back over the stop that
  bears on it; don't put the question again in the same sitting. This goal isn't required, so a no
  never blocks anything else the learner wants to try.
- **generator:** vary the two rehearsal items; hold the rest fixed. Rehearsal one is one question
  from `a-critique-sign-in-plan`'s generator at Medium, case `secret-placement`. Rehearsal two is
  one question from `a-critique-permissions-plan`'s generator at Medium, case `react-only`. Both on
  a made-up app. Fixed: the reading and its two stops, then the two rehearsals in that order,
  neither graded, then the readiness question word for word. Difficulty doesn't vary: this settles
  an indication, not a capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. The
  stops and rehearsals are helped and ungraded, and only two of the fourteen cases across the two
  capabilities are rehearsed, so it shows nothing about either capability. It shows nothing about
  the twelve words, which have their own supply.
- **offer as:** the explanation first: why sign-in through another service works the way it does
  (MDN), then what goes wrong with who may do what (OWASP), then a short close. Vendor-neutral; the
  OpenID Connect flow it describes is the one Google uses. About 20 minutes.
- **note:** Plan on 25 to 30 minutes, not 20: the sketch at stop 1 and the table at stop 2 each take a few minutes once the reading is done.

### `a-read-github-oauth-flow`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** four free pages, no account, read in this order as one sitting. All four opened
  2026-10-07.
  1. **Read first:** GitHub Docs, "Authorizing OAuth apps",
     https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/authorizing-oauth-apps. Read the
     opening and Web application flow through its step 3, "Use the access token to access the
     API". In the parameter tables, read only `client_id`, `redirect_uri`, `scope`,
     `client_secret` and `code`; skip `state`, `code_challenge` and the rest. Skip everything from
     Device flow on. About 900 words read. What it gives: the three steps as GitHub states them
     (users "redirected to request their GitHub identity", "redirected back to your site by
     GitHub" with "a temporary `code`", and "your app accesses the API with the user's access
     token"); the client secret sent with the code to get the token; and step 3's example request,
     `GET https://api.github.com/user`, which is the backend asking who the user is.
  2. **Then:** GitHub Docs, "Scopes for OAuth apps",
     https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps. Read the
     opening and, in the table, only the rows for no scope, `repo`, `read:user` and `user:email`.
     About 250 words. What it gives: no scope "grants read-only access to public information
     (including user profile info...)", against `repo`, "full access to public and private
     repositories".
  3. **Then:** MDN Web Docs, the status pages for 401,
     https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/401, and 403,
     https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/403. Read the first
     paragraph of each and the 401 page's sentence comparing it with 403. About 200 words.
  4. **Last:** OWASP Top 10:2025, "A01:2025 Broken Access Control",
     https://top10.owasp.org/2025/A01_2025-Broken_Access_Control. Read Description, and from How to
     prevent only its opening sentence and the next three bullets. About 400 words.
  About 1,750 words: 11 minutes of reading, 20 with the stops and the close. Words in place: OAuth,
  client secret, redirect URL (as `redirect_uri`), scope, 401, 403, authentication (the 401 page's
  first paragraph: "lacks valid authentication credentials"), and authorization and role from
  OWASP. Not in the pages: identity provider, session and rotate; the tutor brings them in at the
  stops. GitHub is one of the two providers; the
  tutor says Google works the same way except that it hands back an ID token naming the user, so
  the backend need not call an API to ask.
- **verified:** 2026-10-07
- **learner does:** reads the four pages in order with Part B of Problem Set 3 in mind. Stops twice
  and answers before reading on; "I don't know yet" is an honest answer:
  1. After the two GitHub pages: **sketches sign-in as four boxes, the browser, the React frontend
     on its static host, the Express backend on its server host, and GitHub**, draws GitHub's three
     steps as trips between them, marks where the client ID, the client secret, the redirect URL
     and the code each travel, and says which scope an app that only shows the user's name needs.
  2. After MDN and OWASP: writes a three-row who-may-do-what table for a made-up app the tutor
     names (for example, a club events board), with a column for someone not signed in, and says
     for one row which status code the server should send back to someone not signed in and to a
     signed-in user who isn't allowed.
  Then the same close as `a-read-mdn-sign-in`: two ungraded rehearsals, then the readiness question
  word for word as written there.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you had React send the code to GitHub; what else does that request need, and could
  React keep it?"). At stop 1, names identity provider (GitHub here, Google the other) and
  authentication, says registering the app with GitHub is the learner's own job, in GitHub's
  developer settings, which is where the client ID and client secret come from, and that the
  backend keeps the user's GitHub id, not a password, then remembers the browser with a session (a
  cookie holding a secret session identifier). At stop 2, brings in rotate from GitHub's "About
  removing sensitive data from a repository",
  https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository:
  for a leaked secret, "as a first step you need to revoke and/or rotate that secret". Says how
  tokens are signed, and defending a live app against abuse (session 14), are out of scope. At the
  close, as in `a-read-mdn-sign-in`.
- **done when:** as in `a-read-mdn-sign-in`: the ruling is on the learner's answer to the readiness
  question, with the same rules for a yes, a hedge and a no.
- **generator:** as in `a-read-mdn-sign-in`: rehearsal one from `a-critique-sign-in-plan` at
  Medium, case `secret-placement`; rehearsal two from `a-critique-permissions-plan` at Medium, case
  `react-only`; fixed reading, stops, order and readiness question; difficulty doesn't vary.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. The
  stops and rehearsals are helped and ungraded, and only two of the fourteen cases are rehearsed.
  The pages show GitHub's side only, so a pass says nothing about Google's console. It shows
  nothing about the twelve words.
- **offer as:** the concrete version: GitHub's own pages on the steps your app will actually take,
  then the two status codes, then what goes wrong with who may do what. Less of the why than the MDN
  reading, and closest to Part B if you are using GitHub. About 20 minutes.
- **note:** Plan on 25 to 30 minutes, not 20. At stop 1, along with identity provider and the session, say that Google works the same way except that it hands back an ID token naming the user, so the backend need not call an API to ask.

### `a-critique-sign-in-plan`

- **serves:** `c-set-up-sign-in`
- **supports:** attempt
- **checks:** `c-set-up-sign-in`
- **artifact:** no external source. A made-up app and short excerpts of an agent's plan for adding
  sign-in to it, from this activity's bank or written live per the generator below. 2 to 4 minutes
  a question.
- **verified:** 2026-10-07
- **learner does:** reads the scenario's setup and the one excerpt served, and answers in two to
  four sentences the question every excerpt ends with: "Would you agree to this as it stands? If
  not, what would you change, and who does it, you or your agent?"
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never says
  whether an excerpt has anything wrong with it. When the generator is run live, writes the key
  into the record before showing anything. Gives help whenever it is asked for, and records the
  attempt as helped. Labels the attempt with the question's path, or
  `a-critique-sign-in-plan/<case>-<level>` when run live, and records the case with `--cases`.
- **done when:** full credit on the question, with no help. The goal is met once each of its six
  cases has been passed.
- **generator:** a scenario is one made-up app shaped like Problem Set 3, Part B: a React frontend
  built to static files on one made-up host, an Express backend on another made-up host, and a
  Postgres database, with a line on what the app does (a club events board, a study-room finder, a
  recipe box). It is protected now by one shared basic-auth password, which sign-in will replace.
  The setup names the provider (Google or GitHub, one per scenario), what the app shows about a
  signed-in user (their name and picture; their email only if the scenario says the app uses it),
  the two live addresses (such as `https://roomfinder.<statichost>.app` and
  `https://roomfinder-api.<serverhost>.com`) and the two localhost ports (5173 and 3001). Host
  names are invented and never a real vendor's. **Each question is a separate excerpt** of the
  agent's plan, and the setup says the questions are independent. An excerpt is 4 to 8 numbered
  steps written as a coding agent writes a plan, with file names, environment variable names and
  route paths where an agent would give them, followed by the fixed question quoted under
  `learner does`, except for `leaked-secret`, which ends with the question given there.

  **Every question carries exactly one case**, named on its rubric `cases:` line. Every step but
  the one the case fixes is sound, and each case fixes what the excerpt contains and what the key
  says:
  - `register-yourself`: a step where the agent takes on registering the app with the provider:
    it asks for the learner's Google or GitHub password so it can create the OAuth app, or it
    offers to create the OAuth app in the learner's browser, where they are already signed in to
    the provider. Key: the learner registers the app with the provider themselves, in the
    provider's developer settings, and that gives them a client ID and a client secret. Full credit
    needs both: that it is theirs to do, and the two values it gives them. Half credit for one. Any
    reason, or none, counts for "theirs to do"; the learner need not say whether the agent could
    manage it. Don't require any console's button names.
  - `two-redirects`: the plan tells the learner to register one redirect URL only, either the
    localhost one (`http://localhost:3001/auth/<provider>/callback`) or the live one, and names
    that single URL. Key: the provider needs a redirect URL for localhost and another for the live
    app (the backend's live address with the same path). A GitHub OAuth app holds up to 10
    callback URLs (GitHub changelog, 2026-08-14,
    https://github.blog/changelog/2026-08-14-multiple-redirect-uris-and-token-refresh-for-oauth-apps;
    GitHub Docs, "Creating an OAuth app": "You can enter up to 10 callback URLs"), and a Google
    client holds several redirect URIs, so for either provider the ordinary answer is to add the
    second redirect URL to the one registration; a second registration is also acceptable, and the
    key accepts either. Never write, in an excerpt, a key or a rubric, that GitHub allows only one
    callback URL: that is out of date. Full credit needs both URLs named and a way to give the
    provider both. Half credit for naming the missing one with no way to give it to the provider.
  - `secret-placement`: the client secret is going somewhere other than the backend host's
    settings by the learner's own hand, and the same excerpt says where the client ID goes, always
    the frontend's environment (`VITE_GITHUB_CLIENT_ID` or `VITE_GOOGLE_CLIENT_ID`), so the learner
    has to rule on both. Variants: the plan puts the client ID and client secret both in the
    frontend's environment (`VITE_GITHUB_CLIENT_ID`, `VITE_GITHUB_CLIENT_SECRET`); the plan asks the
    learner to paste the client ID and client secret into the chat, and says it will put the ID in
    `frontend/.env` and set the secret on the backend host; the plan writes the secret into a
    committed `backend/config.js` and the ID into `frontend/.env`. Key: the learner puts the client
    secret into the backend host's settings themselves (and into the local `.env` that
    `.gitignore` keeps out of the repository), never into the chat, the frontend or a committed
    file; the client ID in the frontend is fine. Full credit needs both: where the secret goes and
    who puts it there, and that the client ID may stay in the frontend (saying the ID step can stay
    as it is counts). Half credit for the secret alone.
  - `too-much-scope`: the plan asks the provider for more of the user's account than the app uses.
    GitHub: `repo`, or `user` (which can change profile data), when the app shows only the user's
    name and picture. Google: Drive, Gmail, Calendar or Contacts access on top of `openid profile`.
    Key: ask only for what the app shows: for GitHub no scope or `read:user` (with `user:email` if
    the app uses email); for Google `openid profile` (with `email` if it uses email). Full credit
    needs the excess caught and a smaller request named in the learner's words; the exact scope
    string is not required. Half credit for catching it with no replacement, or with a replacement
    that still asks for more than the app uses.
  - `sound-plan`: every step is sound: the Sign in button sends the browser to the provider; the
    provider sends it back to the backend's redirect URL with a code; the backend sends the code
    with the client ID and client secret (read from its environment) to the provider and learns who
    the user is (for GitHub by asking its API for the user, for Google from the ID token it gets
    back); it finds or creates a `users` row keyed by the provider's id (`github_id`, or Google's
    `sub`), with name and perhaps email, and no password column; it starts a session with a cookie,
    set so the browser sends it from the frontend's site to the backend's (the step says the two
    are on different sites, and names `sameSite: 'none'`, `secure: true` and CORS allowing
    credentials from the frontend's address). Key: agree as it stands. Full credit when they agree
    and ask for no change that would break it (moving the code exchange or the client secret into
    React, adding a password, keying users by email instead of the provider's id). A harmless
    suggestion (a sign-out route, a nicer error page) costs nothing, and so does raising that the
    session cookie has to work across the two hosts (asking about the cookie settings, or putting
    both under one domain): that is a real point, not a change that breaks the plan. None
    otherwise.
  - `leaked-secret`: the question's own line says the learner's `.env`, holding the client secret,
    was in a commit pushed to the public repository. The excerpt is the agent's proposed fix:
    delete `.env` in a new commit, add it to `.gitignore`, push (Hard: also rewrite history to
    remove it). It ends: "What do you do now, and does your agent's fix settle it?" Key: get a new
    client secret from the provider and put it where the old one was (the backend host's settings
    and the local `.env`); delete or disable the old one at the provider, since a GitHub OAuth app
    or a Google client can hold more than one secret and the old one stays valid until it is
    removed; and deleting it from the repository doesn't fix it, because it was already public.
    Full credit needs all three: the new secret in place, the old one deleted or disabled at the
    provider, and that the repository fix doesn't settle it. Half credit for some but not all.

  How hard, by how the excerpt is worded:
  - Medium: the step the case fixes says what it does in plain words ("I'll put the client
    secret in `frontend/.env` as `VITE_GITHUB_CLIENT_SECRET`"; "I'll request the `repo` scope").
  - Hard: Medium, plus one of: the step is justified in plausible words ("so we can show their
    projects later"; "to save you a trip to the dashboard, paste them here"); the step shows only
    as a config or code line among others, with no prose about it; or the plan ends by calling
    itself secure. A Hard `sound-plan` uses agent jargon throughout (`passport-github2`,
    `findOrCreate`, `express-session`) and includes one sound step that looks alarming to a novice
    (the client ID in the frontend's environment).
  A scenario carries all six cases, one question each, every one at Medium or Hard and at least two
  at Hard. No question's text gives away another's answer. A scenario's setup states the task and
  how long an answer should be, never the scoring.
- **worked example:** shown only as help when the learner asks for it, which records the attempt
  as helped. Work a different excerpt aloud: for each step, ask whether it happens in the browser,
  on the backend or at the provider, and who has to be there to do it. Cite MDN's "Federated
  identity", https://developer.mozilla.org/en-US/docs/Web/Security/Authentication/Federated_identity,
  under Authentication flow (the client ID and client secret as the prerequisite, `redirect_uri`,
  `scope`, and the token request from the site's server); for scopes, GitHub's "Scopes for OAuth
  apps", https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps; for a
  leaked secret, GitHub's "About removing sensitive data from a repository",
  https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository.
  At the first level of help on a real attempt, ask only "which of these steps happens on your
  backend, and which in the browser?"
- **doesn't show:** each excerpt holds at most one thing wrong, so a pass doesn't show the learner
  would catch two at once, or keep looking after finding one. Excerpts are short and read with a
  check known to be on; a real plan is longer and arrives mid-task. Nothing is registered, so a pass
  says nothing about finding their way around Google's or GitHub's console.
- **offer as:** plan review: your agent shows you a short plan before it writes any code, and you
  say what you'd change. One question per thing that could be wrong, 2 to 4 minutes each.
- **note:** When writing an excerpt live, any step outside `register-yourself`, `secret-placement` and `leaked-secret` that registers the app or sets the client secret should say the learner does it, or be left out. An unattributed step in an agent's plan reads as the agent's own, and a learner who flags it is right. Don't count a flag on a step the excerpt left ambiguous against them.

### `a-reply-to-sign-in-agent`

- **serves:** `c-set-up-sign-in`
- **supports:** attempt
- **checks:** `c-set-up-sign-in`
- **artifact:** no external source. A made-up app and single messages an agent sends partway
  through adding sign-in to it, from this activity's bank or written live per the generator below.
  2 to 3 minutes a question.
- **verified:** 2026-10-07
- **learner does:** reads the scenario's setup and the one agent message served, and writes the
  reply they would send the agent, in two to four sentences, as they would type it: what they say
  yes or no to, what they will do themselves, and what they want changed.
- **tutor role:** examiner
- **tutor does:** sets the message as served, without rewording it or hinting, and never says
  whether anything in it is wrong. When run live, writes the key into the record before showing
  anything. Gives help whenever it is asked for, and records the attempt as helped. Credits what the
  reply commits the learner to, not its tone. Labels the attempt with the question's path, or
  `a-reply-to-sign-in-agent/<case>-<level>` when run live, and records the case with `--cases`.
- **done when:** full credit on the question, with no help. The goal is met once each of its six
  cases has been passed.
- **generator:** a scenario's setup is the same shape as in `a-critique-sign-in-plan`: a made-up
  Problem Set 3 app, React on one made-up static host, Express on another, Postgres, one provider,
  what the app shows about a user, the live addresses and localhost ports, and a line saying the
  learner and their agent are partway through replacing basic auth with sign-in. **Each question is
  one agent message**, 2 to 6 lines, written as a coding agent writes in chat (a status line, a
  question or a request, sometimes a short code or config snippet), and the setup says the
  questions are independent moments in the work. The fixed instruction under each: "Write the
  reply you would send."

  **Every question carries exactly one case.** The keys and credit rules are those of
  `a-critique-sign-in-plan`, case for case; what changes is what the message holds:
  - `register-yourself`: the agent asks to do the registration ("I can open GitHub's developer
    settings in your browser, where you're already signed in, and create the OAuth app for you.
    OK?") or asks for the learner's provider password to do it. Either way the message ends: "And
    once it exists, what comes out of it that the code will need?" The key credits "it's mine to
    do" with any reason or none.
  - `two-redirects`: the agent asks "Which redirect URL do you want me to set in the code, and will
    you register it?", or reports that it has hard-coded one (localhost or live) and asks the
    learner to register that one. As in `a-critique-sign-in-plan`, a GitHub OAuth app holds up to
    10 callback URLs and a Google client holds several redirect URIs, so the ordinary reply adds
    the second URL to the one registration, and a second registration is also acceptable. Never
    write, in a message, a key or a rubric, that GitHub allows only one callback URL.
  - `secret-placement`: the agent asks the learner to paste the client ID and client secret into the
    chat, saying it will put the ID in `frontend/.env` and set the secret on the backend host; or it
    reports that it has put both in the frontend's environment and asks to push. Either way the
    message says where the client ID goes, so the reply has to rule on both.
  - `too-much-scope`: the agent reports sign-in working, with a scope request larger than the app
    uses, and asks to push.
  - `sound-plan`: the agent reports what it built, all of it sound (as `sound-plan` in
    `a-critique-sign-in-plan`), and asks to push.
  - `leaked-secret`: the agent reports that the `.env` holding the client secret went out in a
    commit pushed to the public repository, says it has deleted the file in a new commit and added
    it to `.gitignore`, and asks if anything else is needed.
  How hard: Medium, the message says plainly what it did or wants; Hard, the message wraps it in a
  correct and reassuring status report ("Sign-in works on localhost and live, tests pass") or
  presents it as already handled securely, or, for `sound-plan`, is in agent jargon with one sound
  detail that looks alarming. A scenario carries all six cases, one question each, at least two at
  Hard. No question gives away another's answer.
- **worked example:** shown only as help when asked for, which records the attempt as helped: the
  tutor writes a reply to a different message aloud, saying first what the agent is about to do and
  where (browser, backend, provider, chat), then what the reply commits to. Same citations as in
  `a-critique-sign-in-plan`. First level of help on a real attempt: "if you say yes to this, what
  happens next, and where?"
- **doesn't show:** each message carries at most one thing wrong. A reply on paper is not the
  learner's behaviour with a real agent; a pass doesn't show they would stop to read a message this
  carefully mid-task. As in `a-critique-sign-in-plan`, nothing is registered. The
  `register-yourself` message asks what the registration yields, so it prompts the half of that
  case a plan review leaves the learner to volunteer.
- **offer as:** the same six things as plan review, met the way they really arrive: one message from
  your agent partway through, and you write the reply. Shorter questions, and closer to the moment
  you'll actually face.
- **note:** As in `a-critique-sign-in-plan`: in a message written live, any mention of registering the app or setting the client secret outside its own cases should say the learner does it. A reply that objects to the agent handling the secret, where the message left that unclear, is not a mistake.

### `a-sort-sign-in-steps`

- **serves:** `c-set-up-sign-in`
- **supports:** attempt
- **checks:** `c-set-up-sign-in`
- **artifact:** no external source. A made-up app and a deck of cards, each one step someone has
  proposed for adding sign-in to it, from this activity's bank or written live per the generator
  below. 1 to 2 minutes a card.
- **verified:** 2026-10-07
- **learner does:** reads the scenario's setup and the one card served, and puts it in one of three
  piles, saying why in one to three sentences: **yours** (you do it by hand, at the provider or in
  a host's settings), **your agent's, as written** (code or config your agent can do as the card
  says), or **change it first** (then says what to change it to, and who does the changed step).
  The fixed question under every card: "Which pile, and why? If you'd change it, say to what and
  who does it."
- **tutor role:** examiner
- **tutor does:** sets the card as served, without rewording it or hinting, and never says which
  pile it belongs in or how the deck divides among the piles. When run live, writes the key into
  the record before showing anything. Gives help whenever it is asked for, and records the attempt
  as helped. Labels the attempt with the question's path, or `a-sort-sign-in-steps/<case>-<level>`
  when run live, and records the case with `--cases`. After the last card of a sitting, asks the
  learner to state in one sentence the rule they sorted by; that sentence is not graded.
- **done when:** full credit on the question, with no help. The goal is met once each of its six
  cases has been passed.
- **generator:** a scenario's setup is the same shape as in `a-critique-sign-in-plan`: a made-up
  Problem Set 3 app, React on one made-up static host, Express on another, Postgres, one provider
  (Google or GitHub), what the app shows about a user, the live addresses and the localhost ports
  (5173 and 3001), and a line saying basic auth is being replaced with sign-in. It names the three
  piles as under `learner does` and says the cards are independent and come in no particular
  order. **Each question is one card**: one step, one to three sentences, sometimes with a
  config line or a URL, naming who does it only when the case below says so. A deck is 7 or 8
  cards.

  **Every card carries exactly one case**, and its key names the pile and what the answer must
  say:
  - `register-yourself`: the card is the registration step, "Create the OAuth app at <provider> for
    this app; the later steps use what it gives you", either with no actor named or with the agent
    as actor ("Your agent signs in to GitHub with your password and creates the OAuth app", or "...
    creates it in your browser, where you're already signed in"). Key: yours (for the agent
    version, change it first, to yours), and it gives a client ID and a client secret. Full credit
    needs the right pile and the two values. Half credit for one. Any reason, or none, counts for
    "yours".
  - `two-redirects`: the card gives the provider one redirect URL, localhost or live
    ("Register `http://localhost:3001/auth/github/callback` as the redirect URL"). Key: change it
    first: register a redirect URL for localhost and another for the live app (the backend's live
    address with the same path), as a second URL on the one registration or as a second
    registration; yours to do. As in `a-critique-sign-in-plan`, a GitHub OAuth app holds up to 10
    callback URLs and a Google client holds several redirect URIs, so adding the second URL to the
    one registration is the ordinary answer for either provider. Never write, on a card, a key or a
    rubric, that GitHub allows only one callback URL. Full credit needs both URLs named and that the learner gives the
    provider both. Half credit for naming the missing one with no way to give it to the provider,
    or for "yours" with only the one URL.
  - `secret-placement`: the card says where the client secret and the client ID go. Variants: both
    in the backend host's settings and the frontend's environment respectively, with no actor
    named (sound; key: yours, since the secret needs the learner's hands, and the ID in the
    frontend is fine; a learner who splits the card, the secret yours and the ID your agent's, has
    the pile right); both in
    `frontend/.env` (key: change it first); or "paste both into the chat and your agent sets them"
    (key: change it first). Key in every variant: the client secret goes into the backend host's
    settings (and the local `.env` that `.gitignore` keeps out of the repository) by the learner's
    own hand, never into the chat or the frontend; the client ID may go in the frontend. Full
    credit needs the right pile, where the secret goes and who puts it there, and that the client
    ID may be in the frontend. Half credit for the secret alone.
  - `too-much-scope`: the card is the scope line in the sign-in code, asking for more than the app
    shows (GitHub `repo` or `user`; Google Drive, Gmail, Calendar or Contacts on top of
    `openid profile`). Key: change it first, to only what the app shows (for GitHub no scope or
    `read:user`, with `user:email` if it uses email; for Google `openid profile`, with `email` if
    it uses email); your agent can make the change. Full credit needs the excess caught and a
    smaller request named in the learner's words. Half credit as in `a-critique-sign-in-plan`.
  - `sound-plan`: the card is the backend's sign-in step, all of it sound: "The backend sends the
    code <provider> sends back, with the client ID and client secret from its environment, to
    <provider>, learns who the user is (for GitHub by asking its API; for Google from the ID
    token), and finds or creates a `users` row keyed by `github_id` (or Google's `sub`), with no
    password column." Key: your agent's, as written. Full credit for that pile with a reason that
    doesn't call the step broken and no change that would break it (moving the exchange or the
    secret into React, adding a password, keying users by email). None otherwise.
  - `leaked-secret`: the card's setup line says the `.env` holding the client secret went out in a
    commit pushed to the public repository; the card is the proposed fix, "Delete `.env` in a new
    commit, add it to `.gitignore`, and push." Key: change it first: get a new client secret from
    the provider, put it where the old one was (the backend host's settings and the local `.env`),
    and delete or disable the old one at the provider; deleting it from the repository doesn't fix
    it, because it was already public. Full and half credit as in `a-critique-sign-in-plan`.

  A deck carries all six cases, one card each, plus one or two more cards repeating
  `secret-placement` or `sound-plan` in another variant, so the piles aren't one card each. How
  hard: Medium, the card says what happens in plain words; Hard, the card is a config or code line
  with a short agent comment, or justifies itself in plausible words ("so we can show their
  projects later"; "to save you a trip to the dashboard"), or, for a sound card, carries one detail
  that looks alarming to a novice (the client ID in `VITE_GITHUB_CLIENT_ID`). At least two cards at
  Hard. Cards are studied in file order, so a later card may give away an earlier card's answer,
  never the reverse: no card's text gives away the answer to a card after it.
- **worked example:** shown only as help when asked for, which records the attempt as helped: the
  tutor sorts a different card aloud, asking where the step happens (browser, backend, provider,
  host settings, chat), whose hands it needs, and what would go wrong if the agent did it as
  written. Same citations as in `a-critique-sign-in-plan`. First level of help: "where does this
  step happen, and whose account does it need?"
- **doesn't show:** one step at a time, so the learner never has to find the step that matters
  inside a plan, and the piles themselves say some steps are the learner's, which prompts the
  `register-yourself` and `secret-placement` answers a plan review leaves them to notice. A pass
  shows they can place each step, not that they would catch one in a longer plan; plan review
  shows more. Nothing is registered.
- **offer as:** the quickest and most structured check: one step at a time, sort it into yours,
  your agent's, or change it first. A good way in before plan review, which shows more.
- **note:** For a card with no actor named that belongs to the learner (the registration step, or the sound placement of the secret and the ID), "change it first" with the change being "I do this myself" is the same answer as "yours". Credit it as the right pile.

### `a-critique-permissions-plan`

- **serves:** `c-review-permissions`
- **supports:** attempt
- **checks:** `c-review-permissions`
- **artifact:** no external source. A made-up app with its routes, and a who-may-do-what table and
  short excerpts of an agent's plan for enforcing it, from this activity's bank or written live per
  the generator below. 2 to 4 minutes a question.
- **verified:** 2026-10-07
- **learner does:** reads the scenario's setup and the one question served, and answers in two to
  four sentences. A table or plan question ends: "Would you agree to this as it stands? If not, what
  would you change?" A confirming question ends: "Which request would you make to show this rule
  holds, and what should it get back?"
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never says
  whether a table or plan has anything wrong with it. When run live, writes the key into the record
  before showing anything. Gives help whenever it is asked for, and records the attempt as helped.
  Labels the attempt with the question's path, or `a-critique-permissions-plan/<case>-<level>` when
  run live, and records the case with `--cases`.
- **done when:** full credit on the question, with no help. The goal is met once each of its eight
  cases has been passed.
- **generator:** a scenario is one made-up app shaped like Problem Set 3, Part B: React on a made-up
  static host, Express on a made-up server host, Postgres, sign-in through Google or GitHub already
  working, with a line on what the app does (a club events board, a lost-and-found board, a shared
  reading list). The setup lists the backend's routes, 5 to 7 lines such as `GET /api/events`,
  `POST /api/events`, `PATCH /api/events/:id`, `DELETE /api/events/:id`, `GET /api/me`, with one
  line each on what they do, and names the app's signed-in levels only: a signed-in user, the owner
  of a record, and one admin level (such as the club's officers). It never names, lists or hints
  at someone not signed in as a level, so `missing-signed-out` tests whether the learner thinks of
  the signed-out visitor unprompted. It says the questions are independent. **Each question is a separate piece of the work**: a who-may-do-what
  table as it would appear in `DEPLOY.md` (rows are actions, columns are levels, cells yes or no),
  or a table with an excerpt of the agent's plan for enforcing it (4 to 8 numbered steps, with route
  and middleware names and short code lines where an agent would give them), or, for the confirming
  cases, a line saying the agent reports the rules are in place.

  **Every question carries exactly one case**, named on its rubric `cases:` line. Every table row
  and plan step but the one the case fixes is sound, and every table but the `missing-action` and
  `missing-signed-out` ones is complete: a row for every action the setup's routes allow, and a
  column for each signed-in level and for someone not signed in:
  - `missing-action`: the table alone, with every level's column, missing a row for an action the
    setup's routes allow (most often delete, or editing someone else's record). Key: names the
    missing action and what the row should say (for example, who may delete). Full credit needs
    both. Half credit for naming the action with no rule for it.
  - `missing-signed-out`: the table alone, with a row for every action, but no column for someone
    not signed in; its columns start at a signed-in user. Key: names the missing level and what its
    column should say (that someone not signed in may only read, or may do nothing). Full credit
    needs both. Half credit for naming the level with no rule for it.
  - `react-only`: the plan enforces an owner-only rule by hiding a button in React
    (`{user.id === event.ownerId && <EditButton />}`), while the route that does the change checks
    only that someone is signed in. Key: the server must check the rule on that route too, because
    anyone signed in can send the request without the page. Full credit needs the route named (or
    the action) and the server check. Half credit for saying the button isn't enough with no fix.
  - `unchecked-route`: the plan puts the sign-in check on every route that changes data but one
    (most often `DELETE`, or a `PATCH` added late). Key: names that route and that it needs the
    check. Full credit needs the route; half credit for "check all routes" with none named.
  - `trusts-frontend`: the server decides who is asking from something the frontend sends: a
    `userId` in the request body, a `?user=` query, or an `x-user-id` header the React code sets.
    Key: the server must take the user from the session, since anyone can send any id. Full credit
    needs both: what's wrong and that the session is where the user comes from. Half credit for one.
  - `sound-plan`: every route that changes data checks sign-in on the server, every owner or admin
    rule is checked on the server against the session's user, React hides buttons as well, and the
    `users` table keeps the provider's id, a name, perhaps an email, and a role column. Key: agree as
    it stands. Full credit when they agree and ask for no change that would break it (moving checks
    into React, taking the user id from the request, storing passwords). A harmless suggestion costs
    nothing. None otherwise.
  - `confirm-401`: the agent reports the rules are in place; the question asks how to show that
    someone not signed in is turned away from one action the scenario names. Key: send that request
    (method and path) with no sign-in, for example from a terminal with no session cookie, and it
    should get 401. What the page shows signed out (a missing button, a redirect to sign-in) doesn't
    count. Full credit needs the request and 401. Half credit for one.
  - `confirm-403`: as `confirm-401`, for showing that a signed-in user who isn't the owner is
    refused the owner's action. Key: sign in as a second account and send that request (for
    example, `DELETE` on the owner's record) and it should get 403. Full credit needs a second,
    signed-in account, the request, and 403. Half credit when one is off (signed out instead, or 401,
    or what the page shows).

  How hard: Medium, the table or step the case fixes is stated in plain words, or the confirming
  question just asks. Hard, Medium plus one of: the flaw shows only in a route or code line among
  sound ones (`router.delete('/api/events/:id', deleteEvent)` beside lines carrying
  `requireAuth`); the agent justifies it ("React already hides the button, so the route stays
  simple"); or, for the confirming cases, the agent offers its own check, of what the page shows
  ("I signed out and the Delete button is gone"), and the question asks whether that confirms it and
  what they would do instead. **`missing-action` and `missing-signed-out` never share a scenario**:
  each table is complete in the other's respect, so either one beside the other gives the other's
  answer away. A scenario carries one of the two, plus each of the other six cases, one question
  each, every one at Medium or Hard and at least two at Hard; the bank as a whole carries all eight,
  so it holds at least two scenarios, one for each table case. Questions are studied in file order,
  so a later question may give away an earlier one's answer, never the reverse: write the
  scenario's table case first, since later questions show complete tables (a column for someone
  not signed in, a row for every action). No question's text gives away the answer to a question
  after it.
- **worked example:** shown only as help when asked for, which records the attempt as helped. Work a
  different question aloud: for each row of the table, ask "who could send this request, from
  where, without the page?" and "what does the server look at to decide?" Cite OWASP's "A01:2025
  Broken Access Control", https://top10.owasp.org/2025/A01_2025-Broken_Access_Control, Description
  and the opening of How to prevent ("only effective when implemented in trusted server-side
  code"); for the status codes, MDN's 401 and 403 pages,
  https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/401 and
  https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status/403. First level of help on a
  real attempt: "could someone do this without using your page at all?"
- **doesn't show:** each question holds at most one thing wrong, and the setup's route list makes
  `missing-action` a matter of checking against a list the learner is handed; writing a table for
  their own app from nothing is Part B's job. The setup names only the signed-in levels, so
  `missing-signed-out` does show the learner thinking of the signed-out visitor unprompted, but
  only for a table question set first in its scenario, before any complete table. Naming a confirming request is not making it, so a pass
  doesn't show they could send a request with no session cookie, or sign in a second account, on a
  live app.
- **offer as:** plan review for who may do what: a table or a short plan, and you say what you'd
  change, or which request would prove it. One question per thing that could be wrong, 2 to 4
  minutes each.

### `a-contrast-permission-plans`

- **serves:** `c-review-permissions`
- **supports:** attempt
- **checks:** `c-review-permissions`
- **artifact:** no external source. A made-up app and pairs of versions of one piece of the work, A
  and B, from this activity's bank or written live per the generator below. 2 to 3 minutes a
  question.
- **verified:** 2026-10-07
- **learner does:** reads the setup and the one pair served, and answers: "Would you agree to A, B,
  or both? What gives it away?" For the confirming pairs, also says what the request they chose
  should get back.
- **tutor role:** examiner
- **tutor does:** sets the pair as served, without rewording it or hinting, and never says how many
  of the two are sound. When run live, writes the key into the record before showing anything.
  Gives help whenever it is asked for, and records the attempt as helped. Labels the attempt with
  the question's path, or `a-contrast-permission-plans/<case>-<level>` when run live, and records the
  case with `--cases`.
- **done when:** full credit on the question, with no help. The goal is met once each of its eight
  cases has been passed.
- **generator:** a scenario's setup is the same shape as in `a-critique-permissions-plan`: a made-up
  Problem Set 3 app with its routes and levels. **Each question is one pair**, A and B, two versions
  of the same piece, the same length and wording except where they differ, with the sound one at A
  or B at random. Every question carries exactly one case:
  - `missing-action`: two tables, one complete, one missing the row for an action the routes allow
    (most often delete). Key: the complete one, and the action the other leaves out.
  - `missing-signed-out`: two tables, one complete, one with no column for someone not signed in.
    Key: the complete one, and that the other leaves out someone who isn't signed in.
  - `react-only`: two plan steps for an owner-only rule: one hides the button in React only, the
    other hides it and checks ownership on the route. Key: the one with the server check, because
    the request can be sent without the page.
  - `unchecked-route`: two route lists, identical except that one leaves a data-changing route
    without the sign-in middleware. Key: the complete one, and the route the other leaves open.
  - `trusts-frontend`: two versions of one route handler, one taking the user from the session
    (`req.session.userId`), the other from the request (`req.body.userId`, or a header). Key: the
    session one, and that the other believes whatever id it is sent.
  - `sound-plan`: two sound plans that differ harmlessly (a middleware against a check inside each
    handler; keeping the email or not; one admin role column against an admins table). Key: both.
    No reason is required: full credit for "both" with no reason at all, or with any reason that
    doesn't call either broken; none for rejecting one.
  - `confirm-401`: two ways to confirm someone not signed in is turned away: one looks at the page
    signed out (the button is gone), the other sends the request with no sign-in, with its expected
    status left out. Key: the request, and that it should get 401.
  - `confirm-403`: two ways to confirm a non-owner is refused: one sends the owner's action while
    signed out, the other sends it signed in as a second account, status left out. Key: the second
    account, and that it should get 403 (the signed-out version would show 401, which proves a
    different rule).
  Credit: full when the choice is right and what gives it away (or the status code, for the
  confirming cases) matches the key; half when the choice is right with no reason or a wrong one;
  none otherwise. `sound-plan` is the exception: its own credit line above holds, and "both" with
  no reason is full credit. How hard: Medium, the difference between A and B sits in a plain-words line; Hard,
  it sits in one code or route line in otherwise identical blocks, or the unsound version carries the
  agent's reassuring comment. A scenario carries all eight cases, one question each, at least two at
  Hard. No question gives away another's answer.
- **worked example:** shown only as help when asked for, which records the attempt as helped: the
  tutor works a different pair aloud, finding the one line where A and B differ and asking who could
  exploit it. Same citations as in `a-critique-permissions-plan`. First level of help: "where exactly
  do A and B differ?"
- **doesn't show:** the pair points the learner at the one place that matters, and a sound version
  sits beside every unsound one, so a pass shows recognition, not that they would catch the flaw in a
  plan on its own; `a-critique-permissions-plan` is the stronger check. A choice between two is
  guessable; the "what gives it away" half of the credit is what guards against that, and only
  partly.
- **offer as:** the gentler check: two versions side by side, pick the one you'd agree to and say
  why. Quicker than plan review, and a good first try; plan review shows more.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
