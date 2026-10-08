Lendshelf is a tool-lending library for a student housing co-op: members borrow a drill or a
ladder for a few days, and get an email when it is due back. Its React frontend is built to static
files and served by Staticloft, a static host, at `https://lendshelf.staticloft.app`. Its Express
backend runs on Portpine, a server host, at `https://lendshelf-api.portpine.com`, with a Postgres
database. On your laptop the frontend runs on `http://localhost:5173` and the backend on
`http://localhost:3001`. Right now the whole app sits behind one shared basic-auth password, and
you and your coding agent are partway through replacing it with sign-in through Google. Once
someone is signed in, Lendshelf shows their name and Google picture beside what they have
borrowed, and it uses their email address to send the due-date reminders.

Each question below is one message your agent sends you, at a different moment in the work. They
are independent: treat each one as if it were the only message you had seen. Write the reply you
would send, in two to four sentences, as you would type it to your agent: what you say yes or no
to, what you will do yourself, and what you want changed.

### finish-it-for-you

> The sign-in routes and the Sign in button are done, and the tests pass. All that's left is the
> Google side: if you share your Google password, I'll sign in to the Google Cloud console, set up
> the consent screen and the OAuth client, and have it all finished before you're back, so you
> don't lose an afternoon in settings pages. And once it exists, what comes out of it that the
> code will need?

Write the reply you would send.

### which-redirect

> Which redirect URL do you want me to set in the code, and will you register it?

Write the reply you would send.

### config-file

> Moved the Google settings into one file so your laptop and Portpine read the same thing:
>
> ```js
> // backend/config.js
> module.exports = {
>   googleClientId: '4471-lendshelf.apps.googleusercontent.com',
>   googleClientSecret: 'GOCSPX-8kq...',
>   callbackPath: '/auth/google/callback',
> };
> ```
>
> plus `VITE_GOOGLE_CLIENT_ID` in `frontend/.env` for the button. No env setup on Portpine now. OK
> to commit and push?

Write the reply you would send.

### contacts-scope

> Sign-in works. I've set the scope to `openid profile email` plus
> `https://www.googleapis.com/auth/contacts.readonly`, which lets the app read each user's Google
> contacts. OK to push?

Write the reply you would send.

### env-pushed

> I need to flag something: the commit I pushed an hour ago included `backend/.env`, with
> `GOOGLE_CLIENT_SECRET` in it, and the repository is public. I've deleted the file in a new
> commit, added `.env` to `.gitignore`, and pushed that. Anything else needed?

Write the reply you would send.

### oauth-wired

> Done: `passport-google-oauth20` with `['openid', 'profile', 'email']`, `/auth/google/callback`
> exchanges the code server-side using `GOOGLE_CLIENT_ID`/`GOOGLE_CLIENT_SECRET` from the env you
> set on Portpine, then `findOrCreate` on `users` by `google_sub` (name, picture, email; no
> password column). `express-session`, `sameSite: 'none', secure: true`, CORS with credentials for
> Staticloft. Note `VITE_GOOGLE_CLIENT_ID` gets inlined into the public JS bundle. OK to push?

Write the reply you would send.
