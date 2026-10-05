Rosterpin is in the first arrangement, like Roomly, but with different host behaviour: the
frontend on Glintpage (static files), the backend and database on Moorbolt. When the backend is
down or unreachable, the page still loads from Glintpage, and what fails is everything that needs
data: the trip list, seats, sign-up. Three host facts in the setup decide visitor answers: a
failed build leaves the previous version serving on either host; Moorbolt stops the running
backend before starting a new one, so a new backend that won't start leaves nothing serving; and
Moorbolt takes up to about half a minute to start a backend that has been idle 10 minutes. Here
the failed build is the frontend's, on the first deploy, so there is no earlier version.

One case per question: q1 `request-error` (Medium), q2 `cors-blocked` (Medium, an explained red herring: a
deprecation warning in the build log of the release that went live), q3 `failed-start` (Medium),
q4 `waking` (Medium), q5 `local-only` (Hard, "I've confirmed ... on the live site" with only lines
from `server/`), q6 `failed-build` (Hard, the first deploy, so nothing is at the address), q7
`wrong-address` (Medium). A remark on how to fix any of these is neither credited nor counted
against the learner.

### q1

- **goal:** `c-locate-failure`
- **cases:** request-error
- **answer:** The app is deployed and running; one request, the seats for trip 48, errors in the
  backend (a `TypeError` with a stack trace in `routes/seats.js`). Visitors can load Rosterpin, see
  the trip list and sign up for other trips, but opening the Saturday trip shows an error.
- **credit:** full when they say the app is running and that one trip's request errors on the
  server, and that the rest of the app works for visitors while that trip's page fails. Half when
  one of the two is right, including the kind right but no word on whether the rest of the app
  works. None otherwise.
- **tutor note:** if they say the backend is down, ask what the lines on either side of the error
  returned.

### q2

- **goal:** `c-locate-failure`
- **cases:** cors-blocked
- **answer:** The frontend can't reach the backend: the new release built and is serving, gets the
  request and answers 200, but the browser blocks the answer under CORS because it goes out with
  no `Access-Control-Allow-Origin` header. The `npm WARN deprecated` line is a warning in a build
  that succeeded. Every visitor sees the Rosterpin page load, but the trip list stays empty and
  nothing that needs the backend works.
- **credit:** full when they say the page's calls to the backend aren't getting through to the
  page (naming CORS is welcome and not required) and that visitors see the page but none of its
  data or actions. Half when one of the two is right. None otherwise, including blaming the build
  warning or saying the request errors on the server, which the `200` rules out.
- **tutor note:** if they blame the `rimraf` line, ask what the release's status is and what
  status Moorbolt logged for the request.

### q3

- **goal:** `c-locate-failure`
- **cases:** failed-start
- **answer:** The backend fails as it starts: the build succeeded, then `node server/index.js`
  exits because `nodemailer` isn't installed at run time. Moorbolt had already stopped the previous
  release, so nothing is serving the backend. Visitors get the Rosterpin page from Glintpage, but
  the trip list and everything that needs data fails, since Moorbolt answers the backend's address
  with a 502.
- **credit:** full when they say the backend can't start (it exits on start-up) and that visitors
  get the page but no working data, because nothing is serving the backend. Half when one of the
  two is right, including the kind right but saying visitors still get the previous version, which
  the account and setup rule out. None otherwise.
- **tutor note:** if they say the old version is still serving, ask what the account says Moorbolt
  did with `r-225`.

### q4

- **goal:** `c-locate-failure`
- **cases:** waking
- **answer:** Nothing has failed. The backend had no instances after ten idle minutes, and the
  first request at the meeting started one, which took about half a minute. A visitor right now
  gets the working app; the first visitor after a quiet spell waits up to about half a minute for
  the trip list, then everything works.
- **credit:** full when they say nothing has failed (the backend was starting up after being idle)
  and that a visitor gets a wait on the first load after a quiet spell, then normal use. Half when
  one of the two is right: for example, they call it a slow start but say visitors now see errors,
  or they get the wait right but call it a failure at start. None otherwise.
- **tutor note:** if they call it a failure, ask what status every request after 19:47:29
  returned.

### q5

- **goal:** `c-locate-failure`
- **cases:** local-only
- **answer:** The account isn't evidence about the deployed app. Despite "I've confirmed ... on
  the live site", all it quotes is a file under `server/`, and nothing from Moorbolt, so it can't
  say what release is running or what the deployed app did.
- **credit:** full when they say the account isn't evidence about the deployed app, for whatever
  reason they give that fits (it's only the code, nothing is quoted from Moorbolt). Saying the
  agent should read Moorbolt's logs is welcome and not required. None when they take the agent's
  conclusion as where the deployed app went wrong, whatever kind and visitor answer they give.
- **tutor note:** if they accept "I've confirmed", ask which of its lines came from Moorbolt.

### q6

- **goal:** `c-locate-failure`
- **cases:** failed-build
- **answer:** The frontend's build on Glintpage failed (a JSX tag mismatch in `Trips.jsx`), so
  nothing was published. Since this is the first deploy, there is no earlier version: a club member
  following the link gets no Rosterpin at the address, only Glintpage's own not-found or error
  page. The backend being up on Moorbolt doesn't change that.
- **credit:** full when they say the frontend's build failed and that visitors get no app at the
  address, because there was no earlier version to keep serving. Half when one of the two is
  right: for example, the build is right but they say visitors see the previous version or the
  page without data, or the visitor half is right but they place the failure elsewhere. None
  otherwise.
- **tutor note:** if they say visitors see an earlier version, ask what the question's first line
  says about earlier deploys.

### q7

- **goal:** `c-locate-failure`
- **cases:** wrong-address
- **answer:** The frontend can't reach the backend: the deployed page calls the backend's old name,
  `rosterpin-server.moorbolt.dev`, which no longer resolves, so no request reaches `rosterpin-api`.
  Every visitor sees the Rosterpin page load, but the trip list stays empty and nothing that needs
  the backend works.
- **credit:** full when they say the frontend's calls aren't getting to the backend (naming the
  old address is welcome and not required) and that visitors see the page but none of its data or
  actions. Half when one of the two is right. None otherwise, including saying the backend failed
  to start or is waking, which its `serving` status and empty request log rule out.
- **tutor note:** if they say the backend is stopped, ask whether any request arrived at it during
  the agent's page load.
