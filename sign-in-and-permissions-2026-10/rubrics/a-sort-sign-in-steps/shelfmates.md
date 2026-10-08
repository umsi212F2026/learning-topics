Shelfmates signs in through Google and shows the user's Google name, picture and email, so email
is a scope it may ask for. The frontend is on Leafhost (`https://shelfmates.leafhost.app`), the
backend on Corvane (`https://shelfmates-api.corvane.io`), locally ports 5173 and 3001. The deck is
seven cards, one per case plus a second `secret-placement` card. Piles: yours, card 5; your
agent's, card 7; change it first, cards 1, 2, 3, 4 and 6. Hard cards: 2 (a code line with a
plausible justification) and 6 (a plausible justification). The rest are Medium.

For a card with no actor named that belongs to the learner (card 5), "change it first" with the
change being "I do this myself" is the same answer as "yours": credit it as the right pile.

### card-1

- **goal:** `c-set-up-sign-in`
- **cases:** register-yourself
- **answer:** Change it first: don't give your agent your Google password; you create the OAuth
  client yourself, in Google's developer console, and that gives you a client ID and a client
  secret, which the later steps use.
- **credit:** full for change it first, to the learner creating the OAuth client themselves
  ("yours, not the agent's" is the same answer), and naming the client ID and the client secret as
  what it gives; any reason, or none, counts for the pile. Half for the right pile with only one
  of the two values or neither, or for both values in the wrong pile.
- **tutor note:** don't require the console's button or menu names. A learner who would let the
  agent do it if it promised to forget the password is in the wrong pile.

### card-2

- **goal:** `c-set-up-sign-in`
- **cases:** too-much-scope
- **answer:** Change it first. The calendar scope asks for access to the user's Google Calendar,
  but Shelfmates shows only their name, picture and email, and "later" is no reason to ask now.
  Ask for `openid profile email` only; your agent can make the change.
- **credit:** full for catching that the calendar scope asks for more than Shelfmates uses and
  naming, in their own words, a smaller request (their name, picture and email, or `openid profile
  email`); the exact scope string is not required, and keeping `email` is right here. Half for
  catching the excess with no replacement, or with a replacement that still asks for more than the
  app uses.
- **tutor note:** a learner who drops `email` as well has cut something the app uses; ask what
  the member list shows.

### card-3

- **goal:** `c-set-up-sign-in`
- **cases:** two-redirects
- **answer:** Change it first. Google also needs the localhost redirect URI,
  `http://localhost:3001/auth/google/callback`, added as a second redirect URI on the same OAuth
  client (or through a second client). Yours to do, at Google.
- **credit:** full for naming both the live backend's URL and the localhost one with the same
  path, and that the learner gives Google both (a second URI on the client, or a second client).
  Half for naming the missing localhost URL with no way to give it to Google, or for "yours" with
  only the one URL.
- **tutor note:** a learner who names `http://localhost:5173` as the second URI has the right idea
  but the frontend's port; ask where the code goes to be traded.

### card-4

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Change it first. The client secret must not go in the frontend, where every visitor's
  browser gets it: put it into Corvane's settings for the backend yourself (and into the local
  `backend/.env` that `.gitignore` keeps out of the repository). The client ID in `frontend/.env`
  is fine.
- **credit:** full for change it first, saying the client secret goes into the backend host's
  settings by the learner's own hand, not into the frontend, and that the client ID may stay in
  the frontend (saying the ID part can stay as it is counts). Half for the secret alone.
- **tutor note:** a learner who moves both values out of the frontend has the secret right but not
  the ID; ask what someone could do with the client ID alone.

### card-5

- **goal:** `c-set-up-sign-in`
- **cases:** secret-placement
- **answer:** Yours. The client secret goes into Corvane's settings for the backend by your own
  hand, never through the chat; the client ID in the frontend's environment is fine, since the
  client ID is not a secret.
- **credit:** full for the right pile (yours, or change it first to "I do it myself"; splitting the
  card, the secret yours and the ID your agent's, also has the pile right), saying the secret goes
  in the backend host's settings and the learner puts it there, and that the client ID may be in
  the frontend. Half for the secret alone.

### card-6

- **goal:** `c-set-up-sign-in`
- **cases:** leaked-secret
- **answer:** Change it first. The secret was public the moment it was pushed, and it stays in the
  repository's history, so deleting the file doesn't fix it. Get a new client secret from Google,
  put it where the old one was (Corvane's settings for the backend and the local `backend/.env`),
  and delete or disable the old secret on the OAuth client at Google, since the old one stays valid
  until it is removed. You do these yourself; ignoring `.env` from now on is still worth doing.
- **credit:** full for all three: the new secret in place, the old one deleted or disabled at
  Google, and that the repository fix doesn't settle it. Half for some but not all.
- **tutor note:** the agent's "nobody can get the secret" is the trap; ask who could have copied it
  between the push and the delete.

### card-7

- **goal:** `c-set-up-sign-in`
- **cases:** sound-plan
- **answer:** Your agent's, as written. The code exchange and the client secret stay on the
  backend, and users are keyed by Google's `sub` with no password.
- **credit:** full for your agent's, as written, with a reason that doesn't call the step broken,
  and no change that would break it (moving the code exchange or the client secret into React,
  adding a password, keying users by email). A harmless addition (a sign-out route, an error page)
  costs nothing. None otherwise.
- **tutor note:** the app shows email, which may tempt a learner to key users by it; ask what
  happens if a member changes the email on their Google account.
