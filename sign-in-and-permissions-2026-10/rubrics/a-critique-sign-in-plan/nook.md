GitHub is the provider. Nook shows the user's GitHub name and profile picture and emails them, so it
needs read-only access to their profile and their email address: `user:email`, with `read:user` if
wanted, and nothing more. The backend's two addresses are `http://localhost:3001` and
`https://nook-api.forgeline.com`, so the two redirect URLs are
`http://localhost:3001/auth/github/callback` and
`https://nook-api.forgeline.com/auth/github/callback`. A GitHub OAuth app holds up to 10 callback
URLs (GitHub changelog, 2026-08-14), and can hold more than one client secret. Levels: `browser`
Medium, `one-callback` Hard (the single URL comes with a plausible reason), `env-lines` Hard (the
secret shows only as a config line, beside a step that also puts it in the right place),
`user-scope` Medium, `force-push` Hard (history is rewritten, and keeping the secret comes with a
plausible reason), `passport-flow` Hard (agent jargon throughout, and the client ID in the
frontend's environment). Every step outside the one each question's case fixes is sound. Credit
what the answer commits the learner to, not its tone. A flag on a step the excerpt left unclear
about who does it (an unattributed step reads as the agent's) is not a mistake and costs nothing.

### browser

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Not as it stands: I'll create the OAuth app in GitHub's developer settings myself,
  rather than have the agent do it in my signed-in browser. It gives me a client ID and a client
  secret for the later steps. The rest can stay.
- **credit:** full for saying the registration is theirs to do (with any reason, or none) and
  naming both the client ID and the client secret as what it gives them; half for one of the two.
  Don't require any console's page or button names, and don't require a view on whether the agent
  could manage it.
- **tutor note:** no password is asked for here, which is what makes it easy to agree to. If they
  agree because they never hand over a password, ask who would be at the keyboard at GitHub, and
  what the agent would then have copied. If they name only "credentials", ask what the two values
  are called and whether they differ.

### one-callback

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Not quite: GitHub will only send users back to the callback URL it has, and that one
  is on my laptop, so sign-in on the live site will fail however the backend reads its setting. I'll
  also add `https://nook-api.forgeline.com/auth/github/callback` to the same OAuth app, which takes
  more than one callback URL (or register a second OAuth app for the live site), and set
  `GITHUB_CALLBACK_URL` to that address in Forgeline's settings.
- **credit:** full for naming the live redirect URL (the backend's live address with the same path;
  "the live backend's callback" counts if it plainly means that) and a way to give GitHub both,
  either a second callback URL on the one OAuth app or a second OAuth app; half for naming the
  missing live one with no way to give it to GitHub. Setting the live value of
  `GITHUB_CALLBACK_URL` on Forgeline is a good addition but not required.
- **tutor note:** the trap is step 3's reason: reading the URL from the environment is good
  practice, but GitHub still has to have the live URL. An answer that names the frontend's live
  address (`nook.paperkite.app`) as the redirect URL hasn't named the right one; ask which server
  GitHub sends the code to. Never tell a learner GitHub allows only one callback URL: that is out of
  date.

### env-lines

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Not as it stands: `VITE_GITHUB_CLIENT_SECRET` must come out of `frontend/.env` and
  Paperkite's settings, since anything with the `VITE_` prefix ends up in the files every visitor
  downloads. The secret belongs only where step 2 puts it, in Forgeline's settings and my local
  `backend/.env`, set by me. The client ID can stay in the frontend.
- **credit:** full for both: the client secret goes only into the backend host's settings (and the
  local, git-ignored `.env`) by the learner's own hand, not into the frontend (saying step 2 can
  stay and the secret line in step 1 must go counts); and the client ID may stay in the frontend.
  Half for the secret alone.
- **tutor note:** step 2 is right, which makes it easy to agree to the whole. If they agree, ask
  what each line in step 1's block is for and who can read the frontend's built files. An answer
  that moves the client ID out of the frontend too has the secret right; ask whether the ID is
  secret before ruling on the second half.

### user-scope

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Not as it stands: `user` lets Nook change every user's GitHub profile, and the app
  only reads their name, picture and email. Ask for `user:email` (with `read:user` if wanted)
  instead, which reads the profile and the email address and changes nothing; the agent can change
  that line.
- **credit:** full for catching `user` as more than the app uses and naming a smaller request in
  their own words that still covers the email (read-only access to their profile and email
  address); the exact scope string is not required. Half for catching it with no replacement, or
  with a replacement that still asks for more than the app uses (such as adding `repo`), or one
  that drops the email Nook sends confirmations to (such as no scope, or `read:user` alone).
- **tutor note:** "covers each user's profile" is true, and leaves out that it covers writing to
  it. If they agree because the app needs the email, ask whether reading an email address needs
  permission to change a profile. If they offer `read:user` alone, ask where Nook would then send
  the confirmation.

### force-push

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** It doesn't settle it: the secret was public the moment it was pushed, and anyone could
  have copied it in forty minutes, whatever the history says now. I'll get a new client secret from
  the OAuth app's settings at GitHub, put it in Forgeline's settings and my local `backend/.env`
  where the old one was, and delete the old secret at GitHub.
- **credit:** full for all three: a new secret put where the old one was (the backend host's
  settings and the local `.env`; "replace it" with the backend host named counts), the old one
  deleted or disabled at GitHub, and that removing it from the repository, even from its history,
  doesn't fix it because it was already public; half for some but not all.
- **tutor note:** the rewrite and step 4's reason are the trap. Keeping the history rewrite as an
  extra is fine. "Rotate" alone needs unpacking: ask what happens to the old secret, since an OAuth
  app can hold two at once.

### passport-flow

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Yes, as it stands. The client ID in the frontend is fine, since it isn't secret; the
  code is traded for the user on the backend with the secret from its environment, users are kept by
  their GitHub id with no password, the scopes cover only the profile and email the app uses, and
  the cookie settings fit a frontend and backend on different sites.
- **credit:** full when they agree and ask for no change that would break it (moving the code
  exchange or the client secret into React, adding a password, keying users by email instead of
  `github_id`). A harmless suggestion (a sign-out route, a nicer error page) costs nothing, and so
  does raising whether the session cookie works across the two hosts. None otherwise, including
  an answer that holds off until the client ID is moved out of the frontend because it is secret:
  that is not going along with a sound plan.
- **tutor note:** the client ID in step 2 is the step that looks alarming. If they object to it,
  ask whether the client ID could do anything without the secret. An answer that holds off only to
  ask what `findOrCreateUser` or `connect-pg-simple` does is not a refusal; ask whether, with the
  answer, they would agree.
