Pantry is your Problem Set 3 app: a recipe box where members of a campus cooking club post recipes
and save the ones they want to try. Its React frontend is built to static files on Pagecove, a
static host, at `https://pantry.pagecove.app`. Its Express backend runs on Rivetbox, a server host,
at `https://pantry-api.rivetbox.com`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through GitHub. Once someone signs in, Pantry shows their GitHub name
and profile picture beside the recipes they posted. It doesn't use their email.

Each question below is a separate excerpt from your agent's plan. They are independent: treat each
one as if it were the only part of the plan you had seen. Answer each in two to four sentences.

### register

1. Install `passport` and `passport-github2` in `backend/`.
2. Send me your GitHub username and password. I'll sign in to GitHub and create the OAuth app for
   Pantry, then copy what the code needs from it into the config.
3. In `backend/routes/auth.js`, add `GET /auth/github`, which sends the browser to GitHub, and
   `GET /auth/github/callback`, which GitHub sends it back to.
4. Add a "Sign in with GitHub" button to `frontend/src/components/Header.jsx` that links to the
   backend's `/auth/github`.
5. Once sign-in works, remove the basic-auth middleware from `backend/server.js`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### callback

1. You create the OAuth app in GitHub's developer settings, with the name Pantry and the homepage
   URL `https://pantry.pagecove.app`.
2. In the OAuth app's settings, you enter `http://localhost:3001/auth/github/callback` as the
   authorization callback URL. That is where GitHub sends users back after they sign in.
3. In `backend/routes/auth.js`, add `GET /auth/github`, which sends the browser to GitHub, and
   `GET /auth/github/callback`, which receives the code GitHub sends back.
4. In `backend/auth.js`, set `callbackURL` to `http://localhost:3001/auth/github/callback` to match.
5. Add a "Sign in with GitHub" button to `frontend/src/components/Header.jsx` that links to the
   backend's `/auth/github`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### config-file

Once you've created the OAuth app at GitHub:

1. Add `VITE_GITHUB_CLIENT_ID` to `frontend/.env`, so the Sign in button can send the browser to
   GitHub's authorize page.
2. Add `backend/config.js`:

   ```js
   module.exports = {
     githubClientId: '<client ID from GitHub>',
     githubClientSecret: '<client secret from GitHub>',
   };
   ```

3. Commit `backend/config.js`, so the backend on Rivetbox has both values as soon as it deploys.
4. In `backend/auth.js`, read both values from `config.js` for the exchange with GitHub.
5. The client secret never reaches the browser, so this setup is secure.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### strategy

1. Install `passport` and `passport-github2` in `backend/`.
2. In `backend/auth.js`, set up the GitHub strategy:

   ```js
   passport.use(new GitHubStrategy({
     clientID: process.env.GITHUB_CLIENT_ID,
     clientSecret: process.env.GITHUB_CLIENT_SECRET,
     callbackURL: process.env.GITHUB_CALLBACK_URL,
     scope: ['repo'], // so Pantry can back up a user's recipes to a repository of theirs later
   }, verify));
   ```

3. In `verify`, take the user's GitHub id, name and avatar URL from the profile GitHub returns.
4. Add `GET /auth/github` and `GET /auth/github/callback` in `backend/routes/auth.js`.
5. Add a "Sign in with GitHub" button to `frontend/src/components/Header.jsx`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### leaked

You notice that `backend/.env`, holding `GITHUB_CLIENT_SECRET`, went out in a commit you pushed to
Pantry's public repository on GitHub. Your agent proposes this fix:

1. Delete `backend/.env` in a new commit.
2. Add `.env` to `backend/.gitignore`, so it can't be committed again.
3. Push both commits to the public repository.
4. Run `git status` to check that `.env` no longer shows up as tracked.

What do you do now, and does your agent's fix settle it?

### exchange

1. The "Sign in with GitHub" button sends the browser to GitHub, which asks the user to approve
   Pantry.
2. GitHub sends the browser back to the backend's callback URL with a code.
3. The backend sends that code, with the client ID and client secret from its environment, to
   GitHub, and gets back a token.
4. The backend uses the token to ask GitHub's API who the user is, and gets their GitHub id, name
   and avatar URL.
5. It finds or creates a row in a `users` table keyed by `github_id`, holding their name and
   picture. The table has no password column.
6. It starts a session and sends the browser a cookie. Pagecove and Rivetbox are different sites,
   so the cookie is set with `sameSite: 'none'` and `secure: true`, and CORS on the backend allows
   credentials from `https://pantry.pagecove.app`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?
