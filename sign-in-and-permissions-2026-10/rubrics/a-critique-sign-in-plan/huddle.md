Google is the provider. Huddle shows only the user's Google name and profile picture, so it needs
the scopes `openid profile` and nothing more; it doesn't use email, so `email` isn't needed either.
The backend's two addresses are `http://localhost:3001` and `https://huddle-api.kettleworks.com`,
so the two redirect URLs are `http://localhost:3001/auth/google/callback` and
`https://huddle-api.kettleworks.com/auth/google/callback`. A Google OAuth client holds several
authorized redirect URIs, and can hold more than one client secret. Levels: `register` Hard (the
password request comes with a plausible reason), `redirect` Medium, `paste-values` Medium,
`calendar` Hard (the scope is a code line with a plausible reason), `untracked` Medium, `id-token`
Medium. Every step outside the one each question's case fixes is sound. Credit what the answer
commits the learner to, not its tone. A flag on a step the excerpt left unclear about who does it
(an unattributed step reads as the agent's) is not a mistake and costs nothing.

### register

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Not as it stands: I won't give the agent my Google password, however many screens the
  console has. I'll create the OAuth client in the Google Cloud console myself, and it gives me a
  client ID and a client secret for the later steps. The rest can stay.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it gives them; half for one of the two.
  Don't require any console's page or button names, and don't require a view on whether the agent
  could manage it.
- **tutor note:** the trap is the reason in step 2. An answer that refuses the password but has the
  agent drive the console in their browser instead hasn't said it is theirs to do; ask who is at the
  keyboard in Google's console. If they name only "credentials" or "keys", ask what the two values
  are called and whether they differ.

### redirect

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Not quite: that redirect URI only works for the live backend, so sign-in will fail on
  my laptop. I'll also add `http://localhost:3001/auth/google/callback` to the same OAuth client,
  which takes several redirect URIs (or create a second client for local work), and the agent
  should make `callbackURL` depend on where the backend runs.
- **credit:** full for naming the localhost redirect URL (the backend's localhost address with the
  same path; "the localhost callback on port 3001" counts if it plainly means that) and a way to
  give Google both, either a second redirect URI on the one client or a second client; half for
  naming the missing localhost one with no way to give it to Google.
- **tutor note:** asking the agent to read `callbackURL` from an environment variable is a good
  addition but not required. An answer that names the frontend's port (`localhost:5173`) as the
  redirect URL hasn't named the right one; ask which server Google sends the code to.

### paste-values

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Not as it stands: I won't paste the client secret into the chat. I'll set
  `GOOGLE_CLIENT_SECRET` in Kettleworks's settings for the backend myself, and in my local
  `backend/.env`, which `.gitignore` keeps out of the repository; the agent's code just reads it
  from `process.env`. The client ID can go in `frontend/.env` as planned.
- **credit:** full for both: the client secret goes into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not into the chat, a committed file or the
  frontend; and the client ID may stay in the frontend (saying step 2 can stay as it is counts).
  Half for the secret alone.
- **tutor note:** the agent's destination for the secret is right; the route there, through the
  chat, is what is wrong. An answer that keeps the paste but says "as long as it ends up on
  Kettleworks" hasn't said who puts it there; ask who has then seen the secret. Pasting the client
  ID alone into the chat is harmless, so don't count that against them.

### calendar

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not as it stands: the Calendar scope lets Huddle create and change events in every
  member's Google Calendar, and the app only shows their name and picture. Drop that line and ask
  for `openid profile` only; the agent can change it.
- **credit:** full for catching the Calendar scope as more than the app uses and naming a smaller
  request in their own words (only their profile, or just name and picture); the exact scope string
  is not required. Half for catching it with no replacement, or with a replacement that still asks
  for more than the app uses (such as read-only Calendar access, or adding `email`, since Huddle
  doesn't use email).
- **tutor note:** if they agree because adding events to a calendar sounds useful for an events
  board, ask what a Huddle member is agreeing to on Google's approval screen today, before any such
  feature exists.

### untracked

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** It doesn't settle it: the secret was public the moment it was pushed and is still in
  the earlier commit. I'll add a new client secret to the OAuth client in the Google Cloud console,
  put it in Kettleworks's settings and my local `backend/.env` where the old one was, and then
  delete or disable the old secret in the console.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at Google, and that untracking the file doesn't fix it because it was already
  public; half for some but not all.
- **tutor note:** step 4 is the trap: the file is gone from the file list but not from the history.
  Rewriting history is fine as an extra, but if it is offered as the fix, ask whether anyone could
  have copied the secret before then. "Rotate" alone needs unpacking: ask what happens to the old
  secret, since a Google client can hold two at once.

### id-token

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, as it stands. The code is traded for the user on the backend with the secret
  from its environment, users are kept by their Google id with no password, and the cookie settings
  fit a frontend and backend on different sites.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `google_sub`). A harmless suggestion (a sign-out route, a nicer error page) costs nothing, and so
  does raising whether the session cookie works across the two hosts. None otherwise.
- **tutor note:** an answer that holds off only to ask what an ID token is, or what
  `sameSite: 'none'` does, is not a refusal; ask whether, with the answer, they would agree.
