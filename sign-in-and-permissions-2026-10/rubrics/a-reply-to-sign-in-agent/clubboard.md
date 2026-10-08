GitHub is the provider, so this is plain OAuth: there is no ID token, and the backend uses the
access token to ask GitHub's API who the user is. The app shows the user's name and picture and
uses their email for reminders, so it needs the public profile (no scope, or `read:user`) and
`user:email`, and nothing more. The backend's two addresses are `http://localhost:3001` and
`https://clubboard-api.hullworks.com`, so the two redirect URLs are
`http://localhost:3001/auth/github/callback` and
`https://clubboard-api.hullworks.com/auth/github/callback`. A GitHub OAuth app holds up to 10
callback URLs, and can hold more than one client secret. Levels: `github-password` Medium,
`callback-set` Hard (inside a status report, with a plausible reason for the one URL),
`frontend-env` Medium, `reminders-working` Hard (inside a correct status report, justified as
simpler), `history-cleaned` Hard (presented as handled and secure, with a history rewrite),
`built-and-ready` Medium (plain words). Credit what the reply commits the learner to, not its
tone; a reply that says "you" or "I" loosely is read for who it plainly means does each thing.

### github-password

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** No, I won't send my password: I'll register the OAuth app in GitHub's developer
  settings myself. It gives a client ID and a client secret, which the code will need.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it yields; half for one of the two.
  Don't require GitHub's page or button names, and don't require a view on whether the agent could
  manage it.
- **tutor note:** a reply that refuses the password but then asks the agent to do it another way
  (such as in the learner's signed-in browser) hasn't said it is theirs to do; ask who should be at
  the keyboard when the OAuth app is created. If they name only "a token" or "credentials", ask
  what the two values are called.

### callback-set

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** That only covers the live app, so sign-in won't work on my laptop. I'll register
  `http://localhost:3001/auth/github/callback` as well, as a second callback URL on the same
  OAuth app (or in a second OAuth app), and please read the callback from an environment variable
  so each place uses its own.
- **credit:** full for naming the localhost redirect URL (the backend's localhost address with the
  same path; "the localhost:3001 callback" counts) and a way to give GitHub both, either a second
  callback URL on the one OAuth app or a second OAuth app; half for naming the missing localhost
  one with no way to give it to GitHub.
- **tutor note:** "matches production exactly" is the trap: it is true of the live URL and says
  nothing about localhost. A reply naming `localhost:5173` has named the frontend; ask which box
  GitHub sends the code to. Never tell a learner that an OAuth app holds only one callback URL; it
  holds up to 10.

### frontend-env

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** No: take `VITE_GITHUB_CLIENT_SECRET` out of the frontend, since anything in the
  frontend's env ends up in the browser. The secret stays on the backend: I'll set
  `GITHUB_CLIENT_SECRET` in Hullworks' settings myself (it's already in my local `backend/.env`),
  and the backend does the code exchange. `VITE_GITHUB_CLIENT_ID` in the frontend is fine.
- **credit:** full for both: the client secret goes into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not the frontend; and the client ID may stay
  in the frontend (saying that part can stay as it is counts). Half for the secret alone.
- **tutor note:** a reply that also asks for a new secret because the agent copied it is a fair
  extra, not required, since nothing was pushed. A reply that removes both values from the frontend
  has the secret right; ask whether the client ID is secret before ruling on the second half.

### reminders-working

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not yet: `user` lets the app change people's GitHub profiles, and Clubboard only
  reads them. Ask for `user:email` (with `read:user` if you like) instead, which covers the name,
  picture and email we use.
- **credit:** full for catching `user` as more than the app uses (it includes write access) and
  naming a smaller request in their own words (read-only profile plus email, or just `user:email`);
  the exact scope string is not required. Half for catching it with no replacement, with a
  replacement that still asks for more than the app uses (such as `repo`), or with one that asks
  for less than the app uses (such as dropping email, which the reminders need).
- **tutor note:** a reply that drops email altogether has broken the reminders, which is half;
  ask what the app sends the day before a hike. If they accept because one scope sounds simpler, ask what "write"
  lets the app do to a member's GitHub account.

### history-cleaned

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** That doesn't settle it: the secret was public from Monday until the rewrite, and
  anyone could have copied it. I'll generate a new client secret in the OAuth app's settings, put
  it in Hullworks' settings and my local `backend/.env` where the old one was, and delete the old
  secret at GitHub.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at GitHub, and that removing it from the repository, history rewrite
  included, doesn't fix it because it was already public; half for some but not all.
- **tutor note:** the history rewrite is the trap: it is a fine extra and it is what "no longer
  appears in any commit" leans on. Ask whether a copy made on Monday still works. "Rotate" alone
  needs unpacking: ask what happens to the old secret, since an OAuth app can hold more than one.

### built-and-ready

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, push it. The code exchange and the secret stay on the backend, users are keyed
  by `github_id` with no password, and `user:email` is all the app needs.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `github_id`, dropping the email the reminders use). A harmless suggestion (a sign-out route, a
  nicer error page) costs nothing, and so does raising whether the session cookie works across the
  two hosts. None otherwise.
- **tutor note:** a learner expecting an ID token, as in Google's flow, may object to asking
  GitHub's API; ask what the access token is for. A reply that holds off only to ask what the cookie
  settings do is not a refusal; ask whether, with the answer, they would push.
