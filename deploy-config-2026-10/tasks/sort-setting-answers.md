# Sort what an agent says about six settings

**Used by:** `a-sort-setting-answers`, which serves `c-place-settings`. A study activity: nothing
here can meet the goal. One sitting does the whole set. The key is in
`sort-setting-answers-key.md`, for the tutor.

## The app

Crumbs is a recipe-sharing app shaped like your Problem Set 2 app: a React frontend, an Express
backend, and a database. It is being deployed, each part on its own host.

## The vendors

These vendors are made up, so that nothing here goes out of date.

- **Brightpage:** hosts a folder of files and sends them to anyone who asks. It gives each site an
  address such as `https://crumbs.brightpage.app`.
- **Kettle:** runs one program of yours, such as an Express server, all the time. It gives each
  service an address such as `https://crumbs-api.kettle.run`, and it tells your program which port
  to listen on, through a setting called `PORT`.
- **Harbor:** offers two things under one account: static sites (like Brightpage) and web services
  (like Kettle). Each gets its own address.
- **Larder:** keeps a Postgres database running for you. Its dashboard shows a connection string
  for each database, which includes the database's password.

## The six exchanges

In each one, an agent deploying Crumbs asked for a setting, a student asked "What is this for, and
where does its value come from?", and the agent answered. Only the setting's name and the agent's
answer are shown.

1. **`FRONTEND_API_URL`.** "The React app sends every request for recipes to this address. Use the
   address Kettle gave your service."
2. **`CLIENT_ORIGIN`.** "The server only answers requests from pages loaded from this address, so
   that other sites can't use your API. Set it to your Brightpage address."
3. **`PG_CONNECTION`.** "This is how the server reaches the database. Copy it from Larder's
   dashboard."
4. **`PORT`.** "You don't need to add this one. Kettle sets it when it starts your server."
5. **`API_BASE`.** In this exchange Crumbs is on Harbor: its frontend as a static site and its
   backend as a web service. "The React app sends its requests here. Use your Harbor address."
6. **`LARDER_TOKEN`.** "The server sends this along with every request to the database, to prove
   it's allowed in. Copy it from the Larder dashboard, next to the connection string."

## Sort them

Put each setting in one of four groups, by whose value it needs:

- **the frontend's address**
- **the backend's address**
- **the database's connection details**
- **nobody's**, because a host sets it automatically

Then mark each one that is a secret.

Last, say in a sentence or two the rule you sorted by.
