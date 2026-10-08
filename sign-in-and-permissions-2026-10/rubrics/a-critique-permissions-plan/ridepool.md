The sound table has a column for someone not signed in, who may see the rides and nothing else, and
a row for each of the six routes. Members may offer a ride and join one; only a ride's driver and
the trip leaders may edit or cancel it. Every rule has to hold on the server, against the user the
session names, because anyone signed in can send any of these requests from a terminal without the
page. This scenario's table case is `missing-action`, set first so that no complete table has been
seen before it, and the action it leaves out is joining a ride, a member's action rather than an
owner's; it never carries `missing-signed-out`. Levels: `draft-table` Medium, `edit-ride` Medium,
`who-is-asking` Medium, `routes-file` Hard (the flaw is one route line among sound ones),
`whole-plan` Medium, `confirm-cancel` Medium, `confirm-join` Hard (the agent offers its own check of
what the page does). Each question has one thing wrong at most; a learner who also flags something
sound costs nothing unless the change they ask for would break the plan.

### draft-table

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** Not as it stands: it has no row for joining a ride, though
  `POST /api/rides/:id/riders` allows it. Add one: someone not signed in, no; a signed-in member,
  yes; a ride's driver, yes; a trip leader, yes.
- **credit:** full for naming the missing action (joining a ride) and what its row should say:
  that signed-in members may and someone not signed in may not. A rule that also keeps a driver
  from joining their own ride is fine. Half for naming the action with no rule for it, or with a
  rule that lets someone not signed in join. None for agreeing to the table.
- **tutor note:** if they go looking for a missing delete or edit row, ask them to go down the
  route list and find each route's row. If they tinker with a row that is there (say, members
  shouldn't offer rides), ask the same.

### edit-ride

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** No: step 4 leaves editing a ride to React, and step 5's `PATCH /api/rides/:id`
  checks only that someone is signed in. That route must check on the server, as cancelling does
  in step 3, that the signed-in user is the ride's driver or a trip leader, and refuse the request
  otherwise, because any signed-in member can send that `PATCH` without the page.
- **credit:** full for naming the route or the action (editing a ride) and saying the server must
  check driver-or-trip-leader on it. Half for saying hiding the button isn't enough with no fix, or
  a fix that stays in React.
- **tutor note:** if they agree because the button is hidden, ask: "could someone change the
  meeting spot on Marco's ride without using your page at all?" A reply asking to remove the React
  check is not the fix; the Edit button should stay hidden as well.

### who-is-asking

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** No: the server takes the user from `userId` in the request body, which anyone signed
  in can set to someone else's id, and then edit or cancel that person's rides, or offer and join
  rides in their name. The server must take the user from the session (`req.session.userId`), not
  from anything the request carries; drop `userId` from the body.
- **credit:** full for both: what's wrong (the server believes an id the request sends, which
  anyone can change) and that the user should come from the session. Half for one of the two.
- **tutor note:** "our React code always sends the right id" is the trap; ask whether a request has
  to come from React. If they say `requireAuth` already stops this, ask whose id the body would
  hold when a signed-in member sends someone else's.

### routes-file

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** No: `router.post('/api/rides/:id/riders', joinRide)` has no `requireAuth`, so someone
  not signed in can join a ride and take a seat. Give it `requireAuth`, as the other routes that
  change data have.
- **credit:** full for naming the riders route (or joining a ride) as the one that needs the
  sign-in check. Half for "check all routes" or "make sure every route is protected" with none
  named.
- **tutor note:** if they point at step 5 and say the Join button is hidden from signed-out
  visitors, ask who could send that `POST` without the page. A learner who also asks for
  `requireDriverOrLeader` on it would stop members joining rides; ask what the table says a member
  may do. `GET /api/rides` having no middleware is correct: anyone may see the rides.

### whole-plan

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Yes, as it stands. Every route that changes data checks sign-in on the server; edit
  and cancel check driver-or-trip-leader against the session's user; offering and joining take the
  user from the session; React hides the buttons as well; and `users` keeps Google's id and the
  email the riders need, not a password.
- **credit:** full when they agree and ask for no change that would break it (moving a check into
  React only, taking the user id from the request, adding a password column). A harmless
  suggestion (an index on `google_id`, a test for each rule, checking `role` in a middleware of its
  own) costs nothing. None otherwise.
- **tutor note:** a learner who refuses because `GET /api/rides` has no `requireAuth` has misread
  the table, which lets someone not signed in see the rides; ask them to find that row. One who
  refuses because the email is stored should be asked what the setup says riders see.

### confirm-cancel

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** Sign in as a second member, one who isn't the ride's driver and isn't a trip leader,
  and send `DELETE https://ridepool-api.burrowhost.com/api/rides/<its id>` with that account's
  session. It should get 403.
- **credit:** full for all three: a second account, signed in, that isn't the driver; the request
  (cancelling that ride, method and path or plainly that request); and 403. Half when one is off:
  signed out instead of a second account, 401 instead of 403, or checking what the page shows
  instead of sending the request.
- **tutor note:** if they send the `DELETE` signed out, ask what that would show: it gets 401 and
  proves the sign-in rule, not the driver rule. If their second account is a trip leader, ask what
  the table says a trip leader may do.

### confirm-join

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** No: the agent's check only shows what the page does when you click Join signed out.
  Send `POST https://ridepool-api.burrowhost.com/api/rides/<a ride's id>/riders` with no sign-in,
  for example from a terminal with no session cookie. It should get 401.
- **credit:** full for the request (joining a ride on the backend, method and path, or plainly that
  request, with no session) and 401. Half for one of the two: the request with a wrong or no
  status, or 401 with a check of what the page does. None for accepting the agent's check with
  nothing else. Don't require a verdict on the agent's check stated separately: a reply that goes
  straight to the right request has answered it.
- **tutor note:** if they repeat the agent's check another way (another browser, clearing cookies
  and clicking), ask whether someone could send that request without the page. The full address is
  not required; `POST /api/rides/:id/riders` with no cookie is enough. A learner who expects 403
  should be asked whether the server knows who is asking at all.
