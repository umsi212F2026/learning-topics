Trailhead signs in through GitHub and shows only the user's GitHub name and picture, never their
email. The frontend is on Pagewell (`https://trailhead.pagewell.app`), the backend on Moorbolt
(`https://trailhead-api.moorbolt.dev`), locally ports 5173 and 3001. The deck is seven cards, one
per case plus a second `secret-placement` card. Piles: yours, cards 1 and 5; your agent's, card 6;
change it first, cards 2, 3, 4 and 7. Hard cards: 2 (a code line with a plausible justification),
3 (a plausible justification) and 5 (a sound card with the client ID in a `VITE_` variable, which
looks alarming). The rest are Medium.

For a card with no actor named that belongs to the learner (cards 1 and 5), "change it first" with
the change being "I do this myself" is the same answer as "yours": credit it as the right pile.

### card-1

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Yours. You register Trailhead with GitHub yourself, in your own developer settings,
  and that gives you a client ID and a client secret, which the later steps use.
- **credit:** full for the right pile (yours, or change it first to "I do it myself") and naming
  the client ID and the client secret as what it gives; any reason, or none, counts for the pile.
  Half for the right pile with only one of the two values or neither, or for both values in the
  wrong pile.
- **tutor note:** don't require GitHub's button or menu names.

### card-2

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Change it first. `repo` asks for access to the user's repositories, including private
  ones, but Trailhead shows only their name and picture, and "later" is no reason to ask now. Ask
  for no scope, or `read:user`; your agent can make the change.
- **credit:** full for catching that `repo` asks for more than Trailhead shows and naming, in their
  own words, a smaller request (only their public profile, their name and picture); the exact scope
  string is not required. Half for catching the excess with no replacement, or with a replacement
  that still asks for more than the app shows (such as `user`, or `user:email` when the app doesn't
  use email).
- **tutor note:** a learner who accepts it because of the comment has taken the justification at
  its word; ask what Trailhead shows today.

### card-3

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Change it first. Don't paste the client secret into the chat: put it into Moorbolt's
  settings for the backend yourself (and into the local `backend/.env` that `.gitignore` keeps out
  of the repository). The client ID in `frontend/.env` is fine, and the agent may put it there.
- **credit:** full for change it first, saying the client secret goes into the backend host's
  settings by the learner's own hand and not through the chat, and that the client ID may go in
  the frontend (saying the ID part can stay as it is counts). Half for the secret alone.
- **tutor note:** a learner who refuses to paste either value has the secret right but not the
  ID; ask whether anything goes wrong if a visitor sees the client ID.

### card-4

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Change it first. GitHub also needs the live app's callback URL,
  `https://trailhead-api.moorbolt.dev/auth/github/callback`, added as a second callback URL on the
  one registration or through a second OAuth app. Yours to do, at GitHub.
- **credit:** full for naming both the localhost URL and the live backend's URL with the same path,
  and that the learner gives GitHub both (a second URL on the registration, or a second
  registration). Half for naming the missing live URL with no way to give it to GitHub, or for
  "yours" with only the one URL.
- **tutor note:** a learner who names the frontend's live address (`trailhead.pagewell.app`) as
  the callback has the right idea but the wrong host; ask where the code goes to be traded.

### card-5

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Yours. The client secret goes into Moorbolt's settings for the backend by your own
  hand, never through the chat; the client ID in `VITE_GITHUB_CLIENT_ID` is fine, since the client
  ID is not a secret.
- **credit:** full for the right pile (yours, or change it first to "I do it myself"; splitting the
  card, the secret yours and the ID your agent's, also has the pile right), saying the secret goes
  in the backend host's settings and the learner puts it there, and that the client ID may be in
  the frontend. Half for the secret alone.
- **tutor note:** a learner who moves the client ID out of the frontend because of `VITE_` has
  taken a sound step for a flaw; ask what someone could do with the client ID alone.

### card-6

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Your agent's, as written. The code exchange and the secret stay on the backend, and
  users are keyed by GitHub's id with no password.
- **credit:** full for your agent's, as written, with a reason that doesn't call the step broken,
  and no change that would break it (moving the code exchange or the client secret into React,
  adding a password, keying users by email). A harmless addition (a sign-out route, an error page)
  costs nothing. None otherwise.

### card-7

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** Change it first. The secret was public the moment it was pushed, so deleting the file
  doesn't fix it. Get a new client secret from GitHub, put it where the old one was (Moorbolt's
  settings for the backend and the local `backend/.env`), and delete the old secret in the OAuth
  app's settings at GitHub, since the old one stays valid until it is removed. You do these
  yourself; ignoring `.env` from now on is still worth doing.
- **credit:** full for all three: the new secret in place, the old one deleted or disabled at
  GitHub, and that the repository fix doesn't settle it. Half for some but not all.
- **tutor note:** rewriting history to remove the file doesn't settle it either; a learner who
  proposes that instead of a new secret has missed that the secret was already public.
