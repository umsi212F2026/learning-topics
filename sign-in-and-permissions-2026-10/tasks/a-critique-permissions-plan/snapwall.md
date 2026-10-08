Snapwall is your Problem Set 3 app: a photo wall for a campus photography club, where members post
their photos with a caption, other members comment on them, and the club's moderators pick a photo
to feature at the top of the wall. Its React frontend is built to static files on Tidepage, at
`https://snapwall.tidepage.app`, and its Express backend runs on Ironloft, at
`https://snapwall-api.ironloft.com`, with a Postgres database. Sign-in through GitHub already
works: once someone signs in, the backend keeps them signed in with a session cookie. Now you and
your coding agent are deciding who may do what.

The backend's routes:

- `GET /api/photos`: lists every photo on the wall, with its comments.
- `POST /api/photos`: posts a photo with a caption; whoever posts it is its owner.
- `PATCH /api/photos/:id`: edits a photo's caption.
- `DELETE /api/photos/:id`: deletes a photo.
- `POST /api/photos/:id/comments`: adds a comment under a photo.
- `PATCH /api/photos/:id/featured`: features a photo at the top of the wall.
- `GET /api/me`: returns the signed-in user's GitHub name and picture.

The app's levels: a **signed-in member**; the **owner** of a photo, the member who posted it; and
a **moderator**, one of the club's two moderators, who look after the whole wall.

Each question below is a separate piece of the work. They are independent: treat each one as if
it were the only one you had seen. Answer each in two to four sentences.

### draft-table

Your agent drafts this table for `DEPLOY.md`:

| Action | Signed-in member | Owner of the photo | Moderator |
| --- | --- | --- | --- |
| See the photos and comments | yes | yes | yes |
| Post a photo | yes | yes | yes |
| Edit a caption | no | yes | yes |
| Delete a photo | no | yes | yes |
| Comment on a photo | yes | yes | yes |
| Feature a photo | no | no | yes |
| See your own name and picture | yes | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### comments-route

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the photo | Moderator |
| --- | --- | --- | --- | --- |
| See the photos and comments | yes | yes | yes | yes |
| Post a photo | no | yes | yes | yes |
| Edit a caption | no | no | yes | yes |
| Delete a photo | no | no | yes | yes |
| Comment on a photo | no | yes | yes | yes |
| Feature a photo | no | no | no | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses any request from someone not signed in.
2. `requireOwnerOrModerator` loads the photo and refuses the request unless the signed-in user
   posted it or is a moderator.
3. `requireModerator` refuses the request unless the signed-in user is a moderator.
4. Put `requireAuth` on `POST /api/photos`, `PATCH /api/photos/:id`, `DELETE /api/photos/:id`,
   `PATCH /api/photos/:id/featured` and `GET /api/me`. After it, put `requireOwnerOrModerator` on
   `PATCH` and `DELETE /api/photos/:id`, and `requireModerator` on `PATCH /api/photos/:id/featured`.
5. `POST /api/photos/:id/comments` gets no middleware: its handler saves the comment under the
   photo, with `req.session.userId` as its author.
6. In React, show the Edit and Delete buttons only to the photo's owner and to moderators, the
   Feature button only to moderators, and the comment box only to someone signed in.

Would you agree to this as it stands? If not, what would you change?

