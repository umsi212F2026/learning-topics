Reeltime is your Problem Set 3 app: an events board for a campus film society, where members post
screenings and say they're going. Its React frontend is built to static files on Pagebarn, at
`https://reeltime.pagebarn.app`, and its Express backend runs on Kettlerun, at
`https://reeltime-api.kettlerun.com`, with a Postgres database. Sign-in through GitHub already
works: once someone signs in, the backend keeps them signed in with a session cookie. Now you and
your coding agent are deciding who may do what.

The backend's routes:

- `GET /api/events`: lists every screening on the board.
- `POST /api/events`: posts a new screening; whoever posts it is its owner.
- `PATCH /api/events/:id`: edits a screening's title, time or room.
- `DELETE /api/events/:id`: deletes a screening.
- `POST /api/events/:id/going`: adds the signed-in user to a screening's "going" list.
- `GET /api/me`: returns the signed-in user's GitHub name and picture.

The app's levels: a **signed-in member**; the **owner** of a screening, the member who posted it;
and an **officer**, one of the society's three officers, who look after the whole board.

Each question below is a separate piece of the work. They are independent: treat each one as if
it were the only one you had seen. Answer each in two to four sentences.

### signed-out-table

Your agent drafts this table for `DEPLOY.md`:

| Action | Signed-in member | Owner of the screening | Officer |
| --- | --- | --- | --- |
| See the screenings | yes | yes | yes |
| Post a screening | yes | yes | yes |
| Edit a screening | no | yes | yes |
| Delete a screening | no | yes | yes |
| Say you're going | yes | yes | yes |
| See your own name and picture | yes | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### edit-button

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the screening | Officer |
| --- | --- | --- | --- | --- |
| See the screenings | yes | yes | yes | yes |
| Post a screening | no | yes | yes | yes |
| Edit a screening | no | no | yes | yes |
| Delete a screening | no | no | yes | yes |
| Say you're going | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add `requireAuth` in `backend/middleware/auth.js`, which refuses any request from someone not
   signed in. Put it on every route that changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'member'` by default. You set `'officer'` by hand for the three
   officers.
3. In `DELETE /api/events/:id`, load the screening and refuse the request unless the signed-in user
   posted it or is an officer.
4. In React, show the Edit and Delete buttons only to the screening's owner and to officers:
   `{(user.id === event.ownerId || user.role === 'officer') && <EditButton />}`, and the same for
   Delete.
5. `PATCH /api/events/:id` saves the fields it is sent. React already hides the Edit button from
   everyone but the owner and officers, so the route stays simple: `requireAuth` and nothing more.

Would you agree to this as it stands? If not, what would you change?

### routes-file

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the screening | Officer |
| --- | --- | --- | --- | --- |
| See the screenings | yes | yes | yes | yes |
| Post a screening | no | yes | yes | yes |
| Edit a screening | no | no | yes | yes |
| Delete a screening | no | no | yes | yes |
| Say you're going | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses any request from someone not signed in.
2. `requireOwnerOrOfficer` loads the screening and refuses the request unless the signed-in user
   posted it or is an officer.
3. The routes, in `backend/routes/events.js`:

   ```js
   router.get('/api/events', listEvents);
   router.post('/api/events', requireAuth, createEvent);
   router.patch('/api/events/:id', requireAuth, requireOwnerOrOfficer, updateEvent);
   router.post('/api/events/:id/going', requireAuth, markGoing);
   router.delete('/api/events/:id', deleteEvent);
   router.get('/api/me', requireAuth, getMe);
   ```

4. In React, show the Edit and Delete buttons only to the screening's owner and to officers.

Would you agree to this as it stands? If not, what would you change?

### who-is-asking

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the screening | Officer |
| --- | --- | --- | --- | --- |
| See the screenings | yes | yes | yes | yes |
| Post a screening | no | yes | yes | yes |
| Edit a screening | no | no | yes | yes |
| Delete a screening | no | no | yes | yes |
| Say you're going | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses any request from someone not signed in. It goes on every route that
   changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'member'` by default. You set `'officer'` by hand for the three
   officers.
3. So the backend knows who is asking, React's fetch helper adds an `x-user-id` header to every
   request, set to the id that `GET /api/me` returned.
4. `requireOwnerOrOfficer`, on `PATCH` and `DELETE /api/events/:id`, loads the screening and the
   user named in the `x-user-id` header, and refuses the request unless that user posted the
   screening or is an officer.
5. `createEvent` records the user named in the `x-user-id` header as the new screening's owner.
6. In React, show the Edit and Delete buttons only to the screening's owner and to officers.

Would you agree to this as it stands? If not, what would you change?

### whole-plan

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the screening | Officer |
| --- | --- | --- | --- | --- |
| See the screenings | yes | yes | yes | yes |
| Post a screening | no | yes | yes | yes |
| Edit a screening | no | no | yes | yes |
| Delete a screening | no | no | yes | yes |
| Say you're going | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. The `users` table holds `id`, `github_id` (GitHub's id for the user), `name`, `avatar_url` and
   `role`, which is `'member'` by default. You set `'officer'` by hand for the three officers.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. `requireOwnerOrOfficer` loads the screening and refuses the request unless
   `event.owner_id === req.session.userId` or the user with that id is an officer.
4. The routes, in `backend/routes/events.js`:

   ```js
   router.get('/api/events', listEvents);
   router.post('/api/events', requireAuth, createEvent);
   router.patch('/api/events/:id', requireAuth, requireOwnerOrOfficer, updateEvent);
   router.delete('/api/events/:id', requireAuth, requireOwnerOrOfficer, deleteEvent);
   router.post('/api/events/:id/going', requireAuth, markGoing);
   router.get('/api/me', requireAuth, getMe);
   ```

5. `createEvent` and `markGoing` take the user from `req.session.userId`.
6. In React, show the Edit and Delete buttons only to the screening's owner and to officers.

Would you agree to this as it stands? If not, what would you change?

### confirm-signed-out

Your agent reports: "The rules in the table are in place and deployed to Kettlerun."

Take the rule that someone not signed in may not post a screening. Which request would you make to
show this rule holds, and what should it get back?

### confirm-not-owner

Your agent reports: "The rules in the table are in place and deployed to Kettlerun. I checked the
owner rule myself: I signed out, opened Priya's screening of *Paris, Texas*, and the Delete button
is gone."

Take the rule that a member who didn't post a screening may not delete it. Does the agent's check
show that this rule holds? Which request would you make to show this rule holds, and what should it
get back?
