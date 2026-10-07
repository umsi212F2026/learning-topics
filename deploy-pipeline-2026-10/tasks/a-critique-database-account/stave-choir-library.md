Answer each question in two or three sentences.

Stave is the music library app for the Northwood Community Choir. The library page lists every
piece of sheet music the choir owns, and a member checks out a copy of a piece to take home and
returns it later. The React frontend is in `client/` and the Express backend in `server/`, both in
one GitHub repository, `northwood-choir/stave`. The frontend is hosted on Pinecart, the backend on
Ropewalk, and the Postgres database on Cellarstone. How the frontend deploys is not part of these
questions.

The database has two tables. `scores` holds the choir's 64 pieces, each with its title, composer,
number of copies and a unique `catalog_number`; these are the rows the app is meant to open with.
`checkouts` holds the copies members have checked out.

The pipeline already works. Ropewalk is linked to `northwood-choir/stave`, branch `main`, folder
`server/`, with "Wait for GitHub checks" on. A GitHub Actions workflow runs `npm test` in `client/`
and in `server/` on every push, against a Postgres database started inside the GitHub Actions run
for the tests alone, not a Cellarstone database. The backend reads production's connection string,
`STAVE_DB`, from Ropewalk's settings. Stave has been live for some weeks: production already has
its tables and the choir's 64 pieces, and members have checked out copies of their own.

This is how the backend's host and the database's host behave:

- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Settings (environment variables) entered on the service's Settings page reach the running
    server and never the browser. Saving one restarts the server with the new value.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.
  - Every deploy, and every restart, starts the server afresh with the service's start command, so
    whatever the backend does when it starts runs again each time.
  - Each service can have a pre-deploy command. It runs once on each deploy, after the new version
    is built and before it replaces the running one, with the service's settings. If it fails, the
    deploy fails and the previous one stays live.
- **Cellarstone** hosts Postgres databases.
  - A database keeps its tables and rows across every deploy and restart of the backend that uses
    it: a deploy or a restart does not by itself change it. Only SQL sent to it changes its tables
    or rows: from the backend as it starts or runs, from a pre-deploy command or another script, or
    typed into Cellarstone's query console.
  - Each database has a connection string, which is a secret.

Each question below is an account an agent gave, in a different session, of work it did on Stave's
production database. Read each one on its own.

### q1

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. Here's what it told you:

1. I kept the backend's startup code in `server/db/setup.js`, which runs `CREATE TABLE IF NOT
   EXISTS` for `scores` and for `checkouts` each time the server starts, which creates each table
   only if it isn't there yet.
2. I moved the choir's 64 pieces into `server/db/scores.sql`, so the list of pieces lives in the
   repository.
3. I wrote `server/db/reset.js`, which empties `scores` and `checkouts` and then loads the pieces
   from `scores.sql`, and set `node db/reset.js` as Ropewalk's pre-deploy command, so production
   always starts clean.
4. I pushed this to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q2

You asked the agent to add a due date to each checkout, so members know when to bring a copy
back. Here's what it told you:

1. I added a due date to the checkout form, and to the backend route that saves a checkout.
2. I added a `due_date` column to the `CREATE TABLE IF NOT EXISTS checkouts` statement in
   `server/db/setup.js`, which the backend runs each time it starts and which creates `checkouts`
   only if it isn't there yet.
3. I added tests for the due date. `npm test` passes in `client/` and in `server/`.
4. I pushed to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.
5. The due date feature is done.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q3

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code, and to check afterwards that production's data is kept. Here's
what it told you:

1. I kept the backend's startup code in `server/db/setup.js`, which runs `CREATE TABLE IF NOT
   EXISTS` for `scores` and for `checkouts` each time the server starts, which creates each table
   only if it isn't there yet.
2. The choir's 64 pieces are loaded by `server/db/seed.js`, kept in the repository. Production
   already ran it once, when Stave went live. It is run only on a fresh database, and nothing in
   the start command or the pre-deploy command runs it.
3. A change to the tables is now written as a migration file in `server/migrations/`. I set
   `node db/migrate.js` as Ropewalk's pre-deploy command. It first creates any tables that are
   missing, then applies each migration file not yet applied, and records it.
4. I pushed this to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.
5. To check that production's data is kept, I saved `LOG_LEVEL` on Ropewalk's Settings page, which
   restarted the server. Then I opened the live app, and the library page lists all 64 pieces, as
   before. The data handling is confirmed.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q4

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code, and to check afterwards that production's data is kept. Here's
what it told you:

1. I kept the backend's startup code in `server/db/setup.js`, which runs `CREATE TABLE IF NOT
   EXISTS` for `scores` and for `checkouts` each time the server starts, which creates each table
   only if it isn't there yet.
2. The choir's 64 pieces are in `server/db/scores.sql`, each with its `catalog_number`. Right after
   creating the tables, the startup code inserts them with `INSERT INTO scores ... ON CONFLICT
   (catalog_number) DO NOTHING`. Since `catalog_number` is unique in `scores`, a piece whose number
   is already there is skipped. On production, which already has all 64, the insert adds nothing;
   on a fresh database it adds all 64. It never touches `checkouts`.
3. A change to the tables is now written as a migration file in `server/migrations/`. I set
   `node db/migrate.js` as Ropewalk's pre-deploy command. It first creates any tables that are
   missing, then applies each migration file not yet applied, and records it.
4. I pushed this to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.
5. To check that production's data is kept, I checked out a copy of "Locus Iste" in the live app,
   under the name Test Alto. I pushed a one-line change to a comment in
   `server/index.js` to `main` and waited until Ropewalk's deploy list showed that push's deploy as
   Live. Then I opened the live app: Test Alto's checkout is still there, and the library page
   lists the 64 pieces, each once.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?
