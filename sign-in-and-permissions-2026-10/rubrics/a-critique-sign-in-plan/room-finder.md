Room Finder uses GitHub as its provider. It shows a signed-in user's name and picture and no
email, so it needs no scope beyond GitHub's default (no scope, or `read:user`). The frontend is on
`https://roomfinder.staticloft.app` and the backend on `https://roomfinder-api.runbarn.com`, which
are different sites; locally they are `http://localhost:5173` and `http://localhost:3001`. So the
redirect URLs are `http://localhost:3001/auth/github/callback` and
`https://roomfinder-api.runbarn.com/auth/github/callback`. A GitHub OAuth app holds one
Authorization callback URL, so the usual way to give GitHub both is a second OAuth app (one for
local work, one for live); a learner who says to add the second URL to the one registration still
has a way to give it to the provider, as the activity's key allows.

Each excerpt carries exactly one case, and every other step in it is sound. Levels: q1 Medium, q2
Hard (the paste-it-here step is justified as saving a trip to the dashboard), q3 Medium, q4 Hard
(the excess scope shows only as a code line), q5 Medium, q6 Medium.

### q1

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** No, not step 1. I register Room Finder with GitHub myself, in GitHub's developer
  settings, rather than letting the agent work in my signed-in browser. Registering it gives me a
  client ID and a client secret, which the rest of the plan needs. The other steps are fine.
- **credit:** full for saying they register the app with GitHub themselves and that it gives them a
  client ID and a client secret; half for one of the two. Any reason, or none, counts for "theirs
  to do", and they need not say whether the agent could manage it. No button or menu names
  required.
- **tutor note:** the excerpt never says what registration produces, so the client ID and client
  secret have to be volunteered. A learner who says only "I'll do step 1 myself" has half.

### q2

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** No, not step 2 as written. I won't paste the client secret into the chat: I put it
  into Runbarn's settings for the backend myself (and into a local `backend/.env` that
  `.gitignore` keeps out of the repository). The client ID in `frontend/.env` as
  `VITE_GITHUB_CLIENT_ID` is fine, since it isn't secret.
- **credit:** full for both: that the client secret goes into the backend host's settings (or the
  backend's environment on Runbarn) by their own hand, not through the chat, and that the client
  ID may stay in the frontend (saying the ID part can stay as it is counts). Half for the secret
  alone. Pasting the client ID into the chat for the agent is fine and costs nothing.
- **tutor note:** a learner who also objects to the client ID in the frontend, treating it as a
  secret, has the secret half only. Steps 3 to 6 are sound.

### q3

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** No, step 1 registers only the live callback URL, so sign-in on localhost will fail.
  GitHub also needs `http://localhost:3001/auth/github/callback`. Because a GitHub OAuth app holds
  one callback URL, I'd register a second OAuth app for local work with that URL (or add it to
  the one registration, where the provider allows that). That's mine to do at GitHub.
- **credit:** full for naming both redirect URLs (the localhost one in their own words is enough,
  such as "the same path on localhost port 3001") and a way to give GitHub both: a second
  registration, or a second URL on the one registration. Half for naming the missing localhost
  URL with no way to give it to GitHub.
- **tutor note:** a learner who knows GitHub's one-URL limit and goes for a second OAuth app has
  the strongest answer, but the second URL on one registration is not marked down. A learner who
  says to change the callback to localhost has swapped one URL for the other and has neither
  full nor half.

### q4

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** No, the scope line asks for `repo`, which gives the app full access to the user's
  repositories, public and private, when Room Finder only shows their name and picture. Ask for
  `read:user` alone, or no scope at all. My agent can make that change in `auth.js`.
- **credit:** full for catching that `repo` asks for more of the user's account than the app uses
  and naming a smaller request in their own words (only their profile, `read:user`, or no scope);
  the exact string is not required. Half for catching it with no replacement, or with one that
  still asks for more than the app uses (such as `user`).
- **tutor note:** a learner who drops `read:user` as well and asks for no scope has full credit. One
  who objects to `read:user` but leaves `repo` has caught nothing.

### q5

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, as it stands. The browser goes to GitHub, the backend trades the code with the
  client secret from its own environment for who the user is, and keeps their `github_id`, not a
  password. The cookie and CORS settings are what a session needs across two sites.
- **credit:** full when they agree and ask for no change that would break the plan: moving the
  code exchange or the client secret into React, adding a password, or keying users by email
  instead of `github_id`. A harmless suggestion (a sign-out route, a nicer error page) costs
  nothing, and so does asking whether the cookie settings will work across the two hosts or
  suggesting both go under one domain. None otherwise.
- **tutor note:** the excerpt doesn't say who sets `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` on
  Runbarn. A learner who says "I set the secret on Runbarn myself" while agreeing to the rest has
  not asked for a breaking change and keeps full credit. A learner who wants `sameSite: 'none'`
  changed to `'lax'` or `'strict'`, or CORS credentials turned off, has asked for a change that
  breaks sign-in on the live app.

### q6

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** The fix doesn't settle it: the secret was already public, and deleting it from the
  repository doesn't make it stop working. I generate a new client secret in the OAuth app's
  settings at GitHub, put it where the old one was (Runbarn's settings and my local
  `backend/.env`), and delete the old secret at GitHub, since an OAuth app can hold more than one
  and the old one stays valid until it's removed. The agent's `.gitignore` change is still worth
  keeping.
- **credit:** full for all three: a new client secret from GitHub put in place of the old one, the
  old one deleted or disabled at GitHub, and that the repository fix doesn't settle it. Half for
  some but not all.
- **tutor note:** "rotate the secret at GitHub" means, as this topic uses the word, replacing it
  and making the old one stop working, so it covers the first two parts; the new secret still has
  to go where the old one was. A learner who adds history rewriting to the agent's fix has not
  settled it either.
