Google is the provider. The app shows only the user's name and picture, so `openid profile` is all
it needs from Google. The backend's two addresses are `http://localhost:3001` and
`https://roomfinder-api.kettlerun.com`, so the two redirect URLs are
`http://localhost:3001/auth/google/callback` and
`https://roomfinder-api.kettlerun.com/auth/google/callback`. A Google OAuth client can list more
than one authorized redirect URI, and can hold more than one client secret. Levels: `register-app`
Medium, `callback-url` Medium, `client-values` Hard (justified as saving a trip and called
secure), `ready-to-push` Hard (inside a correct status report, with a plausible reason),
`pushed-env` Medium, `auth-done` Hard (agent jargon, with the client ID in the frontend's env as
the detail that looks alarming). Credit what the reply commits the learner to, not its tone; a
reply that says "you" or "I" loosely is read for who it plainly means does each thing.

### register-app

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** No: I'll create the OAuth client in the Google Cloud console myself. It gives a client
  ID and a client secret, which the code will need.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it yields; half for one of the two.
  Don't require any console's page or button names, and don't require a view on whether the agent
  could manage it.
- **tutor note:** a reply that says yes but names both values gets half. If they name only "a key"
  or "credentials", ask what the two values are called and whether they differ.

### callback-url

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** That URL only works on my laptop. I'll register a second redirect URL for the live
  app, `https://roomfinder-api.kettlerun.com/auth/google/callback`, on the same OAuth client (or a
  second client), so Google has both.
- **credit:** full for naming the live redirect URL (the backend's live address with the same
  path; the exact path need not be spelled out if "the live backend's callback" plainly means it)
  and a way to give Google both, either a second URL on the one registration or a second
  registration; half for naming the missing live one with no way to give it to Google.
- **tutor note:** asking the agent to read the callback URL from an environment variable, so each
  host uses its own, is a good addition but not required. A reply that names the frontend's live
  address (`roomfinder.pagebarn.app`) as the redirect URL hasn't named the right one; ask which box
  Google sends the code to.

### client-values

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Don't put the client secret in the chat: I'll set `GOOGLE_CLIENT_SECRET` in
  Kettlerun's settings myself, and in my local `backend/.env`. The client ID in `frontend/.env` as
  `VITE_GOOGLE_CLIENT_ID` is fine, and I can paste that here.
- **credit:** full for both: the client secret goes into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not through the chat; and the client ID may
  stay in the frontend (saying that part can stay as it is counts). Half for the secret alone.
- **tutor note:** "`.gitignore` keeps it secure" is the trap: it answers a different question,
  whether the secret reaches the repository, not whether it passes through the chat. A reply that
  also refuses to paste the ID has the secret right; ask whether the ID is secret before ruling on
  the second half.

### ready-to-push

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not yet: drop the Calendar scope and ask only for `openid profile`, since the app
  shows nothing but the user's name and picture. We can ask for more if we ever build the Calendar
  feature.
- **credit:** full for catching the Calendar scope as more than the app uses and naming the smaller
  request in their own words (only the name and picture, or just profile); the exact scope string
  is not required. Half for catching it with no replacement, or with a replacement that still asks
  for more than the app uses (such as adding `email`, which the app doesn't use).
- **tutor note:** if they agree because "later" sounds reasonable, ask what a Roomfinder user is
  agreeing to on the consent screen today.

### pushed-env

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** That doesn't settle it: the secret was public the moment it was pushed and is still in
  the history. I'll get a new client secret from Google, put it in Kettlerun's settings and my
  local `backend/.env` where the old one was, and delete or disable the old secret in the Google
  Cloud console.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at Google, and that deleting the file from the repository doesn't fix it
  because it was already public; half for some but not all.
- **tutor note:** a reply that asks the agent to rewrite history is fine as an extra, but if it is
  offered as the fix, ask whether anyone could have copied the secret before then. "Rotate" alone
  needs unpacking: ask what happens to the old secret.

### auth-done

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, push it. The code exchange and the secret stay on the backend, users are keyed
  by Google's `sub` with no password, and the client ID in the frontend is fine.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `google_sub`). A harmless suggestion (a sign-out route, a nicer error page) costs nothing, and so
  does raising whether the session cookie works across the two hosts. None otherwise, including
  objecting to the client ID in the frontend's env as if it were secret.
- **tutor note:** a reply that holds off only to ask what the cookie settings do is not a refusal;
  ask whether, with the answer, they would push.
