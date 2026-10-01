# Judge ten hosting plans for one app

**Used by:** `a-judge-plan-coverage`, which serves `c-place-app-parts`. A study activity: nothing
here can meet the goal.

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

## For each plan, answer

Which part does each vendor in the plan host? Then: is any part left without a host, or put on a
host that cannot run it as the app is now? Or is every part covered? Name every gap and mismatch,
and nothing that isn't one.

When you have done all ten, state the rule you judged by, in one or two sentences.

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

---

## Key, for the tutor

Show the learner everything above this section, not this section. Take all ten answers and the
rule before commenting on any.

| plan | verdict | what decides it |
| ---- | ------- | --------------- |
| q1 | every part covered | The usual split: a static host for the built files, a server host for the backend, and the SQLite file on the server host's disk, which is the only place SQLite can live. |
| q2 | mismatch and gap | Brightpage runs no code, so it cannot run the Express server (mismatch). Nothing hosts the database, and with no running server there is nothing to open the file anyway (gap). The frontend is fine. |
| q3 | every part covered | One vendor, one host, three parts. The backend serves the built frontend itself, so no static host is needed. A learner who calls the missing static host a gap has missed the clause the criterion names. |
| q4 | two mismatches | Spark keeps no program running between requests, so the Express server as written (a program that listens all the time) cannot run there without being rewritten as functions. Ledger runs only Postgres, and the app's database is a SQLite file, so the database is on a host that cannot run it as the app is now. Compare with q9. The frontend on Brightpage is fine. |
| q5 | every part covered | One vendor hosting two parts as two services, and the SQLite file on the web service's disk. Same coverage as q1 under one account. |
| q6 | gap | The frontend's code runs in the browser, but the browser has to get the files from somewhere. Nothing sends them: no static host, and the server doesn't serve `dist`. Compare with q3. |
| q7 | gap | The hosted server on Kettle cannot open a file on the learner's laptop, and the laptop isn't always on. The database has no host. |
| q8 | every part covered | Spark can host a folder of files, which is all the frontend needs. Spark's limits matter only for the backend, and the backend is on Kettle. A learner who flags Spark here is judging the vendor rather than the job it was given. |
| q9 | every part covered | The same vendors as q4 for the database, but the app now uses Postgres, so Ledger can run it. The point of comparing with q4: whether a host fits depends on what the part is, and changing the part can change the answer. |
| q10 | every part covered | The frontend is hosted twice. Wasteful, perhaps confusing, but not a gap and not a mismatch. A learner who names it as a problem has named something that isn't one. |

Make sure q3 against q6, q4 against q9, and q8 are discussed whatever the learner answered.

On the SQLite file in q1, q3, q5, q8 and q10: whether a host's disk keeps that file through
restarts and redeploys is a real question (on many free plans it does not), but it belongs to the
topic on keeping the hosted database's data safe, not this one. If the learner raises it, say so,
say it is a good question, and count the file on the server host's disk as hosted for this
exercise.

The rule the learner should arrive at: list what each part needs (files sent as they are; a
program kept running; a database the app can actually use as it is now), then check each vendor's
offer against the part it was given, counting a part as hosted wherever it is served from, even if
by another part.
