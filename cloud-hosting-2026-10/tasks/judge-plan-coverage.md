# Judge a hosting plan for one app

**Used by:** `a-judge-plan-coverage`, which serves `c-place-app-parts`. A study activity: nothing
here can meet the goal. A bank of ten plans, `q1` to `q10`: each sitting shows the sections
above the line and one plan below it. The key is in `judge-plan-coverage-key.md`, for the tutor.

## The app

Crumbs is a recipe-sharing app with three parts, the same shape as your Problem Set 2 app:

- **The frontend:** a React app made with Vite. Before it goes anywhere it is built (`npm run
  build`), which turns it into a folder of plain files, `dist/`: one HTML page, some JavaScript and
  some CSS. Those files run in the visitor's browser, not on any host.
- **The backend:** an Express server. It has to be running all the time, listening for requests,
  so that it can answer the frontend's requests for recipes and save new ones.
- **The database:** SQLite. The whole database is one file, `crumbs.db`, which the Express server
  opens and writes to directly. Nothing else can open it: there is no database server to connect
  to, only a file on the same machine as the backend.

## The vendors

These vendors are made up, so that nothing here goes out of date. Each says what it offers, and
that is all you know about it.

- **Brightpage:** hosts a folder of files and sends them, as they are, to anyone who asks. Runs no
  code of yours.
- **Kettle:** runs one program of yours (such as a Node server) all the time, with a disk the
  program can read and write.
- **Ledger:** a hosted Postgres database. Your server connects to it over the internet with a
  connection string. Ledger runs only Postgres.
- **Spark:** hosts a folder of files the way Brightpage does, and also runs short functions: each
  request starts a fresh copy of a function, which answers and stops. It never keeps a program
  running between requests, and it has no disk that lasts from one request to the next.
- **Harbor:** offers three things under one account: static sites (like Brightpage), web services
  (like Kettle, with a disk), and hosted Postgres databases (like Ledger).

## For the plan you are given, answer

Which part does each vendor in the plan host? Then: is any part left without a host, or put on a
host that cannot run it as the app is now? Or is every part covered? Name every gap and mismatch,
and nothing that isn't one.

Then say, in a sentence, the rule you judged by.

---

### q1

> Brightpage for the frontend's built files. Kettle for the Express server, with `crumbs.db` on
> Kettle's disk.

### q2

> Brightpage for the frontend and the backend.

### q3

> Kettle runs the Express server, and the server also sends the frontend's built files itself
> (`express.static('dist')`). `crumbs.db` sits on Kettle's disk.

### q4

> Brightpage for the frontend, Spark for the Express server, Ledger for the database.

### q5

> Harbor for everything: a static site for the frontend and a web service for the Express server,
> with `crumbs.db` on the web service's disk.

### q6

> Kettle for the Express server, with `crumbs.db` on its disk. The frontend doesn't need a host,
> because it runs in the browser.

### q7

> Brightpage for the frontend and Kettle for the Express server. The database stays on my laptop,
> where it already is.

### q8

> Spark for the frontend's built files, Kettle for the Express server, with `crumbs.db` on Kettle's
> disk.

### q9

> My agent has switched Crumbs from SQLite to Postgres. Brightpage for the frontend, Kettle for the
> Express server, Ledger for the Postgres database.

### q10

> Kettle runs the Express server and sends the built frontend with `express.static('dist')`, with
> `crumbs.db` on Kettle's disk. I'll also put the built frontend on Brightpage.
