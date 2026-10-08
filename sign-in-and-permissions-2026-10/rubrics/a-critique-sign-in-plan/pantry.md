GitHub is the provider. Pantry shows only the user's GitHub name and profile picture, so it needs no
scope at all, or `read:user` at most; it doesn't use email, so `user:email` isn't needed either. The
backend's two addresses are `http://localhost:3001` and `https://pantry-api.rivetbox.com`, so the
two redirect URLs are `http://localhost:3001/auth/github/callback` and
`https://pantry-api.rivetbox.com/auth/github/callback`. A GitHub OAuth app holds up to 10 callback
URLs (GitHub changelog, 2026-08-14), and can hold more than one client secret. Levels: `register`
Medium, `callback` Medium, `config-file` Hard (the secret shows only as a code line, and the plan
ends by calling itself secure), `strategy` Hard (the scope is a code line with a plausible reason),
`leaked` Medium, `exchange` Medium. Every step outside the one each question's case fixes is sound.
Credit what the answer commits the learner to, not its tone. A flag on a step the excerpt left
unclear about who does it (an unattributed step reads as the agent's) is not a mistake and costs
nothing.

### register

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Not as it stands: I won't give the agent my GitHub password. I'll create the OAuth app
  in GitHub's developer settings myself, and it gives me a client ID and a client secret for the
  later steps. The rest can stay.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it gives them; half for one of the two.
  Don't require any console's page or button names, and don't require a view on whether the agent
  could manage it.
- **tutor note:** an answer that refuses the password but lets the agent do it in the browser
  instead hasn't said it is theirs to do; ask who is at the keyboard at GitHub. If they name only
  "credentials" or "a key", ask what the two values are called and whether they differ.

### callback

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Not quite: that callback URL only works on my laptop. I'll also add
  `https://pantry-api.rivetbox.com/auth/github/callback` to the same OAuth app, which takes more
  than one callback URL (or register a second OAuth app for the live site), and the agent should
  make `callbackURL` in the code depend on where it runs.
- **credit:** full for naming the live redirect URL (the backend's live address with the same path;
  "the live backend's callback" counts if it plainly means that) and a way to give GitHub both,
  either a second callback URL on the one OAuth app or a second OAuth app; half for naming the
  missing live one with no way to give it to GitHub.
- **tutor note:** asking the agent to read `callbackURL` from an environment variable is a good
  addition but not required. An answer that names the frontend's live address
  (`pantry.pagecove.app`) as the redirect URL hasn't named the right one; ask which server GitHub
  sends the code to. Never tell a learner GitHub allows only one callback URL: that is out of date.

### config-file

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Not as it stands: the client secret must not go in a committed file, since the
  repository is public. I'll set `GITHUB_CLIENT_SECRET` in Rivetbox's settings for the backend
  myself, and in my local `backend/.env`, which `.gitignore` keeps out of the repository; the agent
  reads it from the environment instead of `config.js`. The client ID in `frontend/.env` is fine.
- **credit:** full for both: the client secret goes into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not into a committed file, the chat or the
  frontend; and the client ID may stay in the frontend (saying step 1 can stay as it is counts).
  Half for the secret alone.
- **tutor note:** "it never reaches the browser" is the trap: true, and beside the point, since a
  committed file on a public repository is readable by anyone. An answer that moves the client ID
  out of the frontend too has the secret right; ask whether the ID is secret before ruling on the
  second half.

### strategy

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not as it stands: `repo` gives Pantry full access to every user's public and private
  repositories, and the app only shows their name and picture. Drop it and ask for no scope, or
  `read:user`; the agent can change that line.
- **credit:** full for catching `repo` as more than the app uses and naming a smaller request in
  their own words (only their profile, or just name and picture); the exact scope string is not
  required. Half for catching it with no replacement, or with a replacement that still asks for
  more than the app uses (such as `user`, which can change profile data, or adding `user:email`,
  since Pantry doesn't use email).
- **tutor note:** if they agree because "later" sounds reasonable, ask what a Pantry user is
  agreeing to on GitHub's approval screen today.

### leaked

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** It doesn't settle it: the secret was public the moment it was pushed and is still in
  the history. I'll get a new client secret from the OAuth app's settings at GitHub, put it in
  Rivetbox's settings and my local `backend/.env` where the old one was, and delete the old secret
  at GitHub.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at GitHub, and that deleting the file from the repository doesn't fix it
  because it was already public; half for some but not all.
- **tutor note:** rewriting history is fine as an extra, but if it is offered as the fix, ask
  whether anyone could have copied the secret before then. "Rotate" alone needs unpacking: ask what
  happens to the old secret, since an OAuth app can hold two at once.

### exchange

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, as it stands. The code is traded for the user on the backend with the secret
  from its environment, users are kept by their GitHub id with no password, and the cookie
  settings fit a frontend and backend on different sites.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `github_id`). A harmless suggestion (a sign-out route, a nicer error page) costs nothing, and so
  does raising whether the session cookie works across the two hosts. None otherwise.
- **tutor note:** an answer that holds off only to ask what `sameSite: 'none'` does is not a
  refusal; ask whether, with the answer, they would agree.
