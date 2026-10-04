Crumbs is a recipe-sharing app shaped like your Problem Set 2 app: a React frontend, an Express
backend, and a database. It is being deployed on three made-up vendors:

- **Brightpage** hosts the frontend. It hosts a folder of files and sends them to anyone who asks,
  and gives each site an address such as `https://crumbs.brightpage.app`.
- **Kettle** hosts the backend. It runs one program of yours, such as an Express server, all the
  time, and gives each service an address such as `https://crumbs-api.kettle.run`.
- **Larder** hosts the database. It keeps a Postgres database running for you, and its dashboard
  shows what the backend needs to reach it.

Each question shows an exchange in which the agent deploying Crumbs asked for a setting, a
student asked about it, and the agent answered. Answer in two or three sentences.

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

**Agent:** This is how the server reaches the database. Copy it from Larder's dashboard.

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
