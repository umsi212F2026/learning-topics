Answer each question in two or three sentences.

Forkcast is the dish-rating app for Linden Hall, a university dining hall. The menu page lists the
dishes the hall serves, and a student rates a dish they ate, from one to five stars, with a short
comment. The React frontend is in `client/` and the Express backend in `server/`, both in one
GitHub repository, `linden-dining/forkcast`. The frontend is hosted on Pinecart, the backend on
Ropewalk, and the Postgres database on Cellarstone. How the frontend deploys is not part of these
questions.

The database has two tables. `dishes` holds the hall's 40 regular dishes, each with its name and
its station (grill, soup, salad bar and so on); these are the rows the app is meant to open with.
`ratings` holds the ratings students add, one row each, with the dish, the student's name, the
stars and the comment.

The pipeline already works. Ropewalk is linked to `linden-dining/forkcast`, branch `main`, folder
`server/`, with "Wait for GitHub checks" on. A GitHub Actions workflow runs `npm test` in `client/`
and in `server/` on every push, against a Postgres database started inside the GitHub Actions run
for the tests alone, not a Cellarstone database. The backend reads production's connection string,
`FORKCAST_DB`, from Ropewalk's settings. Forkcast has been live for some weeks: production already
has its tables and the hall's 40 dishes, and students have added more than a thousand ratings.

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

Each question below is an account an agent gave, in a different session, of work it did on
Forkcast's production database. Read each one on its own.

### q1

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code. Here's what it told you:

1. I kept the backend's startup code in `server/db/setup.js`, which runs `CREATE TABLE IF NOT
   EXISTS` for `dishes` and for `ratings` each time the server starts, which creates each table
   only if it isn't there yet.
2. I moved the hall's 40 dishes into `server/db/dishes.sql`, so the list of dishes lives in the
   repository.
3. Right after creating the tables, the startup code now runs `dishes.sql`, which inserts the 40
   dishes into `dishes`, adding each one as a new row, so a fresh database gets them too.
4. I pushed this to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.
5. I opened the live app, and the menu page now lists each of the 40 dishes twice. The ratings are
   all still there. I'll tidy the duplicates by hand in Cellarstone's query console.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q2

You had another agent add a way for students to mark a rating as helpful. Once that was pushed and
deployed, the live menu page showed an error, "column `helpful_count` does not exist", and you
asked this agent to fix it. Here's what it told you:

1. I opened the live app and saw the error. The new code reads a `helpful_count` column on
   `ratings`, and production's `ratings` table doesn't have one.
2. I wrote `server/db/rebuild-ratings.js`. It runs `DROP TABLE ratings`, which deletes the table
   and every row in it, and then `CREATE TABLE ratings` with the same columns as before plus
   `helpful_count`, which creates the table again, with the new column.
3. I ran `node db/rebuild-ratings.js` once against production's database.
4. I opened the live app again, and the menu page loads. The error is gone.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q3

You asked the agent to rework how the backend sets up and changes its database, so setting it up
and changing it is all in the code, and to check afterwards that production's data is kept. Here's
what it told you:

1. I kept the backend's startup code in `server/db/setup.js`, which runs `CREATE TABLE IF NOT
   EXISTS` for `dishes` and for `ratings` each time the server starts, which creates each table
   only if it isn't there yet.
2. The hall's 40 dishes are in `server/db/dishes.sql`. Right after creating the tables, the startup
   code inserts them with `INSERT ... WHERE NOT EXISTS`, which adds a dish only if no dish with
   that name is already in `dishes`. On production, which already has all 40, it adds nothing; on
   a fresh database it adds all 40. It never touches `ratings`.
3. A change to the tables is now written as a migration file in `server/migrations/`. I set
   `node db/migrate.js` as Ropewalk's pre-deploy command. It first creates any tables that are
   missing, then applies each migration file not yet applied, and records it.
4. I pushed this to `main`. The checks passed, and Ropewalk's deploy list shows the deploy as Live.
5. To check that production's data is kept, I counted the rows in `ratings` in Cellarstone's query
   console: 1,212. Then I pushed a one-line change to a comment in `server/index.js` to `main`.
   While Ropewalk's deploy list showed that push's deploy as Building, I counted again and found
   1,212. The data handling is confirmed.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?

### q4

You asked the agent to let a student say which meal (breakfast, lunch or dinner) they ate a dish
at, and to check afterwards that production's data is kept. Here's what it told you:

1. The backend's startup code in `server/db/setup.js` runs `CREATE TABLE IF NOT EXISTS` for
   `dishes` and for `ratings` each time the server starts, which creates each table only if it
   isn't there yet. The hall's 40 dishes are loaded by `server/db/seed.js`, kept in the
   repository. Production already ran it once, when Forkcast went live. It is run only on a fresh
   database, and nothing in the start command or the pre-deploy command runs it.
2. I added a meal choice to the rating form, and to the backend route that saves a rating.
3. I wrote a migration file, `server/migrations/004_add_meal_to_ratings.sql`. It runs `ALTER
   TABLE ratings ADD COLUMN meal TEXT`, which adds an empty `meal` column to the existing
   `ratings` table and keeps every rating already in it. Ratings from before the change have no
   meal, and the menu page shows them without one.
4. Ropewalk's pre-deploy command is `node db/migrate.js`. It first creates any tables that are
   missing, then applies each migration file not yet applied, and records it, so `004` is applied
   once, on the deploy of this version, before the new code replaces the running one.
5. I added tests for the meal. Before they run, the server's tests run `db/migrate.js` against
   their fresh database. `npm test` passes in `client/` and in `server/`.
6. Before pushing, I rated Lentil Soup in the live app, under the name Test Diner. I pushed to
   `main`, the checks passed, and I waited until Ropewalk's deploy list showed that push's deploy
   as Live.
7. Then I opened the live app: Test Diner's rating of Lentil Soup is still there, the menu page
   lists the 40 dishes, each once, and a new rating can now say which meal it was.

Would you have accepted this? If a step goes wrong, which one, and what should have happened
instead?
