# Key: judge-plan-coverage

**For the tutor only.** Used by `a-judge-plan-coverage`. Never show this file to the learner; the learner's copy is `judge-plan-coverage.md`.

Show the learner the task file's header and the one plan being served, and none of this file.
Take the learner's answer and rule before commenting. Each row is one bank item.

| plan | case |
| ---- | ---- |
| q1 | clean split |
| q2 | mismatch (Express on a files-only host) |
| q3 | backend serves the frontend |
| q4 | mismatch (Express on a short-functions host) |
| q5 | one vendor hosts both |
| q6 | gap (frontend) |
| q8 | decoy: functions host used only for files |
| q10 | backend serves the frontend, and the frontend hosted twice |
| q11 | gap (backend left on a laptop) |
| q12 | mismatch inside one vendor hosting both |
| q13 | backend serves the frontend, on a host that can't run the backend |

`q7` and `q9` were about the database and have been dropped; their ids are not reused.

| plan | verdict | what decides it |
| ---- | ------- | --------------- |
| q1 | both covered | The usual split: a static host for the built files, a server host for the backend. |
| q2 | mismatch | Brightpage runs no code, so it cannot run the Express server. The frontend is fine. |
| q3 | both covered | One vendor, one host, both parts. The backend serves the built frontend itself, so no static host is needed. A learner who calls the missing static host a gap has missed the clause the criterion names. Its partner is q6. |
| q4 | mismatch | Spark keeps no program running between requests, so the Express server as written (a program that listens all the time) cannot run there without being rewritten as functions. The frontend on Brightpage is fine. Its partner is q8. |
| q5 | both covered | One vendor hosting both parts as two services. Same coverage as q1 under one account. Its partner is q12. |
| q6 | gap | The frontend's code runs in the browser, but the browser has to get the files from somewhere. Nothing sends them: no static host, and the server doesn't serve `dist`. Its partner is q3. |
| q8 | both covered | Spark can host a folder of files, which is all the frontend needs. Spark's limits matter only for a backend, and the backend is on Kettle. A learner who flags Spark here is judging the vendor rather than the job it was given. Its partner is q4. |
| q10 | both covered | The frontend is hosted twice. Wasteful, perhaps confusing, but not a gap and not a mismatch. A learner who names it as a problem has named something that isn't one. |
| q11 | gap | A server on the learner's laptop is not reachable from visitors' browsers and is off whenever the laptop is, so the backend has no host. The frontend is fine. |
| q12 | mismatch | Harbor can host both, but this plan puts the Express server's code in a static site, which only sends files as they are. The fault is in the job given, not the vendor. Its partner is q5. |
| q13 | mismatch, and the frontend not served either | Spark keeps no program running, so the Express server can't run there; and since the server is what sends the built frontend, the frontend isn't served either. The answer must say both. Its partner is q3. |

Pairs that answer each other, for the tutor's question "how does this one differ from the one you
did before?": q3 and q6 (does anything send the frontend's files?), q4 and q8 (the same functions
host, given a different job), q5 and q12 (the same vendor, a different service for the server), q1
and q5 (the same coverage, one account or two), q3 and q13 (the same arrangement, a host that can't
run it). Ask it on the second of the pair, only when the
first has already been served.

If the learner raises where the database goes, say it belongs to the database-hosting topic and
leave it out here.

The rule the learner should arrive at: list what each part needs (files sent as they are; a
program kept running), then check each vendor's offer against the part it was given, counting a
part as hosted wherever it is served from, even if by another part.
