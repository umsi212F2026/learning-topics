Dockyard hosts two parts, each at its own address, so "your Dockyard address" does not settle which
part a setting needs: the learner has to work it out from what the setting is for. The static site
(`https://lendlist.dockyard.app`) is the frontend's address; the web service
(`https://lendlist-r4tz.dockyard.app`) is the backend's. Silo hosts only the database. What each
setting is for is in the agent's answer; accept any wording that says the same thing. A value is a
secret when someone holding it could get into something of yours; an address the app's users see
is not.

The one secret in this scenario is Silo's connection string (`SILO_URI`), which holds the
database's password. A message should be declined when it would put that string in the chat or let
the agent write it into a file, and gone along with otherwise. On a message question, the decision
is credited to `c-judge-secret-request`, and saying whether the value is a secret (or public) to
`c-spot-secret`, with no reason needed; saying what to do instead is welcome but credited to
neither.

On a repair question, the criterion's answer is a reply saying the learner will put (or has put)
the connection string into the web service's settings on Dockyard themselves and telling the agent
it is there, with both reasons: the chat is kept and can be shared, and an agent holding the secret
can write it into a file that gets committed. Naming `SILO_URI` or Dockyard is welcome but not
required. A reply that keeps the secret out some other way (blanking the password, checking the
string themselves, refusing with nothing offered) is safer than complying but does not earn full
credit on its own.

The three repair questions (q8 to q10) share one answer pattern, so after feedback on the first,
the next two can be answered by rote. Weigh the first repair served most.

### q1

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: shared-vendor; c-spot-secret: calls-public
- **answer:** It is where the React app sends its requests for listings and loans. It needs the
  backend's address: the web service's, `https://lendlist-r4tz.dockyard.app`, not the static
  site's. Not a secret: anyone using the app can see where its requests go.
- **credit:**
  - `c-trace-setting-value`: full for the purpose and the backend's (web service's) address; half
    for the purpose with the static site's address, or for "the Dockyard address" without saying
    which.
  - `c-spot-secret`: full for "not a secret" with a reason like the address being public; half for
    "not a secret" with no reason.
- **tutor note:** the near-miss is the static site's address, because the React app is the part
  that reads the setting. Ask where the requests go.

### q2

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: cross-part; c-spot-secret: calls-public
- **answer:** It tells the server which pages may send it requests, so other sites can't use it.
  It needs the frontend's address: the static site's, `https://lendlist.dockyard.app`, even though
  the setting is on the server and its name says "server". Not a secret: the site's address is
  public, since everyone who visits it has it.
- **credit:**
  - `c-trace-setting-value`: full for the purpose and the frontend's (static site's) address; half
    for the purpose with the web service's address, or for "the Dockyard address" without saying
    which.
  - `c-spot-secret`: full for "not a secret" with a reason like the address being public; half for
    "not a secret" with no reason.
- **tutor note:** the name points the wrong way. The near-miss is the web service's address, read
  off "SERVER" in the name; ask whose pages the server is letting in.

### q3

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **cases:** c-trace-setting-value: db-details; c-spot-secret: calls-secret
- **answer:** It is how the server gets into the database. It needs the database's connection
  details, the line on Silo's Connect panel. It is a secret: the line includes what the server uses
  to get in, so whoever holds it can get into the database.
- **credit:**
  - `c-trace-setting-value`: full for what it is for and that it needs the database's connection
    details; half for one of the two.
  - `c-spot-secret`: full for "a secret" because holding it gets someone into the database; half
    for "a secret" with no reason or a reason that wouldn't make it one.
- **tutor note:** the near-miss is "not a secret, it's an address (a URI)", read off the name.
  Ask what else the server needs, besides where the database is, to be let in.

### q4

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: allows-safe; c-spot-secret: calls-public
- **answer:** Yes. The web service's address is public (anyone using the app sees where its
  requests go), so it can go in the chat.
