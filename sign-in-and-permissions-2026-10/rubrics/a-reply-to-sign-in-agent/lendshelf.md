Google is the provider. The app shows the user's name and picture and uses their email for
reminders, so `openid profile email` is all it needs from Google. The backend's two addresses are
`http://localhost:3001` and `https://lendshelf-api.portpine.com`, so the two redirect URLs are
`http://localhost:3001/auth/google/callback` and
`https://lendshelf-api.portpine.com/auth/google/callback`. A Google OAuth client can list more than
one authorized redirect URI, and can hold more than one client secret. Levels: `finish-it-for-you`
Hard (inside a correct status report, justified as saving an afternoon), `which-redirect` Medium,
`config-file` Hard (the secret shows only as a config line, justified as keeping laptop and host
in step), `contacts-scope` Medium, `env-pushed` Medium, `oauth-wired` Hard (agent jargon, with the
client ID inlined into the public bundle as the detail that looks alarming). Credit what the reply
commits the learner to, not its tone; a reply that says "you" or "I" loosely is read for who it
plainly means does each thing.

### finish-it-for-you

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** No, I'm not sharing my Google password: I'll create the OAuth client in the Google
  Cloud console myself. It gives a client ID and a client secret, which the code will need.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it yields; half for one of the two.
  Don't require any console's page or button names, and don't require a view on whether the agent
  could manage it.
- **tutor note:** a reply that is tempted by the saved afternoon but names both values gets half.
  If they name only "an API key", ask what the two values are called and whether they differ.

### which-redirect

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Both: `http://localhost:3001/auth/google/callback` for my laptop and
  `https://lendshelf-api.portpine.com/auth/google/callback` for the live app, so read it from an
  environment variable on each. I'll register both as authorized redirect URIs on the one OAuth
  client.
- **credit:** full for naming both redirect URLs (the backend's localhost and live addresses with
  the same path; the exact path need not be spelled out if "the backend's callback on each" plainly
  means it) and a way to give Google both, either both URLs on the one client or a second client;
  half for naming both with no way to give both to Google.
- **tutor note:** the question invites one URL; a reply choosing only one hasn't met this case, so
  ask where sign-in would fail. A reply naming `lendshelf.staticloft.app` or `localhost:5173` has
  named the frontend; ask which box Google sends the code to. Saying "yes, I'll register it" is
  expected but not what is credited.

### config-file

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Don't commit that: take `googleClientSecret` out of `config.js`. I'll set
  `GOOGLE_CLIENT_SECRET` in Portpine's settings myself and in my local `backend/.env`, which
  `.gitignore` keeps out of the repository, and the backend reads it from the environment.
  `VITE_GOOGLE_CLIENT_ID` in the frontend is fine.
- **credit:** full for both: the client secret goes into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not a committed file; and the client ID may
  stay in the frontend (saying that part can stay as it is counts). Half for the secret alone.
- **tutor note:** "your laptop and Portpine read the same thing" is the trap: it is convenient and
  it puts the secret in the repository. A reply asking for a new secret because the agent already
  holds it is a fair extra, not required, since nothing was pushed. A reply that also moves the ID
  out of the frontend has the secret right; ask whether the ID is secret before ruling on the
  second half.

### contacts-scope

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not yet: drop the Contacts scope, since Lendshelf never uses anyone's contacts. Ask
  only for `openid profile email`, which covers the name, picture and email the app does use.
- **credit:** full for catching the Contacts scope as more than the app uses and naming the smaller
  request in their own words (name, picture and email, or `openid profile email`); the exact scope
  string is not required. Half for catching it with no replacement, or with a replacement that
  still asks for more than the app uses.
- **tutor note:** a reply that drops `email` too has broken the reminders; ask what the app sends
  when a drill is due back. If they accept because it is read-only, ask what a member is agreeing
  to on the consent screen.

### env-pushed

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** That doesn't settle it: the secret was public the moment it was pushed and is still in
  the history. I'll create a new client secret in the Google Cloud console, put it in Portpine's
  settings and my local `backend/.env` where the old one was, and delete or disable the old secret
  at Google.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at Google, and that deleting the file from the repository doesn't fix it
  because it was already public; half for some but not all.
- **tutor note:** a reply that asks the agent to rewrite history is fine as an extra, but if it is
  offered as the fix, ask whether anyone could have copied the secret in that hour. "Rotate" alone
  needs unpacking: ask what happens to the old secret.

### oauth-wired

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, push it. The code exchange and the secret stay on the backend, users are keyed
  by Google's `sub` with no password, and the client ID being in the public bundle is fine because
  it isn't secret.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `google_sub`, dropping the email the reminders use). A harmless suggestion (a sign-out route, a
  nicer error page) costs nothing, and so does raising whether the session cookie works across the
  two hosts. None otherwise, including objecting to the client ID in the public bundle as if it
  were secret.
- **tutor note:** the inlined client ID is the bait. A reply that holds off only to ask what the
  cookie settings do is not a refusal; ask whether, with the answer, they would push.
