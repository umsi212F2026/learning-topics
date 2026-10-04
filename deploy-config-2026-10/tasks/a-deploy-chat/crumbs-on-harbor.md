Crumbs is a recipe-sharing app shaped like your Problem Set 2 app: a React frontend, an Express
backend, and a database. It is being deployed on two made-up vendors:

- **Harbor** hosts both the frontend and the backend. It offers two things under one account: a
  static site, which sends a folder of files to anyone who asks, and a web service, which runs one
  program of yours all the time. Each gets its own address: the static site at
  `https://crumbs.harbor.app`, and the web service at `https://crumbs-k3x9.harbor.app`.
- **Larder** hosts the database. It keeps a Postgres database running for you, and its dashboard
  shows what the backend needs to reach it.

The questions follow the deploy in order. Some show an exchange in which the agent deploying
Crumbs asked for a setting, a student asked about it, and the agent answered. Others show a
message from the agent. Answer in two or three sentences, except where a question asks for the
reply you would send: then write the reply, and after it a sentence or two on why.

### q1

**Agent:** Next, please set `REMOTE_URL`.

**Student:** What is that for, and where does its value come from?

**Agent:** The React app sends its requests here. Use your Harbor address.

What is `REMOTE_URL` for? Whose value does it need: the frontend's address, the backend's address,
the database's connection details, or nobody's, because a host sets it? And is its value a
secret? Say why.

### q2

**Agent:** Now set `PERMIT_HOST`.

**Student:** Sorry, what's that one, and what do I put in it?

**Agent:** The Express server turns away any request that doesn't come from pages loaded from this
address, so other sites can't use your recipes. Use your Harbor address.

What is `PERMIT_HOST` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q3

**Agent:** The server also needs `LARDER_LINK`.

**Student:** What is that for, and where does its value come from?

**Agent:** The server uses it to get into your database. Copy the connection string from Larder's
dashboard.

What is `LARDER_LINK` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q4

**Agent:** Paste the address Harbor gave your static site here, and I'll set `PERMIT_HOST` on the
web service so it accepts requests from your pages.

Would you go along with this? Say why or why not.

### q5

**Agent:** The web service can't reach the database yet. Run `larder info` in your terminal, which
prints everything the backend needs to reach your database, and paste the output here so I can
check which region it's in.

Would you go along with this? Say why or why not.

### q6

**Agent:** Next I'll change the web service's start command on Harbor so it creates the recipes
table in your Larder database before it starts, then redeploy. OK to go ahead?

Would you go along with this? Say why or why not.

### q7

**Agent:** Your seed script, which loads the starter recipes, runs on your laptop too. I'll read
the connection string with Larder's command-line tool myself and write it at the top of
`server/seed.js`, so the script can reach the Larder database from anywhere. Want me to go ahead?

Would you go along with this? Say why or why not.

### q8

**Agent:** Last thing for the database: paste the connection string from Larder's dashboard here,
and I'll save it on the web service as `LARDER_LINK`.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.

### q9

**Agent:** Harbor runs your tests before each deploy of the web service, and I'd like them to run
against the real database. I'll read the connection string
with Larder's command-line tool and put it in `server/tests/db.test.js`, so the tests connect
without any setup.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.

### q10

**Agent:** The web service's logs say the database refused it. Open the settings page for your web
service on Harbor's dashboard and send me a screenshot, so I can check `LARDER_LINK` was saved
without a stray space.

This message would put a secret where it shouldn't go. Write the reply you would send the agent,
then say why that is safer. There may be more than one reason.
