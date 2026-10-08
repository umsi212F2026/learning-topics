Huddle is your Problem Set 3 app: an events board where the clubs on campus post their meetings
and members RSVP to them. Its React frontend is built to static files on Brightdock, a static host,
at `https://huddle.brightdock.app`. Its Express backend runs on Kettleworks, a server host, at
`https://huddle-api.kettleworks.com`, with a Postgres database. On your laptop the frontend runs on
`http://localhost:5173` and the backend on `http://localhost:3001`.

Right now the whole app sits behind one shared basic-auth password. You and your coding agent are
replacing that with sign-in through Google. Once someone signs in, Huddle shows their Google name
and profile picture beside the events they post and the ones they RSVP to. It doesn't use their
email.

Each question below is a separate excerpt from your agent's plan. They are independent: treat each
one as if it were the only part of the plan you had seen. Answer each in two to four sentences.

### register

1. Install `passport` and `passport-google-oauth20` in `backend/`.
2. To save you a trip through the Google Cloud console, which has a lot of screens, send me the
   email address and password of your Google account. I'll sign in, create the OAuth client for
   Huddle, fill in the consent screen, and copy what the code needs from it into the config.
3. In `backend/routes/auth.js`, add `GET /auth/google`, which sends the browser to Google, and
   `GET /auth/google/callback`, which Google sends it back to.
4. Add a "Sign in with Google" button to `frontend/src/components/NavBar.jsx` that links to the
   backend's `/auth/google`.
5. Once sign-in works, remove the basic-auth middleware from `backend/server.js`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### redirect

1. You create an OAuth client in the Google Cloud console, of type Web application, named Huddle.
2. Under the client's Authorized redirect URIs, you add
   `https://huddle-api.kettleworks.com/auth/google/callback`. That is where Google sends users back
   after they sign in.
3. In `backend/routes/auth.js`, add `GET /auth/google`, which sends the browser to Google, and
   `GET /auth/google/callback`, which receives the code Google sends back.
4. In `backend/auth.js`, set `callbackURL` to
   `https://huddle-api.kettleworks.com/auth/google/callback` to match.
5. Add a "Sign in with Google" button to `frontend/src/components/NavBar.jsx` that links to
   `${import.meta.env.VITE_API_URL}/auth/google`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### paste-values

Once you've created the OAuth client in the Google Cloud console:

1. Paste the client ID and the client secret here in the chat.
2. I'll put the client ID in `frontend/.env` as `VITE_GOOGLE_CLIENT_ID`, so the Sign in button can
   send the browser to Google's sign-in page.
3. I'll set `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` in Kettleworks's settings for the
   backend with its command-line tool, and add both to `backend/.env` for your laptop.
4. In `backend/auth.js`, read both values from `process.env` for the exchange with Google.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### calendar

1. Install `passport` and `passport-google-oauth20` in `backend/`.
2. In `backend/auth.js`, set up the Google strategy:

   ```js
   passport.use(new GoogleStrategy({
     clientID: process.env.GOOGLE_CLIENT_ID,
     clientSecret: process.env.GOOGLE_CLIENT_SECRET,
     callbackURL: process.env.GOOGLE_CALLBACK_URL,
     scope: [
       'openid',
       'profile',
       'https://www.googleapis.com/auth/calendar.events', // so RSVPs can go straight into members' calendars later
     ],
   }, verify));
   ```

3. In `verify`, take the user's Google id, name and picture from the profile Google returns.
4. Add `GET /auth/google` and `GET /auth/google/callback` in `backend/routes/auth.js`.
5. Add a "Sign in with Google" button to `frontend/src/components/NavBar.jsx`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?

### untracked

You notice that `backend/.env`, holding `GOOGLE_CLIENT_SECRET`, went out in a commit you pushed to
Huddle's public repository on GitHub. Your agent proposes this fix:

1. Run `git rm --cached backend/.env`, so git stops tracking the file but your copy stays on your
   laptop.
2. Add `.env` to `backend/.gitignore`, so it can't be committed again.
3. Commit both changes and push to the public repository.
4. Check on GitHub that `backend/.env` no longer appears in the repository's file list.

What do you do now, and does your agent's fix settle it?

### id-token

1. The "Sign in with Google" button sends the browser to the backend's `/auth/google`, which sends
   it on to Google, where the user approves Huddle.
2. Google sends the browser back to the backend's callback URL with a code.
3. The backend sends that code, with the client ID and client secret from its environment, to
   Google, and gets back an ID token naming the user: their Google id (`sub`), name and picture.
4. It finds or creates a row in a `users` table keyed by `google_sub`, holding their name and
   picture. The table has no password column.
5. It starts a session and sends the browser a cookie. Brightdock and Kettleworks are different
   sites, so the cookie is set with `sameSite: 'none'` and `secure: true`, and CORS on the backend
   allows credentials from `https://huddle.brightdock.app`.

Would you agree to this as it stands? If not, what would you change, and who does it, you or your
agent?
