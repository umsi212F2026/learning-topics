Five routes and four levels. The complete table for them, which q3 to q6 show and q1 and q2 are
judged against:

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

Levels: q4, q5 and q8 are Hard (q4's flaw is one bare route line among guarded ones; q5's is
justified by the agent; q8's agent offers its own check of the page). The rest are Medium. The
plans in q3 to q6 say "refuses the request" rather than naming a status code, so that no plan
gives away q7 or q8.

q1's table shows a column for someone not signed in and q2's shows a row for deleting, so
whichever of the two is studied second can be answered by comparing it with the first. The
generator asks for both tables and for both to come first, so this can't be avoided within one
scenario. Weigh a pass on q2 accordingly when q1 was studied first in the same sitting.

### q1

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** No. The table has no row for deleting an item, though `DELETE /api/items/:id`
  allows it. Add one: not signed in no, signed-in resident no, owner of the item yes, desk staff
  yes.
- **credit:** full for naming deleting as the missing action and giving its row a rule that keeps
  it from people not signed in and from residents who didn't post the item (owner and desk staff
  yes is the natural rule; desk staff only, or owner only, also counts). Half for naming deleting
  with no rule for it.
- **tutor note:** if they say only "something is missing", ask them to go through the route list
  one line at a time and find the route with no row.

### q2

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** No. The table has no column for someone not signed in. Add one: they may view the
  board, and may not post, edit, mark handed back or delete.
- **credit:** full for naming someone not signed in as the missing level and saying what their
  column should hold (view only, or nothing at all, both count). Half for naming the level with
  no rule for it.

### q3

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** No. Editing is limited to the owner and desk staff only by hiding the Edit button;
  `PATCH /api/items/:id` checks only that someone is signed in, so any signed-in resident can send
  that request without the page (from a terminal, or the browser's developer tools) and edit
  someone else's item. Put `requireOwnerOrStaff` after `requireAuth` on `PATCH /api/items/:id`,
  and keep hiding the button as well.
- **credit:** full for naming the edit route (or editing) and saying the server must check owner
  or staff on it. Half for saying hiding the button isn't enough with no fix on the server.
- **tutor note:** if they want the button shown to everyone instead, ask what stops the request
  once the button is gone, and who could send it without the page.

### q4

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** No. `router.delete('/api/items/:id', deleteItem)` has no middleware, so anyone, even
  someone not signed in, can delete any item. Give it `requireAuth` then `requireOwnerOrStaff`,
  like the edit and handed-back routes.
- **credit:** full for naming the delete route and that it needs the check. Half for "check all
  the routes" or "make sure every route is protected" with no route named.
- **tutor note:** a learner who adds only `requireAuth` to the delete route has met the case; ask
  who the table lets delete, and what else that route needs. A learner who also wants
  `GET /api/items` closed has misread the table's first row; point them to it.

### q5

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** No. `requireOwnerOrStaff` decides who is asking from the `x-user-id` header, which
  the request itself carries; anyone signed in can send a request with the owner's id, or a desk
  staff member's, and edit, hand back or delete any item. It should take the user from the
  session (`req.session.userId`, which `requireAuth` already reads), and the frontend should stop
  sending the header.
- **credit:** full for both: that the server believes an id the request sends, so anyone can
  claim to be someone else, and that the user must come from the session instead. Half for one.
- **tutor note:** if they object only that the header is "insecure", ask who sets that header and
  whether someone could set it to another resident's id.

### q6

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Yes, agree as it stands. Every route that changes data checks sign-in on the server,
  the owner-or-staff rules are checked on the server against the session's user, a new item's
  owner comes from the session, React hides the buttons as well, and the `users` table keeps
  Google's id (`google_sub`), a name, an email and a role, with no password.
- **credit:** full when they agree and ask for no change that would break it (moving the checks
  into React only, taking the user id from the request, adding a password column). A harmless
  suggestion (a staff page for setting roles, a nicer error message) costs nothing. None
  otherwise.
- **tutor note:** a learner uneasy that roles are set by hand in the database, or that the email
  is kept, is asking a fair question; neither breaks the plan. The email is kept because the board
  shows it.

### q7

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** Send `POST https://finders-api.harborbox.com/api/items` with no sign-in, for example
  with `curl` from a terminal, which sends no session cookie. It should get 401.
- **credit:** full for that request (posting to the items route, method and path, with no
  sign-in) and 401. Half for one of the two. What the page shows when signed out (no Post button,
  a prompt to sign in) is not the request and earns nothing on its own.
- **tutor note:** if they answer 403, ask what the server knows about who is asking when there is
  no sign-in at all.

### q8

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** No. The page hiding a button doesn't show what the server does, and a private window
  is signed out, so it tests a different rule anyway. Sign in as a second resident account, one
  that didn't post the item, and send `DELETE https://finders-api.harborbox.com/api/items/<id>`
  for an item the first account posted. It should get 403.
- **credit:** full for a second account that is signed in, the delete request on the owner's item,
  and 403. Half when one of those is off: signed out instead of a second account, or 401, or
  checking what the page shows.
- **tutor note:** if they say "send the delete request from a private window", ask which rule that
  tests and what it should get back, then ask what a non-owner who is signed in would get.
