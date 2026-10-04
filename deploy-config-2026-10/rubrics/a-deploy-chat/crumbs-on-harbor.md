Harbor hosts two parts, each at its own address, so "your Harbor address" does not settle which
part a setting needs: the learner has to work it out from what the setting is for. What each
setting is for is in the agent's answer; accept any wording that says the same thing. A value is
a secret when someone holding it could get into something of yours; an address the app's users
see is not. The static site (`https://crumbs.harbor.app`) is the frontend's address; the web
service (`https://crumbs-k3x9.harbor.app`) is the backend's. Larder hosts only the database.

The one secret in this scenario is Larder's connection string (`LARDER_LINK`), which holds what
the server uses to get into the database. A message should be declined when it would put that
string in the chat or let the agent write it into a file, and gone along with otherwise. On a
message question, the decision is credited to `c-judge-secret-request`, and saying whether the
value is a secret (or public) to `c-spot-secret`, with no reason needed; saying what to do instead
is welcome but credited to neither.

On a repair question, the criterion's answer is a reply saying the learner will put (or has put)
the connection string into the web service's settings on Harbor themselves and telling the agent
it is there, with both reasons: the chat is kept and can be shared, and an agent holding the secret
can write it into a file that gets committed. Naming `LARDER_LINK` or Harbor is welcome but not
required. A reply that keeps the secret out some other way (blanking the password, checking the
string themselves, refusing with nothing offered) is safer than complying but does not earn full
credit on its own: half credit is the right reply with one of the two reasons, or both reasons
with a reply that keeps the secret out some other way. Complying earns none.

The three repair questions (q8 to q10) share one answer pattern, so after feedback on the first,
the next two can be answered by rote. Weigh the first repair served most.

### q1

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: shared-vendor; c-spot-secret: calls-public
- **answer:** It is where the React app sends its requests. It needs the backend's address: the
  web service's, `https://crumbs-k3x9.harbor.app`, not the static site's. Not a secret: anyone
  using the app can see where its requests go.
- **credit:**
  - `c-trace-setting-value`: full for the purpose and the backend's (web service's) address; half
    for the purpose with the wrong Harbor address, or for "Harbor's address" without saying which.
  - `c-spot-secret`: full for "not a secret" with a reason like the address being public; half for
    "not a secret" with no reason.
- **tutor note:** the near-miss is copying the first Harbor address in sight, often the static
  site's. Ask where the requests go.

### q2

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: cross-part; c-spot-secret: calls-public
- **answer:** It tells the server which pages may send it requests, so other sites can't use it.
  It needs the frontend's address: the static site's, `https://crumbs.harbor.app`, even though the
  setting is on the server and its name says "host". Not a secret: the site's address is public,
  since everyone who visits it has it.
- **credit:**
  - `c-trace-setting-value`: full for the purpose and the frontend's (static site's) address; half
    for the purpose with the web service's address, or for "the Harbor address" without saying
    which.
  - `c-spot-secret`: full for "not a secret" with a reason like the address being public; half for
    "not a secret" with no reason.
- **tutor note:** the near-miss is the web service's address, because the server is the part that
  reads the setting and "host" sounds like the server. Ask whose pages the server is letting in.

### q3

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: db-details; c-spot-secret: calls-secret
- **answer:** It is how the server gets into the database. It needs the database's connection
  details, the connection string from Larder's dashboard. It is a secret: whoever holds it can get
  into the database.
- **credit:**
  - `c-trace-setting-value`: full for what it is for and that it needs the database's connection
    details; half for one of the two.
  - `c-spot-secret`: full for "a secret" because holding it gets someone into the database; half
    for "a secret" with no reason or a reason that wouldn't make it one.
- **tutor note:** the near-miss is "not a secret, it's a link", read off the name. Ask what the
  agent said the server uses it for.

### q4

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: allows-safe; c-spot-secret: calls-public
- **answer:** Yes. The static site's address is public (anyone who visits the site has it), so it
  can go in the chat.
