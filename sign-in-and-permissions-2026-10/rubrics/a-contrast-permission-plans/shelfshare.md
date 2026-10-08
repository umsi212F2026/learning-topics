Shelfshare is a shared reading list. Its rules: anyone, signed in or not, may see the list; any
signed-in member may add a book and vote; only the member who added a book or an organizer may
edit or remove it; someone not signed in may do nothing but look. `GET /api/books` is open to
everyone on purpose, and `GET /api/me` changes nothing, so neither is a flaw in any version. The
setup names the three signed-in levels only, never someone not signed in.

Eight questions, one per case, in this order: `missing-action`, `missing-signed-out`, `react-only`,
`unchecked-route`, `trusts-frontend`, `sound-plan`, `confirm-401`, `confirm-403`. The sound version
is at A, B, A, B, B, both, B, A. Hard: q1 (the unsound table carries the agent's reassuring line),
q4 (one route line in otherwise identical lists) and q5 (one code line in otherwise identical
handlers). The rest are Medium. No question before q8 names a refusal status code, and none before
q5 says where the server gets the signed-in member from.

The two table questions show each other's answer (each complete table has every row and the
signed-out column); each pair already shows its own difference, so this is accepted.

### q1

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** A. B has no row for editing a book, though `PATCH /api/books/:id` lets someone try it,
  so it never says who may edit; A says only the member who added it and organizers may. B's closing
  line is wrong.
- **credit:** full for A and naming editing a book as the action B leaves out. Half for A with no
  reason or a wrong one. None for B or both.
- **tutor note:** a learner who picks B because of its closing line has taken the reassurance at its
  word; ask which route lets someone change a book's note, and which row covers it.

### q2

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** B. A has no column for someone who isn't signed in, so it never says what a visitor
  with no sign-in may do; B says they may see the list and nothing else.
- **credit:** full for B and saying that A leaves out someone who isn't signed in. Half for B with
  no reason or a wrong one. None for A or both.
- **tutor note:** "A doesn't say what visitors can do" has it; the exact column name is not required.

### q3

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** A. B keeps people away from the buttons and the edit page, but both live in React;
  anyone signed in can send `PATCH` or `DELETE /api/books/:id` without the page. A also checks on
  the server that the member added the book or is an organizer.
- **credit:** full for A and saying that B's rule lives only in the page (the frontend, React, the
  buttons, the redirect), so the request can be sent without it, or that the server must check who
  added the book. Half for A with no reason or a wrong one. None for B or both.
- **tutor note:** a learner who thinks the redirect makes B safe is treating a page rule as a server
  rule; ask what stops someone sending the `PATCH` from a terminal.

### q4

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** B. In A, `POST /api/books` has no `requireSignIn`, so someone not signed in can add
  books to the list, and adding a book changes data.
- **credit:** full for B and naming the add-a-book route (`POST /api/books`, or adding a book) as
  the one A leaves unchecked. Half for B with no reason or a wrong one, including "A is missing a
  check" with no route named. None for A or both.
- **tutor note:** a learner who flags `GET /api/books` in both has missed that the list is open to
  everyone; it does not cost them q4 if they also name `POST /api/books`.

### q5

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** B. A takes the member id from the request body, so the server believes whatever id it
  is sent, and anyone signed in could cast votes in every other member's name. B takes it from the
  session.
- **credit:** full for B and saying that A believes an id the request sends (the body, the frontend,
  the user) rather than the session. Half for B with no reason or a wrong one. None for A or both.
- **tutor note:** a learner who says `requireSignIn` makes A safe has missed that it checks someone
  is signed in, not that the id in the body is theirs.

### q6

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Both. They differ only in where the owner check lives, a middleware on the two routes
  or a check at the top of each handler; each checks every rule on the server against the session's
  member and keeps `github_id` with no password.
- **credit:** full for "both", with no reason at all or with any reason that doesn't call either
  broken. None for rejecting one.
- **tutor note:** a learner who prefers A as tidier, while agreeing to both, has it; one who rejects
  B because "the check should be middleware" has called a sound plan broken.

### q7

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** B, and it should get 401. A only shows what the page displays; the request is what the
  server actually decides on.
- **credit:** full for B and 401. Half for B with no status code or a wrong one. None for A or both.
- **tutor note:** 403 here is the common slip; ask whether the server knows who is asking at all.

### q8

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** A, and it should get 403. B would be refused with 401 for having no sign-in at all,
  which proves the sign-in rule, not the rule about who may edit.
- **credit:** full for A and 403. Half for A with no status code or a wrong one (such as 401). None
  for B or both.
- **tutor note:** a learner who picks both has missed that B never reaches the owner check; ask what
  B would get back, and what that proves.
