Findit is your Problem Set 3 app: a lost-and-found board for a residence hall, where residents post
things they've found. Once the person who lost an item picks it up, the resident who posted it, or
one of the hall's front desk staff, marks it claimed. Its React frontend is built to static files on Slatebay, at `https://findit.slatebay.app`, and its Express backend runs
on Hearthbox, at `https://findit-api.hearthbox.com`, with a Postgres database. Sign-in through
Google already works: once someone signs in, the backend keeps them signed in with a session
cookie. Now you and your coding agent are deciding who may do what.

The backend's routes:

- `GET /api/items`: lists every item on the board.
- `POST /api/items`: posts a found item; whoever posts it is the post's owner.
- `PATCH /api/items/:id`: edits a post's description or where the item can be picked up.
- `PATCH /api/items/:id/claimed`: marks an item claimed.
- `DELETE /api/items/:id`: deletes a post.
- `GET /api/me`: returns the signed-in user's Google name and picture.

The app's levels: a **signed-in resident**; the **owner** of a post, the resident who posted it;
and a **desk worker**, one of the hall's front desk staff, who look after the whole board.

Each question below is a separate piece of the work. They are independent: treat each one as if
it were the only one you had seen. Answer each in two to four sentences.

### draft-table

Your agent drafts this table for `DEPLOY.md`:

| Action | Not signed in | Signed-in resident | Owner of the post | Desk worker |
| --- | --- | --- | --- | --- |
| See the items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit a post | no | no | yes | yes |
| Mark an item claimed | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### edit-button

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in resident | Owner of the post | Desk worker |
| --- | --- | --- | --- | --- |
| See the items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit a post | no | no | yes | yes |
| Mark an item claimed | no | no | yes | yes |
| Delete a post | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add `requireAuth` in `backend/middleware/auth.js`, which refuses any request from someone not
   signed in. Put it on every route that changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'resident'` by default. You set `'desk'` by hand for the front
   desk staff.
3. In `PATCH /api/items/:id/claimed` and `DELETE /api/items/:id`, load the item and refuse the
   request unless the signed-in user posted it or is a desk worker.
4. Editing a post is handled in React: the Edit button shows only when
   `user.id === item.ownerId || user.role === 'desk'`. `PATCH /api/items/:id` itself checks only
   that someone is signed in.
5. In React, show the Mark claimed and Delete buttons only to the post's owner and to desk workers.

Would you agree to this as it stands? If not, what would you change?

### claim-step

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in resident | Owner of the post | Desk worker |
| --- | --- | --- | --- | --- |
| See the items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit a post | no | no | yes | yes |
| Mark an item claimed | no | no | yes | yes |
| Delete a post | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses any request from someone not signed in.
2. `requireOwnerOrDesk` loads the item and refuses the request unless the signed-in user posted it
   or is a desk worker.
3. Put `requireAuth` on `POST /api/items`, `PATCH /api/items/:id`, `DELETE /api/items/:id` and
   `GET /api/me`, with `requireOwnerOrDesk` after it on `PATCH /api/items/:id` and
   `DELETE /api/items/:id`.
4. Add the handler for `PATCH /api/items/:id/claimed`: it sets the item's `claimed` column to true
   and saves it.
5. In React, show the Edit, Mark claimed and Delete buttons only to the post's owner and to desk
   workers.

Would you agree to this as it stands? If not, what would you change?

### owner-check

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in resident | Owner of the post | Desk worker |
| --- | --- | --- | --- | --- |
| See the items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit a post | no | no | yes | yes |
| Mark an item claimed | no | no | yes | yes |
| Delete a post | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add a `role` column to `users`, `'resident'` by default. You set `'desk'` by hand for the front
   desk staff.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. `requireOwnerOrDesk`, in `backend/middleware/auth.js`:

   ```js
   async function requireOwnerOrDesk(req, res, next) {
     const item = await db.getItem(req.params.id);
     const user = await db.getUser(req.body.userId);
     if (item.owner_id === user.id || user.role === 'desk') return next();
     res.status(403).json({ error: 'Not your post' });
   }
   ```

4. The routes, in `backend/routes/items.js`:

   ```js
   router.get('/api/items', listItems);
   router.post('/api/items', requireAuth, createItem);
   router.patch('/api/items/:id', requireAuth, requireOwnerOrDesk, updateItem);
   router.patch('/api/items/:id/claimed', requireAuth, requireOwnerOrDesk, markClaimed);
   router.delete('/api/items/:id', requireAuth, requireOwnerOrDesk, deleteItem);
   router.get('/api/me', requireAuth, getMe);
   ```

5. `createItem` records `req.session.userId` as the new post's owner.
6. In React, show the Edit, Mark claimed and Delete buttons only to the post's owner and to desk
   workers.

Would you agree to this as it stands? If not, what would you change?

### whole-plan

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in resident | Owner of the post | Desk worker |
| --- | --- | --- | --- | --- |
| See the items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit a post | no | no | yes | yes |
| Mark an item claimed | no | no | yes | yes |
| Delete a post | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. The `users` table holds `id`, `google_id` (Google's id for the user), `name`, `picture_url` and
   `role`, which is `'resident'` by default. You set `'desk'` by hand for the front desk staff.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. The routes, in `backend/routes/items.js`:

   ```js
   router.get('/api/items', listItems);
   router.post('/api/items', requireAuth, createItem);
   router.patch('/api/items/:id', requireAuth, updateItem);
   router.patch('/api/items/:id/claimed', requireAuth, markClaimed);
   router.delete('/api/items/:id', requireAuth, deleteItem);
   router.get('/api/me', requireAuth, getMe);
   ```

4. `updateItem`, `markClaimed` and `deleteItem` each start by loading the item and calling
   `canChange(item, req.session.userId)`, which loads that user and returns true only if they
   posted the item or their role is `'desk'`. When it returns false, the handler sends 403 and
   stops.
5. `createItem` records `req.session.userId` as the new post's owner.
6. In React, show the Edit, Mark claimed and Delete buttons only to the post's owner and to desk
   workers.

Would you agree to this as it stands? If not, what would you change?

### confirm-claimed

Your agent reports: "The rules in the table are in place and deployed to Hearthbox. I checked the
sign-in rule myself: I opened the board in a private window, where I'm not signed in, and
there's no Mark claimed button on any post."

Take the rule that someone not signed in may not mark an item claimed. Does the agent's check show
that this rule holds? Which request would you make to show this rule holds, and what should it get
back?

### confirm-edit

Your agent reports: "The rules in the table are in place and deployed to Hearthbox."

Take the rule that a resident who didn't post an item may not edit its post. Which request would
you make to show this rule holds, and what should it get back?
