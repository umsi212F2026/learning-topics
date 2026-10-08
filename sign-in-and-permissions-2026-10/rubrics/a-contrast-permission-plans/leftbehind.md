Leftbehind is a lost-and-found board. Its rules: anyone, signed in or not, may view the items;
any signed-in user may post an item and claim one; only the item's poster or desk staff may edit or
delete it; someone not signed in may do nothing but view. `GET /api/items` is open to everyone on
purpose, and `GET /api/me` changes nothing, so neither is a flaw in any version. The setup names
the three signed-in levels only, never someone not signed in.

Eight questions, one per case, in this order: `missing-signed-out`, `missing-action`, `react-only`,
`unchecked-route`, `trusts-frontend`, `sound-plan`, `confirm-401`, `confirm-403`. The sound version
is at B, A, B, A, B, both, A, B. Hard: q3 (the unsound step carries the agent's reassuring
sentence), q4 (one route line in otherwise identical lists) and q5 (one code line in otherwise
identical handlers). The rest are Medium. No question before q8 names a status code, and none
before q5 says where the server gets the signed-in user from.

Every table shows the poster's column as yes for claiming, which is odd but the same in A and B;
it is not a flaw any question turns on.

### q1

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** B. A has no column for someone who isn't signed in, so it never says what a visitor
  with no sign-in may do; B says they may view the items and nothing else.
- **credit:** full for B and saying that A leaves out someone who isn't signed in. Half for B with
  no reason or a wrong one. None for A or both.
- **tutor note:** a learner who says "A doesn't cover visitors" has it; the exact column name is
  not required.

### q2

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** A. B has no row for deleting an item, though `DELETE /api/items/:id` lets someone try
  it; A says only the poster and desk staff may.
- **credit:** full for A and naming delete (removing an item) as the action B leaves out. Half for A
  with no reason or a wrong one. None for B or both.

### q3

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** B. A enforces the owner rule only by hiding the buttons in React; anyone signed in
  can send `PATCH` or `DELETE /api/items/:id` without the page, and the route only checks that they
  are signed in. B checks on the server that the user posted the item or is desk staff.
- **credit:** full for B and saying that A's rule lives only in the page (the frontend, React, the
  button), so the request can be sent without it, or that the server must check who posted the
  item. Half for B with no reason or a wrong one. None for A or both.
- **tutor note:** a learner who picks A because of its last sentence has taken the reassurance at
  its word; ask who could send that `DELETE` without the page.

### q4

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** A. In B, `POST /api/items/:id/claim` has no `requireAuth`, so someone not signed in
  can file a claim, and claiming changes data.
- **credit:** full for A and naming the claim route (or claiming) as the one B leaves unchecked.
  Half for A with no reason or a wrong one, including "B is missing a check" with no route named.
  None for B or both.
- **tutor note:** a learner who flags `GET /api/items` in both has missed that viewing is open to
  everyone; it does not cost them q4 if they also name the claim route.

### q5

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** B. A takes the user id from the request body, so the server believes whatever id it
  is sent, and anyone signed in could file a claim in someone else's name. B takes it from the
  session.
- **credit:** full for B and saying that A believes an id the request sends (the body, the
  frontend, the user) rather than the session. Half for B with no reason or a wrong one. None for A
  or both.
- **tutor note:** a learner who says `requireAuth` makes A safe has missed that it checks someone
  is signed in, not that the id in the body is theirs.

### q6

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Both. They differ only in where desk staff are recorded, a `role` column or a
  separate table; each checks every rule on the server against the session's user, keeps
  `google_sub` with no password, and hides buttons in React as well.
- **credit:** full for "both", with no reason at all or with any reason that doesn't call either
  broken. None for rejecting one.

### q7

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** A, and it should get 401. B only shows what the page displays; the `POST` with no
  session cookie is what the server actually decides on.
- **credit:** full for A and 401. Half for A with no status code or a wrong one. None for B or
  both.
- **tutor note:** 403 here is the common slip; ask whether the server knows who is asking at all.

### q8

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** B, and it should get 403. A would be refused with 401 for having no sign-in at all,
  which proves the sign-in rule, not the owner rule.
- **credit:** full for B and 403. Half for B with no status code or a wrong one (such as 401). None
  for A or both.
- **tutor note:** a learner who picks both has missed that A never reaches the owner check; ask
  what A would get back, and what that proves.
