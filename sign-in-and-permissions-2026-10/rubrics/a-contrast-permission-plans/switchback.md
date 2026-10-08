Switchback is a hiking club's trip board, and its trips are for members only. Its rules: any signed-in
member may see the trips, post one, sign up and leave; only a trip's leader or an officer may change
or cancel it; someone not signed in may do nothing at all, not even see the trips. Every route,
`GET /api/trips` included, should check sign-in. The setup names the three signed-in levels only,
never someone not signed in.

Eight questions, one per case, in this order: `missing-signed-out`, `missing-action`, `react-only`,
`unchecked-route`, `trusts-frontend`, `sound-plan`, `confirm-401`, `confirm-403`. The sound version
is at A, B, B, A, A, both, B, A. Hard: q1 (the unsound table carries the agent's reassuring line),
q4 (one route line in otherwise identical lists), q5 (one code line in otherwise identical handlers)
and q6 (the difference sits only in the schemas, in otherwise identical plans). The rest are Medium. No question before q8
names a refusal status code, and none before q5 says where the server gets the signed-in user from.

The two table questions show each other's answer (each complete table has every row and the
signed-out column); each pair already shows its own difference, so this is accepted.

### q1

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** A. B has no column for someone who isn't signed in, so it never says what a visitor
  with no sign-in may do; A says they may do nothing, not even see the trips. B's closing line is
  wrong: someone not signed in can still reach the app.
- **credit:** full for A and saying that B leaves out someone who isn't signed in. Half for A with
  no reason or a wrong one. None for B or both.
- **tutor note:** a learner who reads B's closing line as true because every user is a member has
  missed the visitor who never signs in; ask who could open the site without signing in, and which
  column says what they may do.

### q2

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** B. A has no row for leaving a trip, though `DELETE /api/trips/:id/signups` lets
  someone try it; B says any signed-in member may.
- **credit:** full for B and naming leaving a trip (taking someone off a trip) as the action A
  leaves out. Half for B with no reason or a wrong one. None for A or both.

### q3

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** B. A enforces the leader rule only by hiding the buttons in React; anyone signed in
  can send `PATCH` or `DELETE /api/trips/:id` without the page. B also checks on the server that
  the user leads the trip or is an officer.
- **credit:** full for B and saying that A's rule lives only in the page (the frontend, React, the
  buttons), so the request can be sent without it, or that the server must check who leads the
  trip. Half for B with no reason or a wrong one. None for A or both.

### q4

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** A. In B, `DELETE /api/trips/:id/signups` has no `requireAuth`, so a request with no
  sign-in reaches a handler that deletes rows, and leaving a trip changes data.
- **credit:** full for A and naming the leave-a-trip route (`DELETE /api/trips/:id/signups`, or
  leaving a trip) as the one B leaves unchecked. Half for A with no reason or a wrong one, including
  "B is missing a check" with no route named, or naming `DELETE /api/trips/:id` instead. None for B
  or both.
- **tutor note:** the two `DELETE` lines look alike; a learner who names the cancel route has not
  found the line where A and B differ.

### q5

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** A. B takes the user id from a request header, so the server believes whatever id it is
  sent, and anyone signed in could take any other member off a trip. A takes it from the session.
- **credit:** full for A and saying that B believes an id the request sends (a header, the frontend,
  the user) rather than the session. Half for A with no reason or a wrong one. None for B or both.
- **tutor note:** a learner who says `requireAuth` makes B safe has missed that it checks someone
  is signed in, not that the id in the header is theirs.

### q6

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Both. They differ only in where officers are recorded: A in a `role` column on
  `users`, B in a separate `officers` table. Either way the server checks every rule against the
  session's user, and `requireLeaderOrOfficer` can tell an officer from anyone else.
- **credit:** full for "both", with no reason at all or with any reason that doesn't call either
  broken. None for rejecting one.
- **tutor note:** a learner who prefers one (A for one fewer table, B for keeping officers apart)
  while agreeing to both has it. One who rejects B because its `users` table has no role has missed
  the `officers` table; ask where B says who is an officer. Either way, ask what the rejected
  version lets anyone do that the rules forbid.

### q7

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** B, and it should get 401. A only shows what the page displays; the trips could still
  come back from the backend to anyone who asks, and the request is what the server actually decides
  on.
- **credit:** full for B and 401. Half for B with no status code or a wrong one. None for A or both.
- **tutor note:** 403 here is the common slip; ask whether the server knows who is asking at all.

### q8

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** A, and it should get 403. B would be refused with 401 for having no sign-in at all,
  which proves the sign-in rule, not the rule about who may cancel.
- **credit:** full for A and 403. Half for A with no status code or a wrong one (such as 401). None
  for B or both.
- **tutor note:** a learner who picks both has missed that B never reaches the leader check; ask what
  B would get back, and what that proves.
