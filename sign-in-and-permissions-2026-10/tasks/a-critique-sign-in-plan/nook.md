Nook is your Problem Set 3 app: a study-room finder where students see which library study rooms
are free and book one for an hour. Its React frontend is built to static files on Paperkite, a
static host, at `https://nook.paperkite.app`. Its Express backend runs on Forgeline, a server host,
at `https://nook-api.forgeline.com`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through GitHub. Once someone signs in, Nook shows their GitHub name and
profile picture beside each room they have booked, and emails a booking confirmation to the email
address on their GitHub account.

Each question below is a separate excerpt from your agent's plan. They are independent: treat each
one as if it were the only part of the plan you had seen. Answer each in two to four sentences.

### browser

1. Install `passport` and `passport-github2` in `backend/`.
2. I'll open GitHub's developer settings in your browser, where you're already signed in to GitHub,
   create an OAuth app named Nook, and copy what the code needs from it into the config.
3. In `backend/routes/auth.js`, add `GET /auth/github`, which sends the browser to GitHub, and
   `GET /auth/github/callback`, which GitHub sends it back to.
4. Add a "Sign in with GitHub" button to `frontend/src/components/TopBar.jsx` that links to the
   backend's `/auth/github`.
5. Once sign-in works, remove the basic-auth middleware from `backend/server.js` and the
   `BASIC_AUTH_PASSWORD` line from `backend/.env.example`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### one-callback

1. You create the OAuth app in GitHub's developer settings, with the name Nook and the homepage URL
   `https://nook.paperkite.app`.
2. In the OAuth app's settings, you enter `http://localhost:3001/auth/github/callback` as the
   authorization callback URL.
3. Add `GITHUB_CALLBACK_URL=http://localhost:3001/auth/github/callback` to `backend/.env`, and in
   `backend/auth.js` set `callbackURL` from `process.env.GITHUB_CALLBACK_URL`. Since the backend
   reads its callback URL from the environment, this one registration covers the live site too.
4. In `backend/routes/auth.js`, add `GET /auth/github`, which sends the browser to GitHub, and
   `GET /auth/github/callback`, which receives the code GitHub sends back.
5. Add a "Sign in with GitHub" button to `frontend/src/components/TopBar.jsx` that links to
   `${import.meta.env.VITE_API_URL}/auth/github`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### env-lines

Once you've created the OAuth app at GitHub:

1. Add these lines to `frontend/.env`, and the same two to Paperkite's build settings for the live
   site:

   ```
   VITE_GITHUB_CLIENT_ID=<client ID from GitHub>
   VITE_GITHUB_CLIENT_SECRET=<client secret from GitHub>
   ```

2. You set `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` in Forgeline's settings for the backend,
   and in `backend/.env` on your laptop, which `.gitignore` already keeps out of the repository.
3. In `frontend/src/components/TopBar.jsx`, the Sign in button builds GitHub's authorize URL from
   `import.meta.env.VITE_GITHUB_CLIENT_ID`.
4. In `backend/auth.js`, read `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` from `process.env` for
   the exchange with GitHub.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### user-scope

1. In `backend/auth.js`, set up the GitHub strategy with `clientID`, `clientSecret` and
   `callbackURL` read from `process.env`.
2. I'll request the `user` scope, which GitHub describes as "read and write access to profile
   info", so it covers each user's profile and their email address.
3. In `verify`, take the user's GitHub id, name, avatar URL and primary email from what GitHub
   returns.
4. In `backend/mail.js`, send the booking confirmation to that email address when a room is
   booked.
5. Add `GET /auth/github` and `GET /auth/github/callback` in `backend/routes/auth.js`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### force-push

You notice that `backend/.env`, holding `GITHUB_CLIENT_SECRET`, went out in a commit you pushed to
Nook's public repository on GitHub forty minutes ago. Your agent proposes this fix:

1. Delete `backend/.env` in a new commit, and add `.env` to `backend/.gitignore`.
2. Rewrite the history with `git filter-repo --path backend/.env --invert-paths`, so the file is
   gone from every commit.
3. Force-push to the public repository.
4. The repository has two stars and the commit was up for under an hour, so nobody will have
   copied the secret. The client secret can stay as it is.

What do you do now, and does your agent's fix settle it?

### passport-flow

1. Run `npm install passport passport-github2 express-session connect-pg-simple` in `backend/`.
2. Add `VITE_GITHUB_CLIENT_ID` to `frontend/.env`. In `TopBar.jsx`, the Sign in button builds
   GitHub's authorize URL from it, with `redirect_uri` set to
   `${import.meta.env.VITE_API_URL}/auth/github/callback` and `scope=read:user user:email`.
3. In `backend/auth.js`, `new GitHubStrategy({ clientID, clientSecret, callbackURL })` reads all
   three from `process.env`; you set `GITHUB_CLIENT_SECRET` in Forgeline's settings. On
   `GET /auth/github/callback`, `passport.authenticate('github')` swaps the code for an access token
   and fetches the user's profile and email from GitHub's API.
4. In `verify`, call `findOrCreateUser({ githubId: profile.id })` in `backend/db/users.js`, which
   upserts into a `users` table with a unique `github_id` column, `name`, `avatar_url` and `email`.
   No password column.
5. `express-session` with `connect-pg-simple` keeps sessions in Postgres;
   `passport.serializeUser` stores the user's row id. The cookie is
   `{ sameSite: 'none', secure: true, httpOnly: true }`, since Paperkite and Forgeline are different
   sites, with `app.set('trust proxy', 1)` and
   `cors({ origin: process.env.FRONTEND_URL, credentials: true })`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?
