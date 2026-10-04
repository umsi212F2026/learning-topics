Crumbs is a recipe-sharing app shaped like your Problem Set 2 app: a React frontend, an Express
backend, and a database. It is being deployed on three made-up vendors:

- **Brightpage** hosts the frontend. It hosts a folder of files and sends them to anyone who asks,
  and gives each site an address such as `https://crumbs.brightpage.app`.
- **Kettle** hosts the backend. It runs one program of yours, such as an Express server, all the
  time, and gives each service an address such as `https://crumbs-api.kettle.run`. Its dashboard
  has a page where you can add settings for your server.
- **Larder** hosts the database. It keeps a Postgres database running for you, and its
  dashboard's Connect page shows what the backend needs to reach it.

The questions follow the deploy in order. Some show an exchange in which the agent asked for a
setting, a student asked about it, and the agent answered. Others show a message from the agent.
Answer in two or three sentences.

### q1

**Agent:** Next, please set `FRONTEND_API_URL`.

**Student:** What is that for, and where does its value come from?

**Agent:** The React app sends every request for recipes to this address. Use the address
Kettle gave your service.

What is `FRONTEND_API_URL` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q2

**Agent:** Now set `CLIENT_ORIGIN`.

**Student:** What is that for, and where does its value come from?

**Agent:** The server only answers requests from pages loaded from this address, so that other
sites can't use your API. Set it to your Brightpage address.

What is `CLIENT_ORIGIN` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q3

**Agent:** The server also needs `PG_CONNECTION`.

**Student:** What is that for, and where does its value come from?

**Agent:** This is how the server gets into the database: its connection string, with the login
it needs. Copy it from the Connect page on Larder's dashboard.

What is `PG_CONNECTION` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q4

**Agent:** You'll see `LISTEN_ON` mentioned in the server code.

**Student:** What is that for, and where does its value come from?

**Agent:** It's the port number your server listens on for requests. You don't need to add this
one: Kettle sets it when it starts your server.

What is `LISTEN_ON` for? Whose value does it need: the frontend's address, the backend's address,
the database's connection details, or nobody's, because a host sets it? And is its value a
secret? Say why.

### q5

**Agent:** One more for the server: `LARDER_TOKEN`.

**Student:** What is that for, and where does its value come from?

**Agent:** The server sends this along with every request to the database, to prove it's allowed
in. Copy it from the Larder dashboard, next to the connection string.

What is `LARDER_TOKEN` for? Whose value does it need: the frontend's address, the backend's
address, the database's connection details, or nobody's, because a host sets it? And is its value
a secret? Say why.

### q6

**Agent:** To finish setting up the database, paste your Larder connection string here and I'll
add it to the server's settings as `PG_CONNECTION`.

Would you go along with this? Say why or why not.

### q7

**Agent:** Paste the address Kettle gave your server here, and I'll set `FRONTEND_API_URL` so the
frontend knows where to send requests.

Would you go along with this? Say why or why not.

### q8

**Agent:** In Kettle's dashboard, open your service's settings, add one called `PG_CONNECTION`,
and paste in the connection string from Larder. Tell me when it's done and I'll redeploy.

Would you go along with this? Say why or why not.

### q9

**Agent:** I can read the connection string through Larder's command-line tool myself and put it
straight into `server/config.js`, so it works the same on your laptop and on Kettle. Want me to go
ahead?

Would you go along with this? Say why or why not.

### q10

**Agent:** The server can't reach the database yet. Copy everything on Larder's Connect page and
paste it here, so I can check the format.

Would you go along with this? Say why or why not.

### q11

**Agent:** Paste your Brightpage site's address here and I'll set `CLIENT_ORIGIN` on the server,
so it accepts requests from your pages.

Would you go along with this? Say why or why not.
