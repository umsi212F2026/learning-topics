Finders is a lost-and-found board for a university library. Someone who finds a phone, a water
bottle or a set of keys posts it, and its owner can spot it and come to the front desk. The React
frontend is built to static files on Pagewick, at `https://finders.pagewick.app`. The Express
backend runs on Harborbox, at `https://finders-api.harborbox.com`, with a Postgres database.
Sign-in through GitHub already works: the backend starts a session when someone signs in, and its
`requireAuth` middleware turns away a request from anyone who isn't signed in.

The backend's routes:

- `GET /api/items`: lists every item posted, newest first.
- `POST /api/items`: posts a found item, with a description and where it was found.
- `PATCH /api/items/:id`: edits an item, or marks it returned to its owner.
- `DELETE /api/items/:id`: removes an item.
- `GET /api/me`: says who is signed in, if anyone.

The app has four levels: someone not signed in, any signed-in user, the poster of an item (the
person who posted it), and desk staff (the library's front-desk workers, who look after every
item). The tables below cover the item routes; `GET /api/me` and the sign-in routes are left out
of them.

Each question shows two versions of one piece of the work, A and B, that your agent has written.
The questions are independent of each other. Answer each in two or three sentences.

### q1

Two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Not signed in | Signed-in user | Poster of the item | Desk staff |
| ------ | ------------- | -------------- | ------------------ | ---------- |
| See the list of items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit an item or mark it returned | no | no | yes | yes |

**B**

| Action | Not signed in | Signed-in user | Poster of the item | Desk staff |
| ------ | ------------- | -------------- | ------------------ | ---------- |
| See the list of items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit an item or mark it returned | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

Would you agree to A, B, or both? What gives it away?

### q2

Two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Not signed in | Signed-in user | Poster of the item | Desk staff |
| ------ | ------------- | -------------- | ------------------ | ---------- |
| See the list of items | yes | yes | yes | yes |
| Post a found item | no | yes | yes | yes |
| Edit an item or mark it returned | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

**B**

| Action | Signed-in user | Poster of the item | Desk staff |
| ------ | -------------- | ------------------ | ---------- |
| See the list of items | yes | yes | yes |
| Post a found item | yes | yes | yes |
| Edit an item or mark it returned | no | yes | yes |
| Delete an item | no | yes | yes |

Would you agree to A, B, or both? What gives it away?

### q3

Two versions of one step in your agent's plan for enforcing the table.

**A**

> 4. Edit and Delete are for the item's poster and desk staff. In `ItemCard.jsx`, I'll show the
>    Edit and Delete buttons only when the signed-in user posted the item or is desk staff. The
>    `PATCH` and `DELETE` routes keep `requireAuth`, so only signed-in users reach them.

**B**

> 4. Edit and Delete are for the item's poster and desk staff. In `ItemCard.jsx`, I'll show the
>    Edit and Delete buttons only when the signed-in user posted the item or is desk staff. The
>    `PATCH` and `DELETE` routes get `requireAuth` and a new `requireOwnerOrStaff`, which checks
>    the session's user against the item's poster and their role.

Would you agree to A, B, or both? What gives it away?

### q4

Two versions of the route list in `backend/routes/items.js`. `requireOwnerOrStaff` lets a request
through only if the signed-in user posted the item or is desk staff.

**A**

```js
router.get('/api/items', listItems);
router.post('/api/items', requireAuth, createItem);
router.patch('/api/items/:id', requireAuth, requireOwnerOrStaff, updateItem);
router.delete('/api/items/:id', requireAuth, requireOwnerOrStaff, deleteItem);
router.get('/api/me', getMe);
```

**B**

```js
router.get('/api/items', listItems);
router.post('/api/items', createItem);
router.patch('/api/items/:id', requireAuth, requireOwnerOrStaff, updateItem);
router.delete('/api/items/:id', requireAuth, requireOwnerOrStaff, deleteItem);
router.get('/api/me', getMe);
```

Would you agree to A, B, or both? What gives it away?

### q5

Two versions of the middleware that decides whether a request may edit or delete an item.

**A**

```js
// Runs after requireAuth on PATCH and DELETE /api/items/:id
async function requireOwnerOrStaff(req, res, next) {
  const item = await db.getItem(req.params.id);
  if (!item) return res.status(404).end();
  const userId = req.get('x-user-id'); // ItemCard.jsx sends the signed-in user's id
  const user = await db.getUser(userId);
  if (item.ownerId === user.id || user.role === 'staff') return next();
  return res.status(403).end();
}
```

**B**

```js
// Runs after requireAuth on PATCH and DELETE /api/items/:id
async function requireOwnerOrStaff(req, res, next) {
  const item = await db.getItem(req.params.id);
  if (!item) return res.status(404).end();
  const userId = req.session.userId; // set when the user signed in with GitHub
  const user = await db.getUser(userId);
  if (item.ownerId === user.id || user.role === 'staff') return next();
  return res.status(403).end();
}
```

Would you agree to A, B, or both? What gives it away?

### q6

Two versions of your agent's whole plan for enforcing the table.

**A**

> 1. The `users` table keeps `id`, `github_id`, `name` and `role` (`member` or `staff`), with no
>    password column.
> 2. `POST`, `PATCH` and `DELETE` on `/api/items` all get `requireAuth`.
> 3. A `requireOwnerOrStaff` middleware on `PATCH` and `DELETE` looks up the item and lets the
>    request through only if the session's user posted it or has the `staff` role.
> 4. `ItemCard.jsx` shows Edit and Delete only to the poster and to staff.

**B**

> 1. The `users` table keeps `id`, `github_id`, `name` and `role` (`member` or `staff`), with no
>    password column.
> 2. `POST`, `PATCH` and `DELETE` on `/api/items` all get `requireAuth`.
> 3. Inside `updateItem` and `deleteItem`, before changing anything, the handler looks up the item
>    and goes on only if the session's user posted it or has the `staff` role.
> 4. `ItemCard.jsx` shows Edit and Delete only to the poster and to staff.

Would you agree to A, B, or both? What gives it away?

### q7

Your agent reports that the rules are in place. It offers two ways to confirm that someone who
isn't signed in can't post an item.

**A**

> Sign out of Finders in your browser, open the board, and check that the "Post an item" button
> is gone.

**B**

> From a terminal, with no session cookie, send `POST https://finders-api.harborbox.com/api/items`
> with a made-up item's description.

Would you agree to A, B, or both? What gives it away? Also say what the request you chose should
get back.

### q8

Your agent reports that the rules are in place. It offers two ways to confirm that a signed-in
user who didn't post an item can't delete it. Item 42 was posted by your main account.

**A**

> Sign in to Finders with a second GitHub account, then send
> `DELETE https://finders-api.harborbox.com/api/items/42` from a terminal with that account's
> session cookie.

**B**

> Sign out of Finders, then send `DELETE https://finders-api.harborbox.com/api/items/42` from a
> terminal with no session cookie. I tried this and it was refused, so non-posters are blocked.

Would you agree to A, B, or both? What gives it away? Also say what the request you chose should
get back.
