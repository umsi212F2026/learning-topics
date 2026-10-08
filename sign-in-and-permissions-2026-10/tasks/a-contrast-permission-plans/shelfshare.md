Shelfshare is your Problem Set 3 app: a shared reading list for a campus book club. Members add
books they'd like the club to read, and vote on which one comes next. Its React frontend is built
to static files on Staticove, at `https://shelfshare.staticove.app`, and its Express backend runs on
Portwell, at `https://shelfshare-api.portwell.dev`, with a Postgres database. Sign-in through GitHub
already works.

The backend's routes:

- `GET /api/books` lists every book on the reading list, with its votes.
- `POST /api/books` adds a book to the list.
- `PATCH /api/books/:id` edits a book's title, author or note.
- `DELETE /api/books/:id` removes a book from the list.
- `POST /api/books/:id/vote` adds a vote for a book as the club's next read.
- `GET /api/me` returns the signed-in member's GitHub name and picture.

The app has three levels: any signed-in member; the member who added a book, who may edit or
remove it; and the club's two organizers, who may edit or remove any book.

You and your coding agent are giving Shelfshare its rules for who may do what. Each question below
shows two versions, A and B, of one piece of that work. The questions are independent: treat each
one as if it were the only one you had seen. For each, answer in two or three sentences: would you
agree to A, B, or both? What gives it away?

### q1

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Any signed-in member | Member who added the book | Organizer | Not signed in |
| ------ | -------------------- | ------------------------- | --------- | ------------- |
| See the reading list | yes | yes | yes | yes |
| Add a book | yes | yes | yes | no |
| Vote for a book | yes | yes | yes | no |
| Edit a book | no | yes | yes | no |
| Remove a book | no | yes | yes | no |

**B**

| Action | Any signed-in member | Member who added the book | Organizer | Not signed in |
| ------ | -------------------- | ------------------------- | --------- | ------------- |
| See the reading list | yes | yes | yes | yes |
| Add a book | yes | yes | yes | no |
| Vote for a book | yes | yes | yes | no |
| Remove a book | no | yes | yes | no |

> This covers everything the backend lets anyone do.

Would you agree to A, B, or both? What gives it away?

### q2

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Any signed-in member | Member who added the book | Organizer |
| ------ | -------------------- | ------------------------- | --------- |
| See the reading list | yes | yes | yes |
| Add a book | yes | yes | yes |
| Vote for a book | yes | yes | yes |
| Edit a book | no | yes | yes |
| Remove a book | no | yes | yes |

**B**

| Action | Any signed-in member | Member who added the book | Organizer | Not signed in |
| ------ | -------------------- | ------------------------- | --------- | ------------- |
| See the reading list | yes | yes | yes | yes |
| Add a book | yes | yes | yes | no |
| Vote for a book | yes | yes | yes | no |
| Edit a book | no | yes | yes | no |
| Remove a book | no | yes | yes | no |

Would you agree to A, B, or both? What gives it away?

### q3

Your agent offers two versions of one step of its plan.

**A**

> Step 4. In `BookPage.jsx`, show the Edit and Remove buttons only to the member who added the
> book and to organizers, and have the `/books/:id/edit` page send anyone else back to the list.
> On `PATCH` and `DELETE /api/books/:id`, the server also checks that the signed-in member added
> the book or is an organizer, and refuses the request if not.

**B**

> Step 4. In `BookPage.jsx`, show the Edit and Remove buttons only to the member who added the
> book and to organizers, and have the `/books/:id/edit` page send anyone else back to the list.

Would you agree to A, B, or both? What gives it away?

### q4

Your agent offers two versions of the backend's route list. `requireSignIn` refuses any request
with no signed-in member; `requireAdderOrOrganizer` refuses anyone but the member who added the
book or an organizer.

**A**

```js
router.get('/api/books', listBooks);
router.post('/api/books', addBook);
router.patch('/api/books/:id', requireSignIn, requireAdderOrOrganizer, updateBook);
router.delete('/api/books/:id', requireSignIn, requireAdderOrOrganizer, deleteBook);
router.post('/api/books/:id/vote', requireSignIn, voteForBook);
router.get('/api/me', requireSignIn, getMe);
```

**B**

```js
router.get('/api/books', listBooks);
router.post('/api/books', requireSignIn, addBook);
router.patch('/api/books/:id', requireSignIn, requireAdderOrOrganizer, updateBook);
router.delete('/api/books/:id', requireSignIn, requireAdderOrOrganizer, deleteBook);
router.post('/api/books/:id/vote', requireSignIn, voteForBook);
router.get('/api/me', requireSignIn, getMe);
```

Would you agree to A, B, or both? What gives it away?

### q5

Your agent offers two versions of the handler for `POST /api/books/:id/vote`, which runs after
`requireSignIn`.

**A**

```js
async function voteForBook(req, res) {
  const memberId = req.body.memberId;
  await db.query(
    'INSERT INTO votes (book_id, member_id) VALUES ($1, $2) ON CONFLICT DO NOTHING',
    [req.params.id, memberId]
  );
  res.status(201).json({ ok: true });
}
```

**B**

```js
async function voteForBook(req, res) {
  const memberId = req.session.memberId;
  await db.query(
    'INSERT INTO votes (book_id, member_id) VALUES ($1, $2) ON CONFLICT DO NOTHING',
    [req.params.id, memberId]
  );
  res.status(201).json({ ok: true });
}
```

Would you agree to A, B, or both? What gives it away?

### q6

Your agent offers two versions of its plan for enforcing the rules.

**A**

> 1. The `members` table has one row per person: `id`, `github_id`, `name`, `picture`, and `role`,
>    which is `member` or `organizer`. There is no password column.
> 2. `requireSignIn` runs on every route that changes data, and refuses a request with no
>    signed-in member.
> 3. A `requireAdderOrOrganizer` middleware runs on `PATCH` and `DELETE /api/books/:id`: it loads
>    the book and refuses the request unless the session's member added it or is an organizer.
> 4. Every handler takes the member from the session.

**B**

> 1. The `members` table has one row per person: `id`, `github_id`, `name`, `picture`, and `role`,
>    which is `member` or `organizer`. There is no password column.
> 2. `requireSignIn` runs on every route that changes data, and refuses a request with no
>    signed-in member.
> 3. Inside `updateBook` and `deleteBook`, before changing anything, the handler loads the book and
>    refuses the request unless the session's member added it or is an organizer.
> 4. Every handler takes the member from the session.

Would you agree to A, B, or both? What gives it away?

### q7

Your agent reports that the rules are in place. It offers two ways to confirm that someone who
isn't signed in can't vote for a book.

**A**

> Sign out, open the reading list in the browser, and check that no book shows a Vote button.

**B**

> From a terminal, with no session cookie, send `POST /api/books/7/vote`.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?

### q8

Your agent reports that the rules are in place. It offers two ways to confirm that only the member
who added a book or an organizer can edit it. Book 7 was added from your own account, which isn't
an organizer.

**A**

> From a terminal, with the session cookie of a second account that isn't an organizer, send
> `PATCH /api/books/7` with a new note.

**B**

> From a terminal, with no session cookie, send `PATCH /api/books/7` with a new note.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?
