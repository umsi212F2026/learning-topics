Pantrybook is in the second arrangement: one host, Fernlatch, running the frontend (`pantry-web`,
static files) and the backend (`pantry-api`) as two services that build and deploy separately,
with the database in the same project. So when the backend is down or unreachable, the page still
loads from `pantry-web`, and what fails is everything that needs data: the recipe list, search,
tags, the dinner plan. Two host facts in the setup decide visitor answers: a failed new deploy of
either service leaves that service's previous version serving, and Fernlatch takes up to about a
minute to start `pantry-api` after 20 idle minutes. Here the build that fails is the backend's
(`npm ci`), not the frontend's.

One case per question: q1 `waking` (Medium), q2 `failed-start` (Hard, visitor answer turns on the
previous version still serving), q3 `cors-blocked` (Medium), q4 `local-only` (Medium, lines from
`server/` only), q5 `failed-build` (Medium), q6 `wrong-address` (Hard, red herring: a database
error from two days earlier), q7 `request-error` (Hard, red herring: a deprecation warning in the
build log of the deploy that went live). A remark on how to fix any of these is neither credited
nor counted against the learner.

### q1

- **goal:** `c-locate-failure`
- **cases:** waking
- **answer:** Nothing has failed. `pantry-api` had been stopped after 20 idle minutes, and the
  first request after lunch started it again, which took about 45 seconds. A visitor right now gets
  the working app; the first visitor after a quiet spell sees the loading spinner for up to about a
  minute, then everything works.
- **credit:** full when they say nothing has failed (the backend was starting up after being idle)
  and that a visitor gets a wait on the first load after a quiet spell, then normal use. Half when
  one of the two is right: for example, they call it a slow start but say visitors now see errors,
  or they get the wait right but call it a failure at start. None otherwise.
- **tutor note:** if they call it a failure, ask what status every request after 13:41:49
  returned.

### q2

- **goal:** `c-locate-failure`
- **cases:** failed-start
- **answer:** The new backend deploy built but never came up where Fernlatch looks for it: it
  listened on port 3000, the health check on 8080 got no answer, and Fernlatch stopped it. Fernlatch
  kept the previous deploy, `#60`, serving throughout, so visitors see Pantrybook as it was before
  the push, working, with recipes in the old order; to them it looks like nothing happened.
- **credit:** full when they say the new backend deploy didn't start (it never answered its health
  check, after a build that succeeded) and that visitors still get the previous version, working,
  without the change. Half when one of the two is right: for example, the kind right but saying the
  site or its data is down, which the account rules out, or the visitor half right but placing it
  at the build. None otherwise.
- **tutor note:** if they say visitors get errors, ask which deploy the account says Fernlatch was
  routing traffic to.

### q3

- **goal:** `c-locate-failure`
- **cases:** cors-blocked
- **answer:** The frontend can't reach the backend: `pantry-api` gets the request and answers 200,
  but the browser blocks the answer under CORS because the allowed origin it sends ends in `.app`
  and the page is on `.io`. Every visitor sees the Pantrybook page load, but the recipe list stays
  empty and nothing that needs the backend works.
- **credit:** full when they say the page's calls to the backend aren't getting through to the
  page (naming CORS or the mismatched origin is welcome and not required) and that visitors see the
  page but none of its data or actions. Half when one of the two is right. None otherwise,
  including saying the backend failed to start after the restart or errored, which its log rules
  out.
- **tutor note:** if they say the restart broke the backend, ask what `pantry-api` logged for the
  request at 09:14:07.

### q4

- **goal:** `c-locate-failure`
- **cases:** local-only
- **answer:** The account isn't evidence about the deployed app. All it quotes is a file under
  `server/`, and nothing from Fernlatch, so it can't say what `pantry-api` is actually running or
  doing, where a deployed failure happened, or what a visitor sees.
- **credit:** full when they say the account isn't evidence about the deployed app, for whatever
  reason they give that fits (it's only the code, nothing is quoted from Fernlatch). Saying the
  agent should read Fernlatch's logs is welcome and not required. None when they take the agent's
  conclusion as where the deployed app went wrong, whatever kind and visitor answer they give.
- **tutor note:** if they accept the account, ask which of its lines came from Fernlatch.

### q5

- **goal:** `c-locate-failure`
- **cases:** failed-build
- **answer:** The backend's build of the new commit failed on Fernlatch (`npm ci` stopped because
  the lock file is out of date), so the new deploy never went out. Visitors see Pantrybook as it
  was, working, with search matching titles only.
- **credit:** full when they say the build of the new commit failed and that visitors still get
  the previous version, unchanged, without ingredient search. Half when one of the two is right:
  for example, the build is right but they say search or the site is now broken, or the visitor
  half is right but they place the failure at start or at a request. None otherwise.
- **tutor note:** if they say visitors see an error, ask which deploy of `pantry-api` is
  `Running`.

### q6

- **goal:** `c-locate-failure`
- **cases:** wrong-address
- **answer:** The frontend can't reach the backend: the deployed page calls
  `pantry-apl.fernlatch.io`, a misspelled host name that doesn't resolve, so no request reaches
  `pantry-api`, which has logged nothing since Oct 03. The duplicate-key error is from two days
  earlier and was answered with a 409. Every visitor sees the Pantrybook page load, but the recipe
  list stays empty and nothing that needs the backend works.
- **credit:** full when they say the frontend's calls aren't getting to the backend (naming the
  misspelled address is welcome and not required) and that visitors see the page but none of its
  data or actions. Half when one of the two is right. None otherwise, including blaming the
  `duplicate key` error or saying the backend is stopped and waking, which the empty log since the
  page load rules out.
- **tutor note:** if they fix on the `duplicate key` line, ask what date it was logged and when
  the list went empty.

### q7

- **goal:** `c-locate-failure`
- **cases:** request-error
- **answer:** Both services deployed and are running; one request, `GET /api/plans/week/...`,
  errors in the backend (a `TypeError` with a stack trace in `routes/plans.js`). The `npm WARN
  deprecated` line is a warning in a build that succeeded. Visitors can use Pantrybook, browse and
  open recipes, but the new dinners page shows an error.
- **credit:** full when they say the app is running and the week-plan request errors on the
  server, and that the rest of the app works for visitors while that page fails. Half when one of
  the two is right, including the kind right but no word on whether the rest of the app works, or
  the visitor half right but blaming the build warning. None otherwise.
- **tutor note:** if they blame the `npm WARN` line, ask what the build's last line says and what
  status the deploy has.
