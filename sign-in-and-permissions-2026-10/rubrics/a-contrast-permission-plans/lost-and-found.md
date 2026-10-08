Finders has four item routes and four levels. The complete table has a row for each of the four
things the routes let someone do (see the list, post, edit or mark returned, delete) and a column
for each level, someone not signed in included. Sign-in is GitHub, so users are keyed by
`github_id`, and `requireAuth` is the sign-in middleware the setup names. `GET /api/me` has no
`requireAuth` in either route list and needs none: it changes nothing and answers "nobody" to
someone signed out. The sound version sits at B in q1, q3 and q5, at A in q2, q4 and q8, and q6
is sound in both. q4, q5 and q8 are Hard; the rest are Medium.

### q1

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** B. A has no row for deleting an item, though `DELETE /api/items/:id` lets someone
  try it, so the table never says who may delete (in B, the poster and desk staff only).
- **credit:** full for B with the missing delete row named as what gives it away; half for B
  with no reason or a wrong one.

### q2

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** A. B has no column for someone not signed in, so it never says what a visitor who
  hasn't signed in may do (in A, only see the list).
- **credit:** full for A with the missing signed-out column named as what gives it away; half
  for A with no reason or a wrong one.

### q3

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** B. In A the poster-or-staff rule lives only in React: the routes check only that
  someone is signed in, so any signed-in user can send `PATCH` or `DELETE` on someone else's item
  without the page. B checks it on the server as well.
- **credit:** full for B with the reason that hiding the button doesn't stop the request, which
  can be sent without the page, so the server has to check; half for B with no reason or a wrong
  one.
- **tutor note:** "B is more secure" or "B checks the owner" with nothing on why the hidden
  button isn't enough is half: ask who could still send the request in A, and how.

### q4

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** A. B leaves `POST /api/items` without `requireAuth`, so someone who isn't signed in
  can post items.
- **credit:** full for A with `POST /api/items` (or posting an item) named as the route B leaves
  open; half for A with no reason or a wrong one.
- **tutor note:** a learner who also remarks that `GET /api/me` and `GET /api/items` have no
  `requireAuth` loses nothing for it, since both lists match there; if that is their only reason,
  it is a wrong reason, and half.

### q5

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** B. A takes the user's id from the `x-user-id` header, which whoever sends the
  request can set to any id, such as a desk staff member's; B takes it from the session the
  backend started at sign-in.
- **credit:** full for B with the reason that A believes whatever id the request carries (a
  header anyone can set) rather than the session; half for B with no reason or a wrong one.

### q6

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Both. They differ only in where the poster-or-staff check sits, a middleware on the
  routes or a check inside each handler; either way every rule is checked on the server against
  the session's user, and users are keyed by `github_id` with no password.
- **credit:** full for "both" with any reason that doesn't call either broken; half for "both"
  with no reason; none for rejecting either one, or for agreeing only after a change that would
  break it (moving the check into React, taking the user from the request, adding a password).
- **tutor note:** a preference for one (the middleware is harder to forget on a new route) is
  fine alongside "both"; it costs nothing unless it rejects the other.

### q7

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** B, and it should get 401. A only shows what the page shows when signed out; a
  missing button says nothing about whether the server turns the request away.
- **credit:** full for B with 401 as what it should get back; half for B with no status code or
  the wrong one (403, 404, "an error").
- **tutor note:** a learner who chooses both because A "also helps" has not chosen the request
  over the page: that is none, by the generator's credit rule.

### q8

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** A, and it should get 403. B's request comes from someone not signed in, so its
  refusal (a 401) shows only that signing in is required, not that a signed-in user who didn't
  post item 42 is refused.
- **credit:** full for A with 403 as what it should get back; half for A with no status code or
  the wrong one (401, 404, "an error").
- **tutor note:** a learner swayed by the agent's "I tried this and it was refused" in B may pick
  both, which is none; ask who B's request comes from and which rule its refusal proves.
