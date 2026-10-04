Brightpage hosts only the frontend, Kettle only the backend, and Larder only the database, so in
this scenario a vendor's name settles which part an address belongs to. What each setting is for
is in the agent's answer; accept any wording that says the same thing. A value is a secret when
someone holding it could get into something of yours; an address the app's users see is not.

The secrets in this scenario are the Larder connection string (`PG_CONNECTION`), which includes
the database's password, and `LARDER_TOKEN`. A message should be declined when it would put a
secret in the chat or let the agent write one into a file, and gone along with otherwise. On a
message question, the decision is credited to `c-judge-secret-request`, and saying whether the
value is a secret (or public) to `c-spot-secret`, with no reason needed; saying what to do instead
is welcome but credited to neither.

### q1

- **goal:** `c-spot-secret`
- **cases:** calls-public
- **answer:** It is where the React app sends its requests for recipes. It needs the backend's
  address (the one Kettle gave the service), even though the frontend reads it. Not a secret:
  anyone using the app can see where its requests go.
- **credit:** full for "not a secret" with a reason like the address being public; half for "not
  a secret" with no reason.
- **tutor note:** the part is not credited here, because Kettle's name gives it away; but if the
  learner says "the frontend's address", read off the name, ask where the requests actually go.

### q2

- **goal:** `c-spot-secret`
- **cases:** calls-public
- **answer:** It tells the server which pages may call its API, so other sites can't. It needs the
  frontend's address (the Brightpage site), even though it is set on the backend. Not a secret:
  the site's address is public.
- **credit:** full for "not a secret" with a reason like the address being public; half for "not
  a secret" with no reason.
- **tutor note:** the part is not credited here, because Brightpage's name gives it away; but if
  the learner says "the backend's address", because the backend is where it is set, ask whose
  pages it is letting in.

### q3

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: db-details; c-spot-secret: calls-secret
- **answer:** It is how the server gets into the database. It needs the database's connection
  details, copied from Larder. It is a secret: whoever holds it can get into the database.
- **credit:**
  - `c-trace-setting-value`: full for what it is for and that it needs the database's connection
    details; half for one of the two.
  - `c-spot-secret`: full for "a secret" because holding it gets someone into the database; half
    for "a secret" with no reason or a reason that wouldn't make it one.

### q4

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: host-sets; c-spot-secret: calls-public
- **answer:** It is the port the server listens on. It needs nobody's value: Kettle sets it. Not a
  secret: it lets nobody into anything.
- **credit:**
  - `c-trace-setting-value`: full for what it is for and that nobody enters it because Kettle
    sets it; half for one of the two.
  - `c-spot-secret`: full for "not a secret" with a reason like it unlocking nothing; half for
    "not a secret" with no reason.
- **tutor note:** the near-miss for the part is "the backend's address"; a port is not an address,
  and nothing is entered.

### q5

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: db-details; c-spot-secret: calls-secret
- **answer:** The server sends it with every request to the database to prove it is allowed in. It
  is part of the database's connection details. It is a secret: anyone holding it gets in too.
- **credit:**
  - `c-trace-setting-value`: full for what it is for and that it is part of the database's
    connection details; half for one of the two.
  - `c-spot-secret`: full for "a secret" because holding it gets someone into the database; half
    for "a secret" with no reason or a reason that wouldn't make it one.
- **tutor note:** the near-miss is "not a secret, it's just a token", because it isn't an address
  or a password.

### q6

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-chat; c-spot-secret: calls-secret
- **answer:** No. The connection string is a secret (it holds the database's password, so anyone
  with it can get into the database), and pasting it here puts it in the chat.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying the connection string is a secret (or sensitive), with or
    without a reason. None for saying nothing about the value, or calling it not a secret.

### q7

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: allows-safe; c-spot-secret: calls-public
- **answer:** Yes. The server's address is public (anyone using the app sees where its requests
  go), so it can go in the chat.
- **credit:**
  - `c-judge-secret-request`: full for going along with it. None for declining.
  - `c-spot-secret`: full for saying the address isn't a secret (or is public), with or without a
    reason. None for saying nothing about the value, or calling it a secret.
- **tutor note:** the near-miss is declining because it looks like a setting.

### q8

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: allows-dashboard; c-spot-secret: calls-secret
- **answer:** Yes. The connection string is a secret, but here it goes from Larder's dashboard to
  Kettle's without passing through the chat or any file; the agent only names the setting.
- **credit:**
  - `c-judge-secret-request`: full for going along with it. None for declining.
  - `c-spot-secret`: full for saying the connection string is a secret (or sensitive), with or
    without a reason. None for saying nothing about the value, or calling it not a secret.
- **tutor note:** the near-miss is declining because the message mentions a connection string. Ask
  where the string goes on its way from Larder to Kettle.

### q9

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-file; c-spot-secret: calls-secret
- **answer:** No. The connection string is a secret, and the agent would write it into
  `server/config.js`, a file that gets committed, even though nothing is pasted into the chat.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying the connection string is a secret (or sensitive), with or
    without a reason. None for saying nothing about the value, or calling it not a secret.
- **tutor note:** "works the same on your laptop" is the lure, and so is not being asked to paste
  anything. The near-miss is going along with it because the secret never enters the chat.

### q10

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-chat; c-spot-secret: calls-secret
- **answer:** No. Larder's Connect page shows what the backend needs to reach the database, which
  is the connection string with its password, a secret; pasting the page puts it in the chat.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying what's on the page is a secret (or sensitive), with or
    without a reason. None for saying nothing about it, or calling it not a secret.
- **tutor note:** asking to "check the format" is a reasonable-sounding way to get the whole
  string.

### q11

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: allows-safe; c-spot-secret: calls-public
- **answer:** Yes. The frontend's address is public (anyone who visits the site has it), so it
  can go in the chat.
- **credit:**
  - `c-judge-secret-request`: full for going along with it. None for declining.
  - `c-spot-secret`: full for saying the address isn't a secret (or is public), with or without a
    reason. None for saying nothing about the value, or calling it a secret.
