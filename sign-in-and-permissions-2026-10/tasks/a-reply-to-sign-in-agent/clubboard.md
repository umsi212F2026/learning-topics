Clubboard is an events board for a student hiking club: members see upcoming hikes, sign up for
one, and get an email reminder the day before. Its React frontend is built to static files and
served by Sitecrate, a static host, at `https://clubboard.sitecrate.app`. Its Express backend runs
on Hullworks, a server host, at `https://clubboard-api.hullworks.com`, with a Postgres database. On
your laptop the frontend runs on `http://localhost:5173` and the backend on
`http://localhost:3001`. Right now the whole app sits behind one shared basic-auth password, and
you and your coding agent are partway through replacing it with sign-in through GitHub. Once
someone is signed in, Clubboard shows their GitHub name and profile picture beside the hikes they
signed up for, and it uses their email address to send the reminders.

Each question below is one message your agent sends you, at a different moment in the work. They
are independent: treat each one as if it were the only message you had seen. Write the reply you
would send, in two to four sentences, as you would type it to your agent: what you say yes or no
to, what you will do yourself, and what you want changed.

### github-password

> To set up the GitHub side I need to be signed in to GitHub as you. Can you send me your GitHub
> username and password? I'll create the OAuth app under Developer settings and won't keep the
> password afterwards. And once it exists, what comes out of it that the code will need?

Write the reply you would send.

### callback-set

> Sign-in routes are in `backend/routes/auth.js` and the tests pass. I've set the callback to
> `https://clubboard-api.hullworks.com/auth/github/callback` so it matches production exactly,
> which is what GitHub checks against. When you register the OAuth app, enter that as the
> callback URL and the config side is done.

Write the reply you would send.

### frontend-env

> I've copied the client ID and client secret from `backend/.env`, where you put them, into
> `frontend/.env` as `VITE_GITHUB_CLIENT_ID` and `VITE_GITHUB_CLIENT_SECRET`. The Sign in button
> now sends both to GitHub and gets the user back directly, so the backend has less to do. OK to
> push?

Write the reply you would send.

### reminders-working

> Sign-in works on localhost and on Hullworks, avatars show up, and the reminder emails go out. I'm
> requesting the `user` scope (read and write access to profile info, including email), since that
> one scope covers both the profile and the email addresses we need, which is simpler than juggling
> two. Push?

Write the reply you would send.

### history-cleaned

> Heads up: `backend/.env`, with `GITHUB_CLIENT_SECRET` in it, was in Monday's push to the public
> repository. I've handled it: removed the file, added `.env` to `.gitignore`, rewritten the history
> with `git filter-repo` and force-pushed, so the secret no longer appears in any commit. We're
> secure now. Anything else?

Write the reply you would send.

### built-and-ready

> Here's what's built. The Sign in button sends the browser to GitHub, asking for `user:email`.
> GitHub sends it back to `/auth/github/callback` on the backend with a code. The backend sends the
> code, with the client ID and client secret from the environment you set on Hullworks, to GitHub,
> gets an access token, and asks GitHub's API who the user is. It finds or creates a `users` row by
> `github_id`, with name, avatar and email and no password, and starts a session cookie
> (`sameSite: 'none'`, `secure: true`, CORS allowing credentials from the Sitecrate address). OK to push?

Write the reply you would send.
