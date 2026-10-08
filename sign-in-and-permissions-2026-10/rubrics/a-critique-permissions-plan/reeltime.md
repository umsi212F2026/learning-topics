The sound table has a column for someone not signed in, who may see the screenings and nothing
else (or, on a stricter reading, nothing at all), and a row for each of the six routes. Members may
post and say they're going; only a screening's owner and the officers may edit or delete it. Every
rule has to hold on the server, against the user the session names, because anyone signed in can
send any of these requests from a terminal without the page. This scenario's table case is
`missing-signed-out`, set first so that no complete table has been seen before it; it never carries
`missing-action`. Levels: `signed-out-table` Medium, `edit-button` Hard (the agent justifies the
gap), `routes-file` Hard (the flaw is one route line among sound ones), `who-is-asking` Medium,
`whole-plan` Medium, `confirm-signed-out` Medium, `confirm-not-owner` Hard (the agent offers its own
check of what the page shows). Each question has one thing wrong at most; a learner who also flags
something sound costs nothing unless the change they ask for would break the plan.

### signed-out-table

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** Not as it stands: it leaves out someone who isn't signed in. Add a column for them:
  they may see the screenings and nothing else (no posting, editing, deleting, saying they're
  going, or `GET /api/me`).
- **credit:** full for naming the missing level (someone not signed in, a visitor, a signed-out
  user) and what its column should say: that they may only see the screenings, or may do nothing.
  Half for naming the level with no rule for it. None for agreeing to the table.
- **tutor note:** a learner who says "only members should see anything" has given a rule; accept
  it. If they instead tinker with a member's row (say, members shouldn't post), ask who else could
  send a request to this backend.

### edit-button

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** No: step 5 leaves editing to React. `PATCH /api/events/:id` must check on the server,
  as `DELETE` does in step 3, that the signed-in user posted the screening or is an officer, and
  refuse the request otherwise, because any signed-in member can send that `PATCH` without the
  page.
- **credit:** full for naming the route or the action (editing a screening) and saying the server
  must check owner-or-officer on it. Half for saying hiding the button isn't enough with no fix,
  or a fix that stays in React.
- **tutor note:** if they agree because the button is hidden, ask: "could someone edit Priya's
  screening without using your page at all?" A reply asking to remove the React check is not the
  fix; the buttons should stay hidden as well.

### routes-file

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** No: `router.delete('/api/events/:id', deleteEvent)` has no `requireAuth`, so anyone,
  signed in or not, can delete any screening. Give it `requireAuth` and `requireOwnerOrOfficer`,
  as the `PATCH` route has.
- **credit:** full for naming the `DELETE` route (or deleting a screening) as the one that needs
  the check; naming either middleware, or "the sign-in check", is enough. Half for "check all
  routes" or "make sure every route is protected" with none named.
- **tutor note:** if they point at step 4 and say the button is hidden anyway, ask who could send a
  `DELETE` without the page. `GET /api/events` having no middleware is correct: anyone may see the
  screenings.

### who-is-asking

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** No: the server takes the user from an `x-user-id` header, which anyone signed in can
  set to someone else's id, and then edit, delete or post as them. The server must take the user
  from the session (`req.session.userId`), not from anything the request carries; drop the header.
- **credit:** full for both: what's wrong (the server believes an id the request sends, which
  anyone can change) and that the user should come from the session. Half for one of the two.
- **tutor note:** "the header comes from our own React code" is the trap; ask whether a request
  has to come from React. A fix that signs or hides the header is still taking the user's word;
  ask where the backend already knows who is signed in.

### whole-plan

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Yes, as it stands. Every route that changes data checks sign-in on the server, edit
  and delete check owner-or-officer against the session's user, posting and going take the user
  from the session, React hides the buttons as well, and `users` keeps GitHub's id, not a
  password.
- **credit:** full when they agree and ask for no change that would break it (moving a check into
  React only, taking the user id from the request, adding a password column). A harmless
  suggestion (an index on `github_id`, a test for each rule, checking `role` in a middleware of its
  own) costs nothing. None otherwise.
- **tutor note:** a learner who refuses because `GET /api/events` has no `requireAuth` has misread
  the table, which lets someone not signed in see the screenings; ask them to find that row.

### confirm-signed-out

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** Send `POST https://reeltime-api.kettlerun.com/api/events` with no sign-in, for
  example from a terminal with no session cookie. It should get 401.
- **credit:** full for the request (posting a screening to the backend, method and path, or plainly
  that request, with no session) and 401. Half for one of the two: the request with a wrong or no
  status, or 401 with a check of what the page shows (the Post button gone, a redirect to sign-in).
- **tutor note:** if they open the site signed out and look, ask whether someone could send that
  request without the page. The full address is not required; `POST /api/events` with no cookie is
  enough.

### confirm-not-owner

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** No: the agent's check only shows the page hides a button, and signed out it isn't
  testing the owner rule at all. Sign in as a second member who didn't post Priya's screening and
  send `DELETE https://reeltime-api.kettlerun.com/api/events/<its id>` with that account's session.
  It should get 403.
- **credit:** full for all three: a second account, signed in, that isn't the owner; the request
  (deleting Priya's screening, method and path or plainly that request); and 403. Half when one is
  off: signed out instead of a second account, 401 instead of 403, or checking what the page shows
  instead of sending the request. None for accepting the agent's check with nothing else. Don't
  require a verdict on the agent's check stated separately: a reply that goes straight to the right
  request has answered it.
- **tutor note:** if they send the `DELETE` signed out, ask what that would show: it gets 401 and
  proves the sign-in rule, not the owner rule. If they say "log in as another user and try to
  delete", ask whether they mean the page or the request.
