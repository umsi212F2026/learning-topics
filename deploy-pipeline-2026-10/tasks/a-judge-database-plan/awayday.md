Answer each question in two to four sentences.

Awayday is a ride board for Northfield FC, a youth soccer club. Parents see the season's away
games, offer rides to one, and take a seat in someone else's car. The React frontend is in
`client/` and the Express backend in `server/`, both in one GitHub repository,
`northfield-fc/awayday`. The frontend is hosted on Pinecart, the backend on Ropewalk, and the
Postgres database on Cellarstone.

The database has two tables. `games` holds the away games the app opens with, one row for each
game on the club's schedule for the season, with its opponent, its date and the field's address.
`rides` holds the rides parents offer, one row each, with the game, the driver's name, their phone
number and where they leave from.

The pipeline is already working. Ropewalk is linked to `northfield-fc/awayday`, branch `main`,
folder `server/`, with "Wait for GitHub checks" on. A GitHub Actions workflow runs `npm test` in
`client/` and in `server/` on every push, against a Postgres database started inside the GitHub
Actions run for the tests alone, not a Cellarstone database. The backend reads production's
connection string, `AWAYDAY_DB`, from Ropewalk's Settings page. Awayday has been live for some
weeks: production already has both tables and every game on the schedule, and parents have
offered dozens of rides.

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

1. I'll keep the season's schedule in `server/db/games.json`, in the repository, so the club's
   secretary can update it with a pull request.
2. I'll write a script, `server/db/reset.js`. It creates `games` and `rides` if they aren't there
   yet, then empties both tables, deleting every row in them, and loads the games from
   `games.json` into `games`, so every start begins from the same known state.
3. I'll set the service's start command on Ropewalk to `node db/reset.js && node index.js`, which
   runs `reset.js` and then, once it has finished, starts the server.
4. The backend will keep reading the connection string from `AWAYDAY_DB` on Ropewalk's Settings
   page.
5. I'll add a test, run by `npm test` in `server/`, that checks a ride can be offered for a game
   from `games.json`.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q2

You asked the agent to let a driver say how many seats they have free, so parents can see which
cars still have room. The agent proposes:

1. As now, each time the backend starts it runs `CREATE TABLE IF NOT EXISTS` for `games` and
   `rides`, which creates each table only if it isn't there yet, and the games are already in
   production, so nothing about them changes.
2. I'll add a seats field to the offer-a-ride form in `client/`, and show the number beside each
   ride.
3. In `server/`, the offer-a-ride route will save the number in a new `seats` column, and the
   list of rides for a game will return it.
4. I'll add a `seats` column to the `rides` table in that `CREATE TABLE IF NOT EXISTS` statement,
   so the table has the column the route uses.
5. I've added the `seats` column to the `rides` table in your local database, keeping its rows,
   so it works there too.
6. I'll add tests for offering a ride with seats and listing it, check that they pass, and push to
   `main`, and Ropewalk will deploy it once the checks pass.

Would you agree to this plan as it stands? If not, say what you would change before agreeing.

### q3

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. The agent proposes:

1. Each time the backend starts, it will run `CREATE TABLE IF NOT EXISTS` for `games` and `rides`,
   which creates each table only if it isn't there yet.
2. Then it will insert each game from `server/db/games.json`, every one with its own id, using
   `ON CONFLICT DO NOTHING`, which skips any game whose id is already in `games`. So each game
   goes in once, and a game added to the file later goes in on the next start.
3. A change to the tables will be written as a migration file in `server/db/migrations/`,
   numbered in order (`001-...sql`, `002-...sql`) and kept in the repository.
4. I'll add a migration script, `server/db/migrate.js`, and set `node db/migrate.js` as
   Ropewalk's pre-deploy command. On each deploy it first creates any tables that are missing,
   then applies, in order, each migration file not yet applied, and records it in a `migrations`
   table.
5. The backend and the migration script both read the connection string from `AWAYDAY_DB` on
   Ropewalk's Settings page.

Would you go along with this plan?

### q4

Suppose the agent has carried out plan 3, says everything is set up, and Ropewalk's deploy list
shows the latest deploy as Live.

How would you make sure that a push to `main` now leaves production's data in place?
