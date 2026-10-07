Answer each question in two to four sentences.

Clubhop is a club sign-up sheet for one university's students. A student picks a club from the
list and signs up for it, and each club's leader sees who has signed up. The React frontend is in
`client/` and the Express backend in `server/`, both in one GitHub repository,
`clubhop-campus/sheet`. The frontend is hosted on Pinecart, the backend on Ropewalk, and the
Postgres database on Cellarstone.

The database has two tables. `clubs` holds the clubs the app opens with, one row for each club
the student union recognizes, with its name, its meeting time and its leader. `signups` holds the
sign-ups students add, one row each, with the club, the student's name and their email.

The pipeline is already working. Ropewalk is linked to `clubhop-campus/sheet`, branch `main`,
folder `server/`, with "Wait for GitHub checks" on. A GitHub Actions workflow runs `npm test` in
`client/` and in `server/` on every push, against a Postgres database started inside the GitHub
Actions run for the tests alone, not a Cellarstone database. The backend reads production's
connection string, `CLUBHOP_DB`, from Ropewalk's Settings page. Clubhop has been live for some
weeks: production already has both tables and all the clubs, and students have added hundreds of
sign-ups.

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

1. I'll keep the definitions of `clubs` and `signups` in `server/db/schema.sql`, and the list of
   clubs in `server/db/clubs.json`, both in the repository.
2. Each time the backend starts, before it listens for requests, it will run `DROP TABLE` and then
   `CREATE TABLE` for `signups` and `clubs` from `schema.sql`, and then load the clubs from
   `clubs.json` into `clubs`, so the tables always match the code.
3. The backend will keep reading the connection string from `CLUBHOP_DB` on Ropewalk's Settings
   page.
4. I'll add a test, run by `npm test` in `server/`, that checks the tables have every column the
   backend's routes use.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q2

You asked the agent to add a phone number to each sign-up, so a club's leader can text the
students who signed up. The agent proposes:

1. As now, each time the backend starts it runs `CREATE TABLE IF NOT EXISTS` for `clubs` and
   `signups`, and the clubs are already in production, so nothing about them changes.
2. I'll add a phone field to the sign-up form in `client/`, and send it with each sign-up.
3. In `server/`, the sign-up route will save the number in a new `phone` column, and the leader's
   list will show it.
4. I'll add `phone text` to the `signups` table in the backend's `CREATE TABLE IF NOT EXISTS`
   statement, so the table has the column the route uses.
5. I'll add tests for saving and listing a phone number, and check that they pass.
6. I'll push to `main`, and Ropewalk will deploy it once the checks pass.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q3

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. The agent proposes:

1. Each time the backend starts, it will run `CREATE TABLE IF NOT EXISTS` for `clubs` and
   `signups`.
2. The clubs will go in from a seed script kept in the repository, `server/db/seed.js`, which
   inserts them into `clubs`. It is run by hand, and only on a fresh database. Production already
   ran it once when Clubhop launched, so it won't be run there again.
3. A change to the tables will be written as a migration file in `server/db/migrations/`, such as
   `002-add-signup-phone.sql`, kept in the repository.
4. I'll add a migration script, `server/db/migrate.js`, and set `node db/migrate.js` as Ropewalk's
   pre-deploy command. On each deploy it first creates any tables that are missing, then applies,
   in order, each migration file not yet applied, and records it in a `migrations` table.
5. The backend and the migration script both read the connection string from `CLUBHOP_DB` on
   Ropewalk's Settings page.

Would you go along with this plan?

### q4

Suppose the agent has carried out plan 3, says everything is set up, and Ropewalk's deploy list
shows the latest deploy as Live.

How would you make sure that a push to `main` now leaves production's data in place?
