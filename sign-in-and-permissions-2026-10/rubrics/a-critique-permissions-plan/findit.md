The sound table has a column for someone not signed in, who may see the items and nothing else, and
a row for each of the six routes. Residents may post; only a post's owner and the desk workers may
edit it, mark its item claimed, or delete it. Every rule has to hold on the server, against the
user the session names, because anyone signed in can send any of these requests from a terminal
without the page. This scenario's table case is `missing-action` (the table leaves out deleting),
set first so that no complete table has been seen before it; it never carries
`missing-signed-out`. Levels: `draft-table` Medium, `edit-button` Medium, `claim-step` Medium,
`owner-check` Hard (the flaw is one code line among sound ones), `whole-plan` Medium,
`confirm-claimed` Hard (the agent offers its own check of what the page shows), `confirm-edit`
Medium. Each question has one thing wrong at most; a learner who also flags something sound costs
nothing unless the change they ask for would break the plan.

### draft-table

- **goal:** `c-review-permissions`
- **cases:** missing-action
- **answer:** Not as it stands: it has no row for deleting a post, though `DELETE /api/items/:id`
  allows it. Add one: someone not signed in, no; a signed-in resident, no; the post's owner, yes; a
  desk worker, yes.
- **credit:** full for naming the missing action (deleting a post) and what its row should say:
  that only the post's owner and desk workers may, or a stricter rule such as desk workers only.
  Half for naming the action with no rule for it, or with a rule that lets someone delete a post
  who neither posted it nor works the desk. None for agreeing to the table.
- **tutor note:** if they tinker with a row that is there (say, residents shouldn't post), ask them
  to go down the route list and find each route's row.

### edit-button

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** No: step 4 leaves editing to React. `PATCH /api/items/:id` must check on the server,
  as the claimed and delete routes do in step 3, that the signed-in user posted the item or is a
  desk worker, and refuse the request otherwise, because any signed-in resident can send that
  `PATCH` without the page.
- **credit:** full for naming the route or the action (editing a post) and saying the server must
  check owner-or-desk-worker on it. Half for saying hiding the button isn't enough with no fix, or
  a fix that stays in React.
- **tutor note:** if they agree because the button is hidden, ask: "could someone edit another
  resident's post without using your page at all?" A reply asking to remove the React check is not
  the fix; the Edit button should stay hidden as well.

### claim-step

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** No: `PATCH /api/items/:id/claimed`, added in step 4, gets neither middleware, so
  anyone, signed in or not, can mark any item claimed. Give it `requireAuth` and
  `requireOwnerOrDesk`, as the other routes that change a post have.
- **credit:** full for naming the claimed route (or marking an item claimed) as the one that needs
  the check; naming either middleware, or "the sign-in check", is enough. Half for "check all
  routes" or "make sure every route is protected" with none named.
- **tutor note:** if they point at step 5 and say the button is hidden anyway, ask who could send
  that `PATCH` without the page. `GET /api/items` having no middleware is correct: anyone may see
  the items.

### owner-check

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** No: `requireOwnerOrDesk` decides who is asking from `req.body.userId`, an id the
  request sends, so anyone signed in can put another resident's id (or a desk worker's) in the body
  and edit, mark claimed or delete their posts. It must load the user from the session,
  `req.session.userId`, as `requireAuth` and `createItem` already do.
- **credit:** full for both: what's wrong (the owner check believes a user id the request sends,
  which anyone can change) and that the user should come from the session. Half for one of the
  two.
- **tutor note:** if they agree, ask them to read the line that loads `user` and say where that id
  comes from. "Our React code always sends the right id" is the trap; ask whether a request has to
  come from React.

### whole-plan

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Yes, as it stands. Every route that changes data checks sign-in on the server; edit,
  mark claimed and delete each check owner-or-desk-worker against the session's user inside the
  handler; posting takes the owner from the session; React hides the buttons as well; and `users`
  keeps Google's id, not a password.
- **credit:** full when they agree and ask for no change that would break it (moving a check into
  React only, taking the user id from the request, adding a password column). A harmless
  suggestion (moving `canChange` into a middleware, an index on `google_id`, a test for each rule)
  costs nothing. None otherwise.
- **tutor note:** a learner who refuses because the routes carry only `requireAuth` has missed step
  4; ask what each handler does before it changes anything. One who refuses because
  `GET /api/items` has no `requireAuth` has misread the table; ask them to find that row.

### confirm-claimed

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** No: the agent's check only shows the page hides a button. Send
  `PATCH https://findit-api.hearthbox.com/api/items/<an item's id>/claimed` with no sign-in, for
  example from a terminal with no session cookie. It should get 401.
- **credit:** full for the request (marking an item claimed on the backend, method and path, or
  plainly that request, with no session) and 401. Half for one of the two: the request with a
  wrong or no status, or 401 with a check of what the page shows. None for accepting the agent's
  check with nothing else. Don't require a verdict on the agent's check stated separately: a reply
  that goes straight to the right request has answered it.
- **tutor note:** if they repeat the agent's check another way (another browser, clearing
  cookies and looking), ask whether someone could send that request without the page. The full
  address is not required; `PATCH /api/items/:id/claimed` with no cookie is enough.

### confirm-edit

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** Sign in as a second resident, one who didn't post the item and isn't a desk worker,
  and send `PATCH https://findit-api.hearthbox.com/api/items/<its id>` with a new description,
  using that account's session. It should get 403.
- **credit:** full for all three: a second account, signed in, that isn't the owner; the request
  (editing that post, method and path or plainly that request); and 403. Half when one is off:
  signed out instead of a second account, 401 instead of 403, or checking what the page shows
  instead of sending the request.
- **tutor note:** if they send the `PATCH` signed out, ask what that would show: it gets 401 and
  proves the sign-in rule, not the owner rule. If their second account is a desk worker, ask what
  the table says a desk worker may do.
