The sound table has a column for someone not signed in, who may see the photos and comments and
nothing else (or, on a stricter reading, nothing at all), and a row for each of the seven routes.
Members may post photos and comment; only a photo's owner and the moderators may edit its caption
or delete it; only moderators may feature a photo. Every rule has to hold on the server, against
the user the session names, because anyone signed in can send any of these requests from a
terminal without the page. This scenario's table case is `missing-signed-out`, set first so that
no complete table has been seen before it; it never carries `missing-action`. Levels:
`draft-table` Medium, `comments-route` Medium, `delete-button` Medium, `new-photo` Hard (the flaw is
one code line among sound ones), `whole-plan` Medium, `confirm-delete` Medium, `confirm-caption`
Hard (the agent offers its own check of what the page shows, from the right account). Each question
has one thing wrong at most; a learner who also flags something sound costs nothing unless the
change they ask for would break the plan.

### draft-table

- **goal:** `c-review-permissions`
- **cases:** missing-signed-out
- **answer:** Not as it stands: it leaves out someone who isn't signed in. Add a column for them:
  they may see the photos and comments and nothing else (no posting, editing, deleting, commenting,
  featuring, or `GET /api/me`).
- **credit:** full for naming the missing level (someone not signed in, a visitor, a signed-out
  user) and what its column should say: that they may only see the photos, or may do nothing. Half
  for naming the level with no rule for it, or with a rule that lets them change anything. None for
  agreeing to the table.
- **tutor note:** a learner who says "only members should see anything" has given a rule; accept
  it. If they instead tinker with a row that is there (say, owners should be able to feature their
  own photo), ask who else could send a request to this backend.

### comments-route

- **goal:** `c-review-permissions`
- **cases:** unchecked-route
- **answer:** No: step 5 leaves `POST /api/photos/:id/comments` with no `requireAuth`, so someone
  not signed in can post comments, with no author. Give it `requireAuth`, as the other routes that
  change data have.
- **credit:** full for naming the comments route (or commenting on a photo) as the one that needs
  the sign-in check. Half for "check all routes" or "make sure every route is protected" with none
  named.
- **tutor note:** if they point at step 6 and say the comment box is hidden from signed-out
  visitors, ask who could send that `POST` without the page. A learner who also asks for
  `requireOwnerOrModerator` on it would stop members commenting on each other's photos; ask what
  the table says a member may do. `GET /api/photos` having no middleware is correct.

### delete-button

- **goal:** `c-review-permissions`
- **cases:** react-only
- **answer:** No: step 4 leaves the owner rule for deleting to React, and step 5's
  `DELETE /api/photos/:id` checks only that someone is signed in. That route must check on the
  server, as the caption route does in step 3, that the signed-in user posted the photo or is a
  moderator, and refuse the request otherwise, because any signed-in member can send that `DELETE`
  without the page.
- **credit:** full for naming the route or the action (deleting a photo) and saying the server must
  check owner-or-moderator on it. Half for saying hiding the button isn't enough with no fix, or a
  fix that stays in React.
- **tutor note:** if they agree because the button is hidden, ask: "could someone delete Dana's
  photo without using your page at all?" A reply asking to remove the React check is not the fix;
  the Delete button should stay hidden as well.

### new-photo

- **goal:** `c-review-permissions`
- **cases:** trusts-frontend
- **answer:** No: `createPhoto` takes the new photo's owner from `req.query.user`, a value the
  request sends, so anyone signed in can post a photo with another member's id in the query and
  have it appear as theirs. It must take the owner from the session, `req.session.userId`, as
  `addComment` and the middlewares already do.
- **credit:** full for both: what's wrong (the owner comes from an id the request sends, which
  anyone can change) and that the user should come from the session. Half for one of the two.
- **tutor note:** if they agree, ask them to read the line that sets `ownerId` and say where that
  value comes from. "Our React code always puts the right id in the query" is the trap; ask whether
  a request has to come from React. If they say `requireAuth` already covers it, ask whose id the
  query would hold when a signed-in member sends someone else's.

### whole-plan

- **goal:** `c-review-permissions`
- **cases:** sound-plan
- **answer:** Yes, as it stands. Every route that changes data checks sign-in on the server; editing
  and deleting check owner-or-moderator, and featuring checks moderator, against the session's
  user; posting and commenting take the user from the session; React hides the buttons as well;
  and `users` keeps GitHub's id, not a password.
- **credit:** full when they agree and ask for no change that would break it (moving a check into
  React only, taking the user id from the request, adding a password column). A harmless
  suggestion (an index on `github_id`, a test for each rule, a moderators table instead of the
  `role` column) costs nothing. None otherwise.
- **tutor note:** a learner who refuses because `GET /api/photos` has no `requireAuth` has misread
  the table, which lets someone not signed in see the photos; ask them to find that row.

### confirm-delete

- **goal:** `c-review-permissions`
- **cases:** confirm-401
- **answer:** Send `DELETE https://snapwall-api.ironloft.com/api/photos/<a photo's id>` with no
  sign-in, for example from a terminal with no session cookie. It should get 401.
- **credit:** full for the request (deleting a photo on the backend, method and path, or plainly
  that request, with no session) and 401. Half for one of the two: the request with a wrong or no
  status, or 401 with a check of what the page shows (the Delete button gone).
- **tutor note:** a learner who expects 403 because deleting is an owner's action should be asked
  whether the server knows who is asking at all. The full address is not required;
  `DELETE /api/photos/:id` with no cookie is enough.

### confirm-caption

- **goal:** `c-review-permissions`
- **cases:** confirm-403
- **answer:** No: the agent used the right account but only looked at the page, which shows the
  button is hidden, not that the server refuses. Signed in as that second account (a member who
  didn't post Dana's photo and isn't a moderator), send
  `PATCH https://snapwall-api.ironloft.com/api/photos/<its id>` with a new caption, using that
  account's session. It should get 403.
- **credit:** full for all three: a second account, signed in, that isn't the owner; the request
  (editing that photo's caption, method and path or plainly that request); and 403. Half when one
  is off: signed out instead of a second account, 401 instead of 403, or checking what the page
  shows instead of sending the request. None for accepting the agent's check with nothing else.
  Don't require a verdict on the agent's check stated separately: a reply that goes straight to the
  right request has answered it.
- **tutor note:** the agent's account is right and its method is wrong; a learner who objects only
  to the account has missed that. If they send the `PATCH` signed out, ask what that would show: it
  gets 401 and proves the sign-in rule, not the owner rule. If their second account is a moderator,
  ask what the table says a moderator may do.
