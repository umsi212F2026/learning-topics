Roomly is in the first arrangement: the frontend on one host (Pagewell, static files), the
backend and database on another (Kettlerun). So when the backend is down or unreachable, the page
itself still loads from Pagewell, and what fails is everything that needs data: the room list,
search results, booking. Two host facts in the setup decide visitor answers: a failed new deploy
leaves the previous version serving on either host, and Kettlerun takes up to about a minute to
start a backend that has been idle 15 minutes. q5 turns on the account's own statement that a
settings restart is not a new deploy, so nothing else is serving.

One case per question: q1 `failed-build` (Medium), q2 `request-error` (Medium), q3
`wrong-address` (Medium), q4 `waking` (Hard, red herring: last night's database timeout), q5
`failed-start` (Hard, visitor answer turns on no previous version serving), q6 `local-only` (Hard,
"I reproduced it" with nothing from the host), q7 `cors-blocked` (Medium). A remark on how to fix
any of these is neither credited nor counted against the learner.

### q1

- **goal:** `c-locate-failure`
- **cases:** failed-build
- **answer:** The frontend's build on Pagewell failed (Vite couldn't resolve an import), so the new
  deploy never went out. Visitors see last Tuesday's version, unchanged and working, with no
  building filter.
- **credit:** full when they say the build of the new commit failed and that visitors still get
  the previous version, unchanged, without the filter. Half when one of the two is right: for
  example, the build is right but they say the site is down or broken, or the visitor half is
  right but they place the failure at start or at a request. None otherwise.
- **tutor note:** if they say visitors see an error, ask what Pagewell is still serving at
  `roomly.pagewell.app` while `3e7b0d4` sits at `HALTED`.

### q2

- **goal:** `c-locate-failure`
- **cases:** request-error
- **answer:** The app is deployed and running; one request, `POST /api/bookings`, errors in the
  backend (a `TypeError` with a stack trace in `routes/bookings.js`). Visitors can load the app and
  browse and search rooms, but booking a room fails: the button shows an error or does nothing.
- **credit:** full when they say the app is running and the booking request errors on the server,
  and that the rest of the app works for visitors while booking fails. Half when one of the two is
  right, including the kind right but no word on whether the rest of the app works. None
  otherwise.
- **tutor note:** if they say the backend is down, ask what the `GET /api/rooms 200` lines on
  either side of the error tell them.

### q3

- **goal:** `c-locate-failure`
- **cases:** wrong-address
- **answer:** The frontend can't reach the backend: the deployed page calls `localhost:3001`
  instead of `roomly-api.kettlerun.net`, so no request reaches the backend. Every visitor sees the
  Roomly page load, but the room list stays empty and nothing that needs the backend works.
- **credit:** full when they say the frontend's calls aren't getting to the backend (naming the
  wrong or local address is welcome and not required) and that visitors see the page but none of
  its data or actions. Half when one of the two is right. None otherwise, including saying the
  backend failed to start or errored, which its log rules out.
- **tutor note:** if they say it only fails on the phone, ask which machine `localhost` means in a
  visitor's browser.

### q4

- **goal:** `c-locate-failure`
- **cases:** waking
- **answer:** Nothing has failed. The backend had been stopped after a quiet spell, and this
  morning's first request started it again, which took about 40 seconds. The `ETIMEDOUT` from last
  night is unrelated and recovered. A visitor right now gets the working app; the first visitor
  after a quiet spell waits up to about a minute for the data, then everything works.
- **credit:** full when they say nothing has failed (the backend was starting up after being idle)
  and that a visitor gets a wait on the first load after a quiet spell, then normal use. Half when
  one of the two is right: for example, they call it a slow start but say visitors now see errors,
  or they get the wait right but blame the database timeout. None otherwise.
- **tutor note:** if they fix on the `ETIMEDOUT`, ask what time it was logged and what the next
  line says.

### q5

- **goal:** `c-locate-failure`
- **cases:** failed-start
- **answer:** The backend fails as it starts: `server/db.js` throws because `DB_URL` is no longer
  set, the process exits, and Kettlerun keeps restarting it. Because this was a settings restart
  of the running deploy, no previous version is serving. Visitors get the Roomly page from
  Pagewell, but the room list and everything that needs data fails, since Kettlerun answers the
  backend's address with a 503.
- **credit:** full when they say the backend can't start (it exits on start-up) and that visitors
  get the page but no working data, because nothing is serving the backend. Half when one of the
  two is right, including the kind right but saying visitors still get the previous version, which
  the account rules out. None otherwise.
- **tutor note:** if they say the old version is still serving, ask what the account says about a
  settings restart, and whether it is a new deploy.

### q6

- **goal:** `c-locate-failure`
- **cases:** local-only
- **answer:** The account isn't evidence about the deployed app. Every line it quotes comes from a
  run on the laptop (`localhost:3001`, a `/Users/you/...` path), not from Kettlerun, so it can't say
  where the deployed app failed or what a visitor sees.
- **credit:** full when they say the account isn't evidence about the deployed app, for whatever
  reason they give that fits (it's from the laptop, nothing is quoted from Kettlerun). Saying the
  agent should read Kettlerun's logs is welcome and not required. None when they take the agent's
  conclusion as where the deployed app went wrong, whatever kind and visitor answer they give.
- **tutor note:** if they accept "I reproduced it", ask where the server that printed
  `Listening on http://localhost:3001` was running.

### q7

- **goal:** `c-locate-failure`
- **cases:** cors-blocked
- **answer:** The frontend can't reach the backend: the backend gets the request and answers 200,
  but the browser blocks the answer under CORS because the new deploy no longer sends
  `Access-Control-Allow-Origin`. Every visitor sees the Roomly page load, but the room list stays
  empty and nothing that needs the backend works.
- **credit:** full when they say the page's calls to the backend aren't getting through to the
  page (naming CORS is welcome and not required) and that visitors see the page but none of its
  data or actions. Half when one of the two is right. None otherwise, including saying the request
  errors on the server, which the `200` rules out.
- **tutor note:** if they say the backend is broken, ask what status Kettlerun logged for that
  request.