### delete-button

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the photo | Moderator |
| --- | --- | --- | --- | --- |
| See the photos and comments | yes | yes | yes | yes |
| Post a photo | no | yes | yes | yes |
| Edit a caption | no | no | yes | yes |
| Delete a photo | no | no | yes | yes |
| Comment on a photo | no | yes | yes | yes |
| Feature a photo | no | no | no | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add `requireAuth` in `backend/middleware/auth.js`, which refuses any request from someone not
   signed in. Put it on every route that changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'member'` by default. You set `'moderator'` by hand for the two
   moderators.
3. In `PATCH /api/photos/:id`, load the photo and refuse the request unless the signed-in user
   posted it or is a moderator. In `PATCH /api/photos/:id/featured`, refuse the request unless the
   signed-in user is a moderator.
4. In React, the Delete button on a photo shows only to its owner and to moderators:
   `{(user.id === photo.ownerId || user.role === 'moderator') && <DeleteButton />}`.
5. `DELETE /api/photos/:id` runs `requireAuth` and then deletes the photo.
6. In React, show the Edit button only to the photo's owner and to moderators, and the Feature
   button only to moderators.

Would you agree to this as it stands? If not, what would you change?

### new-photo

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the photo | Moderator |
| --- | --- | --- | --- | --- |
| See the photos and comments | yes | yes | yes | yes |
| Post a photo | no | yes | yes | yes |
| Edit a caption | no | no | yes | yes |
| Delete a photo | no | no | yes | yes |
| Comment on a photo | no | yes | yes | yes |
| Feature a photo | no | no | no | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add a `role` column to `users`, `'member'` by default. You set `'moderator'` by hand for the two
   moderators.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. `requireOwnerOrModerator` loads the photo and refuses the request unless
   `photo.owner_id === req.session.userId` or the user with that id is a moderator.
   `requireModerator` refuses the request unless the user with `req.session.userId` is a moderator.
4. The routes, in `backend/routes/photos.js`:

   ```js
   router.get('/api/photos', listPhotos);
   router.post('/api/photos', requireAuth, createPhoto);
   router.patch('/api/photos/:id', requireAuth, requireOwnerOrModerator, updateCaption);
   router.delete('/api/photos/:id', requireAuth, requireOwnerOrModerator, deletePhoto);
   router.post('/api/photos/:id/comments', requireAuth, addComment);
   router.patch('/api/photos/:id/featured', requireAuth, requireModerator, featurePhoto);
   router.get('/api/me', requireAuth, getMe);
   ```

5. The two handlers that record who did something, in `backend/handlers/photos.js`:

   ```js
   async function createPhoto(req, res) {
     const photo = await db.insertPhoto({
       ownerId: req.query.user,
       imageUrl: req.body.imageUrl,
       caption: req.body.caption,
     });
     res.json(photo);
   }

   async function addComment(req, res) {
     const comment = await db.insertComment({
       photoId: req.params.id,
       authorId: req.session.userId,
       text: req.body.text,
     });
     res.json(comment);
   }
   ```

6. In React, show the Edit and Delete buttons only to the photo's owner and to moderators, and the
   Feature button only to moderators.

Would you agree to this as it stands? If not, what would you change?

### whole-plan

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Owner of the photo | Moderator |
| --- | --- | --- | --- | --- |
| See the photos and comments | yes | yes | yes | yes |
| Post a photo | no | yes | yes | yes |
| Edit a caption | no | no | yes | yes |
| Delete a photo | no | no | yes | yes |
| Comment on a photo | no | yes | yes | yes |
| Feature a photo | no | no | no | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. The `users` table holds `id`, `github_id` (GitHub's id for the user), `name`, `avatar_url` and
   `role`, which is `'member'` by default. You set `'moderator'` by hand for the two moderators.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. `requireOwnerOrModerator` loads the photo and refuses the request unless
   `photo.owner_id === req.session.userId` or the user with that id is a moderator.
   `requireModerator` refuses the request unless the user with `req.session.userId` is a moderator.
4. The routes, in `backend/routes/photos.js`:

   ```js
   router.get('/api/photos', listPhotos);
   router.post('/api/photos', requireAuth, createPhoto);
   router.patch('/api/photos/:id', requireAuth, requireOwnerOrModerator, updateCaption);
   router.delete('/api/photos/:id', requireAuth, requireOwnerOrModerator, deletePhoto);
   router.post('/api/photos/:id/comments', requireAuth, addComment);
   router.patch('/api/photos/:id/featured', requireAuth, requireModerator, featurePhoto);
   router.get('/api/me', requireAuth, getMe);
   ```

5. `createPhoto` records `req.session.userId` as the new photo's owner, and `addComment` records it
   as the comment's author.
6. In React, show the Edit and Delete buttons only to the photo's owner and to moderators, the
   Feature button only to moderators, and the comment box only to someone signed in.

Would you agree to this as it stands? If not, what would you change?

### confirm-delete

Your agent reports: "The rules in the table are in place and deployed to Ironloft."

Take the rule that someone not signed in may not delete a photo. Which request would you make to
show this rule holds, and what should it get back?

### confirm-caption

Your agent reports: "The rules in the table are in place and deployed to Ironloft. I checked the
owner rule myself: I signed in as my second account, opened Dana's photo of the boathouse, and
there's no Edit button on it."

Take the rule that a member who didn't post a photo may not edit its caption. Does the agent's check
show that this rule holds? Which request would you make to show this rule holds, and what should it
get back?
