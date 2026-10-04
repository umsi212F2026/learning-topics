Lendlist is a neighborhood tool-lending app shaped like your Problem Set 2 app: a React frontend,
an Express backend, and a database. It is being deployed on two made-up vendors:

- **Dockyard** hosts both the frontend and the backend. It offers two things under one account: a
  static site, which sends a folder of files to anyone who asks, and a web service, which runs one
  program of yours all the time. Each gets its own address: the static site at
  `https://lendlist.dockyard.app`, and the web service at `https://lendlist-r4tz.dockyard.app`.
  Each has a settings page on Dockyard's dashboard.
- **Silo** hosts the database. It keeps a Postgres database running for you, and its dashboard's
  Connect panel shows the connection string, login included, as one line.

The questions follow the deploy in order. Some show an exchange in which the agent asked for a
setting, a student asked about it, and the agent answered. Others show a message from the agent.
Answer in two or three sentences, except where a question asks for the reply you would send: then
write the reply, and after it a sentence or two on why.

### q1

**Agent:** Next, please set `FETCH_ROOT`.

**Student:** What's that one for, and where do I get the value?

**Agent:** The React app sends every request for listings and loans to this address. Use your
Dockyard address.

What is `FETCH_ROOT` for? Whose value does it need: the frontend's address, the backend's address,
the database's connection details, or nobody's, because a host sets it? And is its value a
secret? Say why.

### q2

**Agent:** Now set `SERVER_ALLOWS_FROM`.

**Student:** What does that do, and what should I put in it?

**Agent:** The server only answers requests that come from pages loaded from this address, so
other sites can't use it. Set it to your Dockyard address.

What is `SERVER_ALLOWS_FROM` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q3

**Agent:** The server also needs `SILO_URI`.

**Student:** What is that for, and where does its value come from?

**Agent:** The server uses it to get into your database: it says where the database is and holds
the login. Copy the line shown on the Connect panel of Silo's dashboard.

What is `SILO_URI` for? Whose value does it need: the frontend's address, the backend's address,
the database's connection details, or nobody's, because a host sets it? And is its value a
secret? Say why.

### q4

**Agent:** Paste the address Dockyard gave your web service here, and I'll set `FETCH_ROOT` so the
frontend knows where to send its requests.

Would you go along with this? Say why or why not.

### q5

**Agent:** The web service still can't reach the database. Take a screenshot of the Connect panel
on Silo's dashboard and drop it here, so I can check the host name is right.

Would you go along with this? Say why or why not.

### q6

**Agent:** I've changed the server so it reads the database's connection from `SILO_URI` in its
settings, instead of from the database file it used on your laptop. I'll commit that change and
redeploy the web service on Dockyard. OK to go ahead?

Would you go along with this? Say why or why not.

### q7

**Agent:** To save you a step, I can fetch the connection string with Silo's command-line tool
myself and put it in `server/db.js` as the fallback for when `SILO_URI` isn't set, so the app keeps
working even if a setting goes missing. Want me to go ahead?

Would you go along with this? Say why or why not.

### q8

**Agent:** Last thing for the database: paste the line from Silo's Connect panel here, and I'll add
it to the web service's settings as `SILO_URI`.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.

### q9

**Agent:** Dockyard reads a file called `dockyard.yaml` from your repo on every deploy. I'll fetch
the connection string with Silo's command-line tool and list it in that file under `SILO_URI`, so
it's set automatically each time you deploy.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.

### q10

**Agent:** The web service's logs say the database turned it away. Run `dockyard settings show` in
your terminal, which prints every setting on the web service, and paste the output here so I can
check what `SILO_URI` is set to.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.
