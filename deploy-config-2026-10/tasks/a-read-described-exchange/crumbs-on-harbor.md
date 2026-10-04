Crumbs is a recipe-sharing app shaped like your Problem Set 2 app: a React frontend, an Express
backend, and a database. It is being deployed on two made-up vendors:

- **Harbor** hosts both the frontend and the backend. It offers two things under one account: a
  static site, which sends a folder of files to anyone who asks, and a web service, which runs one
  program of yours all the time. Each gets its own address: the static site at
  `https://crumbs.harbor.app`, and the web service at `https://crumbs-k3x9.harbor.app`.
- **Larder** hosts the database. It keeps a Postgres database running for you, and its dashboard
  shows what the backend needs to reach it.

Each question shows an exchange in which the agent deploying Crumbs asked for a setting, a
student asked about it, and the agent answered. Answer in two or three sentences.

### q1

**Agent:** Next, please set `API_BASE`.

**Student:** What is that for, and where does its value come from?

**Agent:** The React app sends its requests here. Use your Harbor address.

What is `API_BASE` for? Whose value does it need: the frontend's address, the backend's address,
the database's connection details, or nobody's, because a host sets it? And is its value a
secret? Say why.
