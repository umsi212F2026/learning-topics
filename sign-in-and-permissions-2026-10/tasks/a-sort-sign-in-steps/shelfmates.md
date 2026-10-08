Shelfmates is your Problem Set 3 app: a shared reading list for a book club, where members add
books and mark what they've read. Its React frontend is built to static files on Leafhost, at
`https://shelfmates.leafhost.app`, and its Express backend runs on Corvane, at
`https://shelfmates-api.corvane.io`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through Google. Once someone signs in, Shelfmates shows their Google
name, profile picture and email on the club's member list, so members can reach each other.

Each card below is one step someone has proposed for adding sign-in. The cards are independent of
each other and come in no particular order. Put each card in one of three piles:

- **yours**: you do it by hand, at Google or in a host's settings.
- **your agent's, as written**: code or config your agent can do just as the card says.
- **change it first**: say what you would change it to, and who does the changed step.

Answer each card in one to three sentences.

### card-1

Your agent asks for your Google password, so that it can sign in to Google's developer console as
you and create the OAuth client for Shelfmates. The later steps use what it gives you.

Which pile, and why? If you'd change it, say to what and who does it.

### card-2

Your agent proposes this line in `backend/auth.js`:

```js
scope: ['openid', 'profile', 'email', 'https://www.googleapis.com/auth/calendar'], // so members can add meetings to their calendars later
```

Which pile, and why? If you'd change it, say to what and who does it.

### card-3

In the OAuth client's settings at Google, add `https://shelfmates-api.corvane.io/auth/google/callback`
as the authorized redirect URI.

Which pile, and why? If you'd change it, say to what and who does it.

### card-4

Put the client ID and the client secret in `frontend/.env`, as `VITE_GOOGLE_CLIENT_ID` and
`VITE_GOOGLE_CLIENT_SECRET`, so the Sign in button has both.

Which pile, and why? If you'd change it, say to what and who does it.

### card-5

Put the client secret in the backend's environment settings on Corvane, and the client ID in the
frontend's environment settings on Leafhost.

Which pile, and why? If you'd change it, say to what and who does it.

### card-6

You notice that `backend/.env`, holding the client secret, went out in a commit you pushed to
Shelfmates' public repository on GitHub. Your agent proposes: "Delete `backend/.env` in a new
commit, add it to `.gitignore`, and push. Then nobody who looks at the repository can get the
secret."

Which pile, and why? If you'd change it, say to what and who does it.

### card-7

When Google sends the browser back to the backend with a code, the backend sends that code, with
the client ID and client secret from its environment, to Google. It learns who the user is from the
ID token Google sends back, and finds or creates a `users` row keyed by Google's `sub`, holding
their name, picture and email, with no password column.

Which pile, and why? If you'd change it, say to what and who does it.
