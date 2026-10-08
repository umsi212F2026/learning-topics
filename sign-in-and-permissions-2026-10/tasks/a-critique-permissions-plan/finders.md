Finders is a lost-and-found board for one residence hall. Residents post things they have lost
or found, with a title, a short description and a photo, and the board shows each item with the
name and email of the resident who posted it, so the finder and the loser can get in touch. It is
a React frontend built to static files at `https://finders.tidepage.app`, an Express backend at
`https://finders-api.harborbox.com`, and a Postgres database. Sign-in through Google already
works.

The backend's routes:

- `GET /api/items`: lists every item on the board.
- `POST /api/items`: posts a new item.
- `PATCH /api/items/:id`: edits an item's title, description or photo.
- `POST /api/items/:id/handed-back`: marks an item as handed back, which takes it off the board.
- `DELETE /api/items/:id`: deletes an item.

The app has four levels: someone not signed in; a signed-in resident; the owner of an item,
meaning the resident who posted it; and desk staff, who run the hall's front desk and look after
the board.

Each question below is a separate piece of the work, and they are independent of each other.
Answer each in two to four sentences.

### q1

Your agent has drafted this table for `DEPLOY.md`.

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### q2

Your agent has drafted this table for `DEPLOY.md`.

| Action | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes |
| Post an item | yes | yes | yes |
| Edit an item | no | yes | yes |
| Mark an item handed back | no | yes | yes |
| Delete an item | no | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### q3

Your agent proposes this table, and this plan for enforcing it.

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

1. Add `requireAuth` in `backend/middleware/auth.js`. It looks for a signed-in user in the
   session and refuses the request if there isn't one.
2. Put `requireAuth` on every route that changes data: `POST /api/items`,
   `PATCH /api/items/:id`, `POST /api/items/:id/handed-back` and `DELETE /api/items/:id`.
3. Add `requireOwnerOrStaff` in the same file. It loads the item and refuses the request unless
   the signed-in user posted it or has the `staff` role. Put it after `requireAuth` on
   `POST /api/items/:id/handed-back` and `DELETE /api/items/:id`.
4. For editing, hide the Edit button in `ItemCard.jsx` from everyone but the item's owner and
   desk staff: `{(user.id === item.ownerId || user.role === 'staff') && <EditButton />}`.
   `PATCH /api/items/:id` keeps `requireAuth` only.
5. Hide the Handed back and Delete buttons the same way, and hide Post an item from anyone not
   signed in.

Would you agree to this as it stands? If not, what would you change?

### q4

Your agent proposes this table, and this plan for enforcing it.

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

1. Add `requireAuth` in `backend/middleware/auth.js`. It looks for a signed-in user in the
   session and refuses the request if there isn't one.
2. Add `requireOwnerOrStaff` in the same file. It loads the item and refuses the request unless
   the signed-in user posted it or has the `staff` role.
3. Wire them up in `backend/routes/items.js`:

   ```js
   router.get('/api/items', listItems);
   router.post('/api/items', requireAuth, createItem);
   router.patch('/api/items/:id', requireAuth, requireOwnerOrStaff, updateItem);
   router.post('/api/items/:id/handed-back', requireAuth, requireOwnerOrStaff, markHandedBack);
   router.delete('/api/items/:id', deleteItem);
   ```

4. `GET /api/items` stays open, since anyone may view the board.
5. In React, hide Post an item from anyone not signed in, and hide Edit, Handed back and Delete
   from everyone but the item's owner and desk staff.

Would you agree to this as it stands? If not, what would you change?

### q5

Your agent proposes this table, and this plan for enforcing it.

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

1. Add `requireAuth` in `backend/middleware/auth.js`. It looks for a signed-in user in the
   session and refuses the request if there isn't one.
2. After sign-in, React fetches the user once and keeps `user.id`. `frontend/src/api.js` adds it
   to every request as an `x-user-id` header.
3. Add `requireOwnerOrStaff` in the same file as `requireAuth`. It loads the item, and the user
   whose id is in `req.headers['x-user-id']`, and refuses the request unless that user posted the
   item or has the `staff` role. React already knows who is signed in, so passing the id along
   keeps this middleware short.
4. Put `requireAuth` on `POST /api/items`, and `requireAuth` then `requireOwnerOrStaff` on
   `PATCH /api/items/:id`, `POST /api/items/:id/handed-back` and `DELETE /api/items/:id`.
   `GET /api/items` stays open.
5. In React, hide Post an item from anyone not signed in, and hide Edit, Handed back and Delete
   from everyone but the item's owner and desk staff.

Would you agree to this as it stands? If not, what would you change?

### q6

Your agent proposes this table, and this plan for enforcing it.

| Action | Not signed in | Signed-in resident | Owner of the item | Desk staff |
| ------ | ------------- | ------------------ | ----------------- | ---------- |
| View the board | yes | yes | yes | yes |
| Post an item | no | yes | yes | yes |
| Edit an item | no | no | yes | yes |
| Mark an item handed back | no | no | yes | yes |
| Delete an item | no | no | yes | yes |

1. The `users` table has `id`, `google_sub` (unique), `name`, `email` and `role`, which is
   `'resident'` unless set to `'staff'`. There is no password column. The sign-in route finds or
   creates the row by `google_sub`.
2. Add `requireAuth` in `backend/middleware/auth.js`. It reads `req.session.userId`, refuses the
   request if there isn't one, and loads that user into `req.user`.
3. Add `requireOwnerOrStaff` in the same file. It loads the item and refuses the request unless
   `item.owner_id === req.user.id` or `req.user.role === 'staff'`.
4. Routes: `GET /api/items` stays open; `POST /api/items` gets `requireAuth`;
   `PATCH /api/items/:id`, `POST /api/items/:id/handed-back` and `DELETE /api/items/:id` get
   `requireAuth` then `requireOwnerOrStaff`.
5. `createItem` sets the new item's `owner_id` from `req.user.id`.
6. In React, hide Post an item from anyone not signed in, and hide Edit, Handed back and Delete
   from everyone but the item's owner and desk staff.
7. For desk staff, you set `role` to `'staff'` on their rows in the database by hand once they
   have signed in.

Would you agree to this as it stands? If not, what would you change?

### q7

Your agent reports that the rules for who may do what are now in place on the live app.

Which request would you make to show that someone not signed in can't post an item, and what
should it get back?

### q8

Your agent reports that the rules for who may do what are now in place on the live app, and
adds: "I checked this myself. I opened one of your items in a private window, and the Delete
button isn't there, so other residents can't delete your posts."

Does that show that a signed-in resident who didn't post an item can't delete it? If not, which
request would you make to show it, and what should it get back?
