Room Finder is a study-room finder for one campus library: students post which group-study rooms
are free and claim one for an hour. Its React frontend is built to static files on Staticloft, at
`https://roomfinder.staticloft.app`. Its Express backend runs on Runbarn, at
`https://roomfinder-api.runbarn.com`, and its data is in a Postgres database. On your laptop the
frontend runs at `http://localhost:5173` and the backend at `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You are replacing that with
sign-in through GitHub. Once someone signs in, Room Finder shows their name and their GitHub
picture. It doesn't use their email.

Each question below is a separate excerpt from your coding agent's plan for adding sign-in. The
excerpts are independent: nothing in one carries over to another. Answer each in two to four
sentences.

### q1

Your agent's plan:

1. I'll open GitHub's developer settings in your browser, where you're already signed in, and
   create an OAuth app for Room Finder.
2. In `backend/src/auth.js`, I'll add `GET /auth/github`, which sends the browser to GitHub to
   sign in.
3. I'll add `GET /auth/github/callback`, where GitHub sends the browser back with a code. The
   backend trades that code with GitHub for the user's GitHub profile.
4. I'll add a `users` table keyed by `github_id`, with the user's name and avatar URL, and create
   a row the first time someone signs in.
5. I'll replace the basic-auth middleware with a check for a signed-in session, and add
   `GET /api/me`, which returns the signed-in user.
6. In React, I'll swap the password prompt for a "Sign in with GitHub" button and show the user's
   name and picture in the header.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### q2

Your agent's plan:

1. Once you've created the OAuth app in GitHub's developer settings, GitHub shows you a client ID
   and a client secret.
2. To save you a trip to the Runbarn dashboard, paste both here and I'll set everything up: the
   client ID goes in `frontend/.env` as `VITE_GITHUB_CLIENT_ID`, and I'll set `GITHUB_CLIENT_ID`
   and `GITHUB_CLIENT_SECRET` on the backend with Runbarn's command-line tool.
3. The "Sign in with GitHub" button in React builds GitHub's sign-in URL from
   `VITE_GITHUB_CLIENT_ID` and sends the browser there.
4. GitHub sends the browser back to the backend's `/auth/github/callback` route with a code.
5. The backend sends that code to GitHub, with the client ID and client secret from its
   environment, and gets back who the user is.
6. It finds or creates the user's row in `users` by their `github_id` and starts a session.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### q3

Your agent's plan:

1. You create an OAuth app in GitHub's developer settings (Settings, Developer settings, OAuth
   Apps, New OAuth App), with Homepage URL `https://roomfinder.staticloft.app` and Authorization
   callback URL `https://roomfinder-api.runbarn.com/auth/github/callback`.
2. You put the client ID and client secret it gives you into Runbarn's settings for the backend,
   as `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET`, and into `backend/.env` for local work.
   `.gitignore` already keeps `backend/.env` out of the repository.
3. I'll add `GET /auth/github` and `GET /auth/github/callback` to the backend. The callback trades
   GitHub's code, with the client ID and secret, for the user's name and picture.
4. I'll add a `users` table keyed by `github_id`, with no password column.
5. We'll try it on localhost first, then on the live app.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### q4

Your agent's plan:

1. Install `passport` and `passport-github2` in `backend/`.
2. Configure the strategy in `backend/src/auth.js`:

   ```js
   passport.use(new GitHubStrategy({
     clientID: process.env.GITHUB_CLIENT_ID,
     clientSecret: process.env.GITHUB_CLIENT_SECRET,
     callbackURL: process.env.GITHUB_CALLBACK_URL,
     scope: ['read:user', 'repo'],
   }, findOrCreateUser));
   ```

3. `GITHUB_CALLBACK_URL` is the localhost callback in `backend/.env` and the live one in Runbarn's
   settings, beside the client ID and client secret you set there.
4. `findOrCreateUser` looks up `users` by `github_id` and, on a first sign-in, inserts a row with
   `name` and `avatar_url`.
5. Routes: `GET /auth/github` starts sign-in; `GET /auth/github/callback` finishes it and redirects
   to the frontend.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### q5

Your agent's plan:

1. The "Sign in with GitHub" button sends the browser to the backend's `/auth/github`, which
   redirects it to GitHub's sign-in page with the client ID and the callback URL, and no scope:
   Room Finder needs only the user's name and picture, which every GitHub profile shows publicly.
2. After the user approves, GitHub sends the browser back to `/auth/github/callback` with a code.
3. The backend sends that code, with `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` from its
   environment, to GitHub and gets an access token. It uses the token to ask GitHub's API
   (`GET https://api.github.com/user`) who the user is.
4. A migration adds a `users` table: `id`, `github_id` (unique), `name`, `avatar_url`,
   `created_at`, and no password column. The callback finds the row by `github_id`, or creates it.
5. The backend starts a session with `express-session`. The frontend and the backend are on
   different sites, so the session cookie is set with `sameSite: 'none'`, `secure: true` and
   `httpOnly: true`, CORS allows credentials from `https://roomfinder.staticloft.app` (and
   `http://localhost:5173` locally), and React's requests use `credentials: 'include'`.
6. The basic-auth middleware goes, replaced by a check for a session on every `/api` route, and
   `GET /api/me` returns the signed-in user's name and picture, or 401.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### q6

A week after launch you notice that `backend/.env`, holding the client secret, was in a commit you
pushed to Room Finder's public repository on GitHub. Your agent proposes this fix:

1. Run `git rm --cached backend/.env` and commit with the message "Remove .env".
2. Add `backend/.env` to `.gitignore` and commit that.
3. Push both commits.

What do you do now, and does your agent's fix settle it?
