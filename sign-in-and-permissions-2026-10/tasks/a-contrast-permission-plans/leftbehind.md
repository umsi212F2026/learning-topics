Leftbehind is your Problem Set 3 app: a lost-and-found board for a college library. Whoever finds
something posts it, and the person who lost it can claim it. Its React frontend is built to static
files on Sitecrate, at `https://leftbehind.sitecrate.app`, and its Express backend runs on
Rookhouse, at `https://leftbehind-api.rookhouse.dev`, with a Postgres database. Sign-in through
Google already works.

The backend's routes:

- `GET /api/items` lists every item on the board.
- `POST /api/items` posts a found item.
- `PATCH /api/items/:id` edits an item's description, or marks it returned.
- `DELETE /api/items/:id` removes an item from the board.
- `POST /api/items/:id/claim` records that someone says an item is theirs, with a short note.
- `GET /api/me` returns the signed-in user's name and picture.

The app has three levels: any signed-in user; the poster of an item, who may edit or remove it;
and the library's desk staff, who may edit or remove any item.

You and your coding agent are giving Leftbehind its rules for who may do what. Each question below
shows two versions, A and B, of one piece of that work. The questions are independent: treat each
one as if it were the only one you had seen. For each, answer in two or three sentences: would you
agree to A, B, or both? What gives it away?

### q1

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Any signed-in user | Poster of the item | Desk staff |
| ------ | ------------------ | ------------------ | ---------- |
| View the items | yes | yes | yes |
| Post a found item | yes | yes | yes |
| Claim an item | yes | yes | yes |
| Edit an item | no | yes | yes |
| Delete an item | no | yes | yes |

**B**

| Action | Any signed-in user | Poster of the item | Desk staff | Not signed in |
| ------ | ------------------ | ------------------ | ---------- | ------------- |
| View the items | yes | yes | yes | yes |
| Post a found item | yes | yes | yes | no |
| Claim an item | yes | yes | yes | no |
| Edit an item | no | yes | yes | no |
| Delete an item | no | yes | yes | no |

Would you agree to A, B, or both? What gives it away?

### q2

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Any signed-in user | Poster of the item | Desk staff | Not signed in |
| ------ | ------------------ | ------------------ | ---------- | ------------- |
| View the items | yes | yes | yes | yes |
| Post a found item | yes | yes | yes | no |
| Claim an item | yes | yes | yes | no |
| Edit an item | no | yes | yes | no |
| Delete an item | no | yes | yes | no |

**B**

| Action | Any signed-in user | Poster of the item | Desk staff | Not signed in |
| ------ | ------------------ | ------------------ | ---------- | ------------- |
| View the items | yes | yes | yes | yes |
| Post a found item | yes | yes | yes | no |
| Claim an item | yes | yes | yes | no |
| Edit an item | no | yes | yes | no |

Would you agree to A, B, or both? What gives it away?

### q3

Your agent offers two versions of one step of its plan.

**A**

> Step 5. In `ItemCard.jsx`, show the Edit and Delete buttons only to the item's poster and to
> desk staff: `{(user.id === item.posterId || user.isDesk) && <ItemButtons />}`. The routes already
> check that someone is signed in, so hiding the buttons covers the owner rule with no extra server
> code.

**B**

> Step 5. In `ItemCard.jsx`, show the Edit and Delete buttons only to the item's poster and to
> desk staff: `{(user.id === item.posterId || user.isDesk) && <ItemButtons />}`. On `PATCH` and
> `DELETE /api/items/:id`, the server also checks that the signed-in user posted the item or is
> desk staff, and refuses the request if not.

Would you agree to A, B, or both? What gives it away?

### q4

Your agent offers two versions of the backend's route list. `requireAuth` refuses any request with
no signed-in user; `requirePosterOrDesk` refuses anyone but the item's poster or desk staff.

**A**

```js
router.get('/api/items', listItems);
router.post('/api/items', requireAuth, createItem);
router.patch('/api/items/:id', requireAuth, requirePosterOrDesk, updateItem);
router.delete('/api/items/:id', requireAuth, requirePosterOrDesk, deleteItem);
router.post('/api/items/:id/claim', requireAuth, claimItem);
router.get('/api/me', requireAuth, getMe);
```

**B**

```js
router.get('/api/items', listItems);
router.post('/api/items', requireAuth, createItem);
router.patch('/api/items/:id', requireAuth, requirePosterOrDesk, updateItem);
router.delete('/api/items/:id', requireAuth, requirePosterOrDesk, deleteItem);
router.post('/api/items/:id/claim', claimItem);
router.get('/api/me', requireAuth, getMe);
```

Would you agree to A, B, or both? What gives it away?

### q5

Your agent offers two versions of the handler for `POST /api/items/:id/claim`, which runs after
`requireAuth`.

**A**

```js
async function claimItem(req, res) {
  const userId = req.body.userId;
  await db.query(
    'INSERT INTO claims (item_id, user_id, note) VALUES ($1, $2, $3)',
    [req.params.id, userId, req.body.note]
  );
  res.status(201).json({ ok: true });
}
```

**B**

```js
async function claimItem(req, res) {
  const userId = req.session.userId;
  await db.query(
    'INSERT INTO claims (item_id, user_id, note) VALUES ($1, $2, $3)',
    [req.params.id, userId, req.body.note]
  );
  res.status(201).json({ ok: true });
}
```

Would you agree to A, B, or both? What gives it away?

### q6

Your agent offers two versions of its plan for enforcing the rules.

**A**

> 1. The `users` table has one row per person: `id`, `google_sub`, `name`, `picture`, and `role`,
>    which is `member` or `desk`. There is no password column.
> 2. `requireAuth` runs on every route that changes data, and refuses a request with no signed-in
>    user.
> 3. On `PATCH` and `DELETE /api/items/:id`, the server loads the item and refuses the request
>    unless the session's user posted it or has the `desk` role.
> 4. React also hides the Edit and Delete buttons from everyone else.

**B**

> 1. The `users` table has one row per person: `id`, `google_sub`, `name`, and `picture`. There is
>    no password column. A separate `desk_staff` table holds the `user_id` of each desk staff member.
> 2. `requireAuth` runs on every route that changes data, and refuses a request with no signed-in
>    user.
> 3. On `PATCH` and `DELETE /api/items/:id`, the server loads the item and refuses the request
>    unless the session's user posted it or is in `desk_staff`.
> 4. React also hides the Edit and Delete buttons from everyone else.

Would you agree to A, B, or both? What gives it away?

### q7

Your agent reports that the rules are in place. It offers two ways to confirm that someone who
isn't signed in can't post a found item.

**A**

> From a terminal, with no session cookie, send `POST /api/items` with a short description.

**B**

> Sign out, open the board in the browser, and check that the Post an Item button is gone.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?

### q8

Your agent reports that the rules are in place. It offers two ways to confirm that only an item's
poster or desk staff can remove it. Item 12 was posted from your own account, which isn't desk
staff.

**A**

> From a terminal, with no session cookie, send `DELETE /api/items/12`.

**B**

> From a terminal, with the session cookie of a second account that isn't desk staff, send
> `DELETE /api/items/12`.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?
