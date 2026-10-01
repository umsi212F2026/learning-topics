# Key: judge-plan-coverage

**For the tutor only.** Used by `a-judge-plan-coverage`. Never show this file to the learner; the learner's copy is `judge-plan-coverage.md`.

Show the learner the whole of the task file and none of this one. Take all ten answers and the
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
