Answer each question in two to four sentences.

Shedshare is the tool-lending list of the Elm Street neighbourhood association, which keeps a shed
of tools its members can borrow. A member finds a tool in the list and records a loan when they
take it, and the volunteer who runs the shed sees what is out and who has it. The React frontend
is in `client/` and the Express backend in `server/`, both in one GitHub repository,
`elm-street/shedshare`. The frontend is hosted on Pinecart, the backend on Ropewalk, and the
Postgres database on Cellarstone.

The database has two tables. `tools` holds the tools the app opens with, one row for each tool in
the shed, with its name, its shelf and any notes on using it. `loans` holds the loans members
record, one row each, with the tool, the member's name and the day they took it.

The pipeline is already working. Ropewalk is linked to `elm-street/shedshare`, branch `main`,
folder `server/`, with "Wait for GitHub checks" on. A GitHub Actions workflow runs `npm test` in
`client/` and in `server/` on every push, against a Postgres database started inside the GitHub
Actions run for the tests alone, not a Cellarstone database. The backend reads production's
connection string, `SHEDSHARE_DB`, from Ropewalk's Settings page. Shedshare has been live for some
weeks: production already has both tables and every tool in the shed, and members have recorded
over a hundred loans.

This is how Ropewalk and Cellarstone behave:

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

The agent proposed each plan below in a different session. Each question is about its own plan
alone.

### q1

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. The agent proposes:

1. I'll keep the list of tools in `server/db/tools.json`, in the repository, so the shed's
   volunteer can add a tool with a pull request.
2. Each time the backend starts, before it listens for requests, it will run `CREATE TABLE IF NOT
   EXISTS` for `tools` and `loans`, which creates each table only if it isn't there yet.
3. Then it will add every tool listed in `tools.json` to `tools`, each as a new row, so the list
   in the app is never missing a tool.
4. The backend will keep reading the connection string from `SHEDSHARE_DB` on Ropewalk's Settings
   page.
5. I'll add a test, run by `npm test` in `server/`, that starts the backend against an empty
   database and checks that every tool in `tools.json` is listed.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q2

A while ago you asked the agent to add a due date to each loan, so the shed's volunteer can see
which tools are late coming back. It pushed the change, Ropewalk deployed it, and now the live app
shows an error whenever a member records a loan: "column `due_date` does not exist". You ask the
agent to fix it. The agent proposes:

1. As now, each time the backend starts it runs `CREATE TABLE IF NOT EXISTS` for `tools` and
   `loans`, which creates each table only if it isn't there yet. Its statement for `loans`
   already has the `due_date` column, and the tests pass.
2. I'll write a script, `server/db/rebuild-loans.js`. It drops `loans`, which deletes the table
   and every row in it, and then creates it again with every column the code uses, `due_date`
   included, so the table matches the code.
3. I'll set `node db/rebuild-loans.js` as Ropewalk's pre-deploy command, and push to `main`, so
   the script runs on the next deploy before the new version replaces the running one.
4. The script reads the connection string from `SHEDSHARE_DB` on Ropewalk's Settings page, like
   the backend.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q3

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. The agent proposes:

1. Each time the backend starts, it will run `CREATE TABLE IF NOT EXISTS` for `tools` and `loans`,
   which creates each table only if it isn't there yet.
2. The tools will go in from a seed script kept in the repository, `server/db/seed.js`, which
   inserts them into `tools`. It is run by hand, and only on a fresh database. Production already
   ran it once when Shedshare launched, so it won't be run there again.
3. A change to the tables will be written as a migration file in `server/db/migrations/`,
   numbered in order (`001-...sql`, `002-...sql`) and kept in the repository.
4. I'll add a migration script, `server/db/migrate.js`, and set `node db/migrate.js` as
   Ropewalk's pre-deploy command. On each deploy it first creates any tables that are missing,
   then applies, in order, each migration file not yet applied, and records it in a `migrations`
   table.
5. The backend and the migration script both read the connection string from `SHEDSHARE_DB` on
   Ropewalk's Settings page.

Would you go along with this plan?

### q4

Suppose the agent has carried out plan 3, says everything is set up, and Ropewalk's deploy list
shows the latest deploy as Live.

How would you make sure that a push to `main` now leaves production's data in place?
