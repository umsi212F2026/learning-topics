Roomfinder lets students at a small college see which study rooms are free and book one for an
hour. Its React frontend is built to static files and served by Pagebarn, a static host, at
`https://roomfinder.pagebarn.app`. Its Express backend runs on Kettlerun, a server host, at
`https://roomfinder-api.kettlerun.com`, with a Postgres database. On your laptop the frontend runs
on `http://localhost:5173` and the backend on `http://localhost:3001`. Right now the whole app sits
behind one shared basic-auth password, and you and your coding agent are partway through replacing
it with sign-in through Google. Once someone is signed in, Roomfinder shows their name and Google
picture beside their bookings. It does not use their email.

Each question below is one message your agent sends you, at a different moment in the work. They
are independent: treat each one as if it were the only message you had seen. Write the reply you
would send, in two to four sentences, as you would type it to your agent: what you say yes or no
to, what you will do yourself, and what you want changed.

### register-app

> Next is the Google side. I can open the Google Cloud console in your browser, where you're
> already signed in to Google, and create the OAuth client for Roomfinder for you. OK? And once it
> exists, what comes out of it that the code will need?

Write the reply you would send.

### callback-url

> I've set the callback in `backend/auth.js` to `http://localhost:3001/auth/google/callback`, and
> the sign-in routes are wired up. When you register the OAuth client, enter that URL as the
> authorized redirect URI and we're good to go.

Write the reply you would send.

### client-values

> To save you a trip back and forth between dashboards, paste the client ID and client secret here
> once Google shows them. I'll put the ID in `frontend/.env` as `VITE_GOOGLE_CLIENT_ID` and set the
> secret on Kettlerun as `GOOGLE_CLIENT_SECRET` myself. Both `.env` files are already in
> `.gitignore`, so this keeps everything secure.

Write the reply you would send.

### ready-to-push

> Sign-in works on localhost and on the live app, and all 14 tests pass. I'm requesting
> `openid profile https://www.googleapis.com/auth/calendar` so Roomfinder can add bookings to
> people's Google Calendar later on; users only see the consent screen once. Ready to push?

Write the reply you would send.

### pushed-env

> Heads up: `backend/.env`, with `GOOGLE_CLIENT_SECRET` in it, went out in yesterday's commit,
> which is pushed to the public repository. I've deleted the file in a new commit, added `.env` to
> `.gitignore`, and pushed that. Anything else needed?

Write the reply you would send.

### auth-done

> Done: `passport-google-oauth20`, scope `['openid', 'profile']`. Callback exchanges the code
> server-side with `GOOGLE_CLIENT_ID`/`GOOGLE_CLIENT_SECRET` from the env you set on Kettlerun,
> gets `sub`, name and picture back, and `findOrCreate`s on `users` by `google_sub` (no password
> column). `express-session` cookie is `sameSite: 'none', secure: true` (Pagebarn and Kettlerun
> are different sites); CORS allows credentials from `https://roomfinder.pagebarn.app`. Frontend
> has `VITE_GOOGLE_CLIENT_ID` in its env for the button. OK to push?

Write the reply you would send.