- **credit:**
  - `c-judge-secret-request`: full for going along with it. None for declining.
  - `c-spot-secret`: full for saying the address isn't a secret (or is public), with or without a
    reason. None for saying nothing about the value, or calling it a secret.

### q5

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-chat; c-spot-secret: calls-secret
- **answer:** No. A command that prints everything the backend needs to reach the database prints
  the connection string, a secret; pasting its output puts it in the chat, whatever the agent means
  to check.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying what the command prints is a secret (or sensitive), with or
    without a reason. None for saying nothing about it, or calling it not a secret.
- **tutor note:** "check which region it's in" is the lure: the agent asks about one harmless
  detail and the output carries the whole string.

### q6

- **goal:** `c-judge-secret-request`
- **cases:** allows-safe
- **answer:** Yes. Changing the start command and redeploying move no value through the chat or
  into a file; the server reaches the database with whatever is already in its settings.
- **credit:** full for going along with it. None for declining.
- **tutor note:** the near-miss is declining because the message mentions the database and a
  redeploy. Ask what value the agent would see or write.

### q7

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-file; c-spot-secret: calls-secret
- **answer:** No. The connection string is a secret, and the agent would write it into
  `server/seed.js`, a file that gets committed, even though nothing is pasted into the chat.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying the connection string is a secret (or sensitive), with or
    without a reason. None for saying nothing about the value, or calling it not a secret.
- **tutor note:** "runs on your laptop too" and "from anywhere" are the lure, and so is not being
  asked to paste anything. The near-miss is going along with it because the secret never enters
  the chat.

### q8

- **goal:** `c-secret-instead`
- **answer:** A reply such as "I won't paste it here. I'll add `LARDER_LINK` in the web service's
  settings on Harbor myself, copied from Larder's dashboard, and tell you when it's there." It is
  safer because the chat is kept and can be shared, so a string pasted there stays readable; and an
  agent that holds the string can write it into a file that gets committed.
- **credit:** full for a reply that puts the string into the host's settings themselves and tells
  the agent it is there, with both reasons; half for that reply with one reason, or for both
  reasons with a reply that keeps the string out some other way.

### q9

- **goal:** `c-secret-instead`
- **answer:** A reply such as "Please don't put it in the test file. I've added the connection string
  as `LARDER_LINK` in the web service's settings on Harbor myself, so have the tests read it from
  there and leave it out of every file." It is safer because a test file is committed
  with the repo, where anyone who can see the code can read the string, and an agent holding the
  string can write it into this file or another; and keeping it out of the chat matters too, since
  the chat is kept and can be shared.
- **credit:** full for a reply that puts the string into the host's settings themselves and tells
  the agent it is there, with both reasons; half for that reply with one reason, or for both
  reasons with a reply that keeps the string out some other way.
- **tutor note:** the message never mentions the chat, so the reason about the chat is the one most
  often left out. That is half credit, not full. A reply that keeps the tests off the real database
  instead is a fair engineering call, but it is a way of keeping the string out, not the
  criterion's answer.

### q10

- **goal:** `c-secret-instead`
- **answer:** A reply such as "The settings page shows the connection string, so I won't send a
  screenshot. I've copied the string from Larder's dashboard again and pasted it into `LARDER_LINK`
  in the web service's settings on Harbor myself; it's there now, so please redeploy and check the
  logs." It is safer because the chat is kept and can be shared, and an agent holding the string
  can write it into a file that gets committed.
- **credit:** full for a reply that puts the string into the host's settings themselves, or checks
  or re-enters it there themselves, and tells the agent it is there, with both reasons; half for
  that reply with one reason, or for both reasons with a reply that keeps the string out some
  other way, such as a screenshot with the value covered, or a check made somewhere other than
  Harbor's settings.
- **tutor note:** checking the value for a stray space in Harbor's settings themselves, and
  telling the agent it's fixed, is the common reply here, and it is the criterion's answer. A
  screenshot with the value covered is safer than complying, but on its own it is half credit at
  most.
