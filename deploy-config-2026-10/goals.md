# Learning goals: deploy config

**origin:** course

**What I want to be able to do, and what would count as having got there.**

## Where this came from

_Yours to fill in. Nobody can answer this one for you._

<!-- Which of A / B / C / D, and the answer to the follow-up. -->

## What I already have

_Yours to fill in. Say where your knowledge stops, not what you have heard of._

<!--
  The nearest thing already known well, and where it stops.
  This is a claim, not a verified fact — it's a self-report about one's own knowledge,
  and the assessment may contradict it.
-->

## What I'll use it for

_Yours to fill in. The course supplies one occasion: Problem Set 3, which puts your Problem Set 2
app on the public internet, first for anyone to use and then with sign-in. Name any others you
have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Know what each setting your agent asks for is for and where its value comes from, and ask when
you don't.** Not writing the code that reads settings, not deciding where each one goes, and not
setting up the hosts. When your agent gets your app ready to deploy, it adds settings your app
never needed on localhost and asks you for values only you have, such as the addresses your hosts
gave you. If your database is on a host of its own, its connection details are one of those, and
they are a secret. This topic is enough to
follow the agent's explanation of each setting, to know which of your hosts the value comes from,
and to carry a secret from one host to another yourself instead of handing it to the agent.

This topic assumes you have studied cloud-hosting and database-hosting first, so you already have
the layout of a deployed app and know where your database will live. That is why it has no
orientation of its own. What sits past that line: choosing hosts belongs to cloud-hosting.
Deploying automatically and debugging a deployed app come in session 12, sign-in and what to do
about a secret that has already leaked in session 13, and defending the app in session 14.

## Sequence

1. vocabulary
2. capabilities

## Goals

### `c-trace-setting-value`

- **goal:** follow an agent's explanation of a setting it wants: what it is for and where its
  value comes from
- **criterion:** Given an app whose frontend, backend and database are each on a named vendor,
  and an exchange in which an agent asks for a setting under a name the learner hasn't met, a
  student asks what it is for and where its value comes from, and the agent answers. The learner
  says what the setting is for and whose value it needs (the frontend's address, the backend's
  address, the database's connection details, or nobody's, because a host sets it automatically,
  as with `PORT`). It passes when both are right, including when the setting belongs to one part
  but holds another part's address, such as the backend's allowed origin holding the frontend's
  address, and when the agent's answer names only a vendor that hosts two parts. Finding the
  value on the vendor's site, whether it is a secret, and what to do with one are not part of
  it.
- **cases:**
  - `shared-vendor`: the agent's answer names only a vendor that hosts two parts
  - `cross-part`: on a shared vendor, a setting on one part that holds the other part's address
  - `db-details`: a setting that needs the database's connection details
  - `host-sets`: a value nobody enters, because a host sets it

### `c-spot-secret`

- **goal:** tell whether a value an agent asks for is a secret
- **criterion:** Given a setting an agent asks for and its explanation of what the value is, says
  whether the value is a secret and why: someone holding it could get into something of yours.
  It passes when they call a secret one, including one whose name doesn't say so, such as a
  token or a connection string, and don't call a public value one, such as the frontend's or the
  backend's address. What to do with a secret is not part of it.
- **cases:**
  - `calls-secret`: a secret, including one whose name doesn't say so, called a secret
  - `calls-public`: a public value, such as an address, not called a secret
- **capability:** handle-secrets

### `c-judge-secret-request`

- **goal:** tell whether an agent's request would send a secret through the chat or into the code
- **criterion:** Given one message from an agent deploying an app, which asks for a value or
  proposes a step, says whether they would go along with it. It passes when they decline a
  request that would put a secret in the chat or let the agent write one into a file, and go
  along with one that wouldn't, including an instruction to put a secret into the host's
  settings themselves. What to do instead is not part of it.
- **cases:**
  - `declines-chat`: a request that would put a secret in the chat
  - `declines-file`: a request that would let the agent write a secret into a file
  - `allows-safe`: a request involving no secret
  - `allows-dashboard`: an instruction to put a secret into the host's settings themselves
- **capability:** handle-secrets

### `c-secret-instead`

- **goal:** say what to do instead of handing a secret to the agent, and why
- **criterion:** Given a message from an agent that would route a secret through the chat or
  into a file, says what they would do instead and why. It passes when they say to put the
  secret into the host's settings themselves and tell the agent it is there, and give both
  reasons: the chat is kept and can be shared, and an agent holding the secret can write it into
  a file that gets committed. Dealing with a secret that has already leaked is not part of it.
- **capability:** handle-secrets

### `w-config`

- **goal:** config
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the values that differ depending on where the app runs
- **nearest confusable:** code
- **synonyms:** configuration, settings

### `w-env-var`

- **goal:** environment variable
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a named value handed to the running program from outside its code
- **nearest confusable:** a setting written into the code
- **synonyms:** env var

### `w-port`

- **goal:** port
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the number after the colon that says which program on a machine a request is for
- **nearest confusable:** the host name

### `w-connection-string`

- **goal:** connection string
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** one line telling the backend where the database is and how to get in
- **nearest confusable:** a database file path; the database's password
- **synonyms:** database URL, DATABASE_URL

### `w-origin`

- **goal:** origin
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** where a page was loaded from, down to the port
- **nearest confusable:** domain; a full URL

### `w-cors`

- **goal:** CORS
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the browser's check on which other origins a page may call
- **nearest confusable:** a server error; a server's own access control
- **synonyms:** cross-origin resource sharing

### `w-secret`

- **goal:** secret
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a value that lets whoever holds it into something of yours
- **nearest confusable:** a setting; an environment variable
- **synonyms:** credential
