Claimdesk signs in through GitHub and uses the user's GitHub name, picture and email, so email is a
scope it may ask for. The frontend is on Brightdock (`https://claimdesk.brightdock.app`), the backend
on Railspur (`https://claimdesk-api.railspur.com`), locally ports 5173 and 3001. The deck is seven
cards, one per case plus a second `secret-placement` card. Piles: yours, card 5; your agent's,
card 7; change it first, cards 1, 2, 3, 4 and 6. Hard cards: 1 (a plausible justification), 3 (a
plausible justification), 5 (config lines, with a client ID value in a `VITE_` variable, which
looks alarming) and 7 (code with agent comments and jargon). The rest are Medium.

For a card with no actor named that belongs to the learner (card 5), "change it first" with the
change being "I do this myself" is the same answer as "yours": credit it as the right pile.

### card-1

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Change it first: you create the OAuth app yourself, in your own GitHub developer
  settings, rather than letting your agent act in your signed-in browser; it gives you a client ID
  and a client secret, which the later steps use.
- **credit:** full for change it first, to the learner creating the OAuth app themselves ("yours,
  not the agent's" is the same answer), and naming the client ID and the client secret as what it
  gives; any reason, or none, counts for the pile. Half for the right pile with only one of the
  two values or neither, or for both values in the wrong pile.
- **tutor note:** don't require GitHub's button or menu names. A learner who accepts because it
  saves a trip has taken the justification at its word; ask whose account the agent would be
  acting in.

### card-2

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Change it first. The `user` scope lets the app change the user's GitHub profile as
  well as read it, and Claimdesk only reads their name, picture and email. Ask for `read:user` and
  `user:email` instead; your agent can make the change.
- **credit:** full for catching that `user` asks for more than Claimdesk uses (it can change their
  profile, not just read it) and naming, in their own words, a smaller request (read-only access to
  their profile and email); the exact scope strings are not required. Half for catching the excess
  with no replacement, with a replacement that still asks for more than the app uses (such as
  `repo`), or with one that asks for less than the app uses (such as dropping email, which Claimdesk
  uses).
- **tutor note:** a learner who drops email entirely has cut something the app uses, which is
  half; ask what the
  person claiming an item sees.

### card-3

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Change it first. GitHub also needs the live app's callback URL,
  `https://claimdesk-api.railspur.com/auth/github/callback`, added as a second callback URL on the one
  OAuth app or through a second OAuth app. Yours to do, at GitHub.
- **credit:** full for naming both the localhost URL and the live backend's URL with the same path,
  and that the learner gives GitHub both (a second URL on the app, or a second app). Half for
  naming the missing live URL with no way to give it to GitHub, or for "yours" with only the one
  URL.
- **tutor note:** the agent's "sends everyone back" is the trap; ask where GitHub would send
  someone signing in on the live app. A learner who names `claimdesk.brightdock.app` has the right
  idea but the frontend's host.

### card-4

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Change it first. Don't paste the client secret into the chat: put it into Railspur's
  settings for the backend yourself (and into the local `backend/.env` that `.gitignore` keeps out
  of the repository). The client ID in `frontend/.env` is fine, and the agent may put it there.
- **credit:** full for change it first, saying the client secret goes into the backend host's
  settings by the learner's own hand and not through the chat, and that the client ID may go in
  the frontend (saying the ID part can stay as it is counts). Half for the secret alone.
- **tutor note:** a learner who refuses to paste either value has the secret right but not the
  ID; ask whether anything goes wrong if a visitor sees the client ID.

### card-5

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Yours. The client secret goes into Railspur's settings for the backend by your own
  hand; the client ID in Brightdock's build settings, where every visitor's browser gets it, is
  fine, since the client ID is not a secret.
- **credit:** full for the right pile (yours, or change it first to "I do it myself"; splitting the
  card, the secret yours and the ID your agent's, also has the pile right), saying the secret goes
  in the backend host's settings and the learner puts it there, and that the client ID may be in
  the frontend. Half for the secret alone.
- **tutor note:** a learner who moves the client ID out of the frontend because its value is
  showing has taken a sound step for a flaw; ask what someone could do with the client ID alone.

### card-6

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** Change it first. The secret was public the moment it was pushed, so deleting the
  file doesn't fix it. Get a new client secret from GitHub, put it where the old one was
  (Railspur's settings for the backend and the local `backend/.env`), and delete the old secret in
  the OAuth app's settings at GitHub, since the old one stays valid until it is removed. You do
  these yourself; ignoring `.env` from now on is still worth doing.
- **credit:** full for all three: the new secret in place, the old one deleted or disabled at
  GitHub, and that the repository fix doesn't settle it. Half for some but not all.
- **tutor note:** rewriting history to remove the file doesn't settle it either; a learner who
  proposes that instead of a new secret has missed that the secret was already public.

### card-7

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Your agent's, as written. The backend trades GitHub's code for who the user is, with
  the client secret read from its environment, and users are keyed by `github_id` with no
  password.
- **credit:** full for your agent's, as written, with a reason that doesn't call the step broken,
  and no change that would break it (moving the code exchange or the client secret into React,
  adding a password, keying users by email). A harmless addition (a sign-out route, an error page)
  costs nothing. None otherwise.
- **tutor note:** don't require the learner to read every line of the code; a learner who balks at
  the jargon can be asked where the code runs and what it keeps about the user.