- **credit:**
  - `c-judge-secret-request`: full for going along with it. None for declining.
  - `c-spot-secret`: full for saying the address isn't a secret (or is public), with or without a
    reason. None for saying nothing about the value, or calling it a secret.

### q5

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-chat; c-spot-secret: calls-secret
- **answer:** No. The Connect panel shows the connection string, password and all, which is a
  secret; a screenshot of it puts it in the chat, whatever the agent means to check.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying what's on the panel is a secret (or sensitive), with or
    without a reason. None for saying nothing about it, or calling it not a secret.
- **tutor note:** "check the host name" is the lure: the agent asks for one harmless piece and the
  screenshot carries the whole string.

### q6

- **goal:** `c-judge-secret-request`
- **cases:** allows-safe
- **answer:** Yes. The change only makes the server read the connection string from its settings;
  no value passes through the chat or into a file, and committing and redeploying move none.
- **credit:** full for going along with it. None for declining.
- **tutor note:** the near-miss is declining because the message mentions the database, the
  settings and a redeploy. Ask what value the agent would see or write.

### q7

- **goal:** `c-judge-secret-request`, `c-spot-secret`
- **cases:** c-judge-secret-request: declines-file; c-spot-secret: calls-secret
- **answer:** No. The connection string is a secret, and the agent would write it into
  `server/db.js`, a file that gets committed, even though nothing is pasted into the chat.
- **credit:**
  - `c-judge-secret-request`: full for declining. None for going along with it.
  - `c-spot-secret`: full for saying the connection string is a secret (or sensitive), with or
    without a reason. None for saying nothing about the value, or calling it not a secret.
- **tutor note:** "a fallback" and "to save you a step" are the lure, and so is not being asked to
  paste anything. The near-miss is going along with it because the secret never enters the chat.

### q8

- **goal:** `c-secret-instead`
- **answer:** A reply such as "I won't paste it here. I'll add `SILO_URI` in the web service's
  settings on Dockyard myself, copied from Silo's Connect panel, and tell you when it's there." It
  is safer because the chat is kept and can be shared, so a string pasted there stays readable;
  and an agent that holds the string can write it into a file that gets committed.
- **credit:** full for a reply that puts the string into the host's settings themselves and tells
  the agent it is there, with both reasons; half for that reply with one reason, or for both
  reasons with a reply that keeps the string out some other way.

### q9

- **goal:** `c-secret-instead`
- **answer:** A reply such as "Please don't put it in `dockyard.yaml`. I've added `SILO_URI` in the
  web service's settings on Dockyard myself, so it's already set on every deploy; leave it out of
  every file." It is safer because the file is committed with the repo, where anyone who can see
  the code can read the string, and an agent holding the string can write it into this file or
  another; and keeping it out of the chat matters too, since the chat is kept and can be shared.
- **credit:** full for a reply that puts the string into the host's settings themselves and tells
  the agent it is there, with both reasons; half for that reply with one reason, or for both
  reasons with a reply that keeps the string out some other way.
- **tutor note:** the message never mentions the chat, so the reason about the chat is the one most
  often left out. That is half credit, not full.

### q10

- **goal:** `c-secret-instead`
- **answer:** A reply such as "That command prints the connection string, so I won't paste its
  output. I've copied the line from Silo's Connect panel again and pasted it into `SILO_URI` in
  the web service's settings on Dockyard myself; it's there now, so please redeploy and check the
  logs." It is safer because the chat is kept and can be shared, and an agent holding the string
  can write it into a file that gets committed.
- **credit:** full for a reply that puts the string into the host's settings themselves, or checks
  or re-enters it there themselves, and tells the agent it is there, with both reasons; half for
  that reply with one reason, or for both reasons with a reply that keeps the string out some
  other way, such as pasting the output with the password blanked out, or comparing the two
  strings somewhere other than Dockyard's settings.
- **tutor note:** offering to paste the output with the password blanked out is the common reply
  here. It is safer than complying, but on its own it is half credit at most.
