Trailhead is your Problem Set 3 app: a board where a hiking club posts weekend trips and members
sign up for them. Its React frontend is built to static files on Pagewell, at
`https://trailhead.pagewell.app`, and its Express backend runs on Moorbolt, at
`https://trailhead-api.moorbolt.dev`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through GitHub. Once someone signs in, Trailhead shows their GitHub name
and profile picture beside the trips they signed up for. It doesn't use their email.

Each card below is one step someone has proposed for adding sign-in. The cards are independent of
each other and come in no particular order. Put each card in one of three piles:

- **yours**: you do it by hand, at GitHub or in a host's settings.
- **your agent's, as written**: code or config your agent can do just as the card says.
- **change it first**: say what you would change it to, and who does the changed step.

Answer each card in one to three sentences.

### card-1

Create an OAuth app in GitHub's developer settings for Trailhead. The later steps use what it gives
you.

Which pile, and why? If you'd change it, say to what and who does it.

### card-2

Your agent proposes this line in `backend/auth.js`:

```js
scope: ['repo'], // so we can show their projects on their trip page later
```

Which pile, and why? If you'd change it, say to what and who does it.

### card-3

"To save you hunting for the settings page on Moorbolt, paste the client ID and client secret here
in the chat. I'll put the ID in `frontend/.env` as `VITE_GITHUB_CLIENT_ID` and set the secret on
the backend host for you."

Which pile, and why? If you'd change it, say to what and who does it.

### card-4

In the OAuth app's settings at GitHub, set the callback URL to
`http://localhost:3001/auth/github/callback`.

Which pile, and why? If you'd change it, say to what and who does it.

### card-5

Put the client secret in Moorbolt's settings for the backend as `GITHUB_CLIENT_SECRET`, and the
client ID in the frontend's environment as `VITE_GITHUB_CLIENT_ID`.

Which pile, and why? If you'd change it, say to what and who does it.

### card-6

When GitHub sends the browser back to the backend with a code, the backend sends that code, with
the client ID and client secret from its environment, to GitHub. It then asks GitHub's API who the
user is, and finds or creates a `users` row keyed by `github_id`, holding their name and picture,
with no password column.

Which pile, and why? If you'd change it, say to what and who does it.

### card-7

You notice that `backend/.env`, holding the client secret, went out in a commit you pushed to
Trailhead's public repository on GitHub. Your agent proposes: "Delete `backend/.env` in a new
commit, add it to `.gitignore`, and push."

Which pile, and why? If you'd change it, say to what and who does it.
