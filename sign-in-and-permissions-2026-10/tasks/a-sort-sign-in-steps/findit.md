Findit is your Problem Set 3 app: a campus lost-and-found board, where people post what they've
found and owners claim it. Its React frontend is built to static files on Brightdock, at
`https://findit.brightdock.app`, and its Express backend runs on Railspur, at
`https://findit-api.railspur.com`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through GitHub. Once someone signs in, Findit shows their GitHub name
and profile picture on each post, and shows their email to the person who claims their item.

Each card below is one step someone has proposed for adding sign-in. The cards are independent of
each other and come in no particular order. Put each card in one of three piles:

- **yours**: you do it by hand, at GitHub or in a host's settings.
- **your agent's, as written**: code or config your agent can do just as the card says.
- **change it first**: say what you would change it to, and who does the changed step.

Answer each card in one to three sentences.

### card-1

Your agent offers: "To save you a trip to GitHub's developer settings, I'll create the OAuth app
for Findit in your browser, where you're already signed in to GitHub. The later steps use what it
gives you."

Which pile, and why? If you'd change it, say to what and who does it.

### card-2

When someone signs in, ask GitHub for the `user` scope, so the backend can read their name,
picture and email.

Which pile, and why? If you'd change it, say to what and who does it.

### card-3

Your agent writes: "In the OAuth app's settings at GitHub, set the Authorization callback URL to
`http://localhost:3001/auth/github/callback`. That's where GitHub sends everyone back after they
sign in."

Which pile, and why? If you'd change it, say to what and who does it.

### card-4

Paste the client ID and the client secret into the chat. Your agent then puts the client secret in
Railspur's settings for the backend and the client ID in `frontend/.env`.

Which pile, and why? If you'd change it, say to what and who does it.

### card-5

```
Railspur, findit-api, Environment:    GITHUB_CLIENT_SECRET = <the client secret>
Brightdock, findit, Build settings:   VITE_GITHUB_CLIENT_ID = Ov23liQ7kXb2mN4pR8sT
```

Which pile, and why? If you'd change it, say to what and who does it.

### card-6

A classmate tells you that `backend/.env`, holding the client secret, is in Findit's public
repository on GitHub: it went out in a commit you pushed yesterday. Your agent proposes: "Delete
`backend/.env` in a new commit, add it to `.gitignore`, and push."

Which pile, and why? If you'd change it, say to what and who does it.

### card-7

Your agent proposes this in `backend/auth.js`:

```js
passport.use(new GitHubStrategy({
  clientID: process.env.GITHUB_CLIENT_ID,
  clientSecret: process.env.GITHUB_CLIENT_SECRET,   // stays on the server
  callbackURL: process.env.GITHUB_CALLBACK_URL,
}, async (accessToken, refreshToken, profile, done) => {
  // passport-github2 trades GitHub's code for a token, then asks GitHub's API who this is
  const user = await findOrCreateUser({ github_id: profile.id }, {
    name: profile.displayName,
    avatar_url: profile.photos[0].value,
    email: profile.emails?.[0]?.value,
  }); // users has no password column
  done(null, user);
}));
```

Which pile, and why? If you'd change it, say to what and who does it.
