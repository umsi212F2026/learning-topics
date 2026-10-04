**The app.** Crumbs, a recipe-sharing class project: a React frontend built with Vite and an
Express server. About twenty users, mostly in the week it is graded, which is the last week of the
month. Its owner works through a coding agent. Crumbs also has a database; where it is kept belongs
to the database-hosting topic and is left out here.

**Plan H, one vendor:** Harbor hosts the frontend (a static site) and the server (a web service).
**Plan S, a vendor for each:** Brightpage hosts the frontend, Kettle runs the server.

**Free-tier terms** (made-up vendors, modeled on real terms of 2026-10-01). No vendor needs a card
to sign up.

- **Harbor.** Static sites never sleep. The web service sleeps after 15 minutes without a request,
  and the next request waits about a minute; 750 free hours a month, then suspended. With a card
  on file, bandwidth past 100 GB a month is billed ($0.15 per GB); without one, services are
  suspended. One official CLI and MCP server for both parts: deploy, read logs, set environment
  variables; can't delete services or change plans. Builds with ordinary `npm`.
- **Brightpage.** Never sleeps. 100 GB a month, a hard cap: past it, paused until next month. The
  free plan takes no card, so it can't bill. A CLI that deploys and sets build settings; deploy
  logs only, since it runs no code. Any static host can take the files.
- **Kettle.** $1 of credit a month, enough to keep a small server running for about three weeks;
  never sleeps. When the credit runs out the server stops until next month, or, with a card on
  file, keeps running and bills. Official CLI and MCP server: deploy, read logs, set environment
  variables. Reads a small `kettle.toml`; the server is ordinary Node.

Answer from these terms only. Which plan anyone chooses is never what is judged.

### v1

Make the call yourself. Choose Plan H or Plan S and say why: name each difference in the terms
that would matter for this app, say what Plan S's extra vendor adds in accounts, secrets and places
to look when something breaks, and state the strongest case for the plan you didn't choose.

### v2

A student chose Plan S and wrote: "A grader opening Crumbs after a quiet spell would wait a minute
on Harbor; Kettle never sleeps. Kettle's credit only lasts about three weeks, so I'd need it to
cover grading week, or put a card on and accept it bills." Give the strongest case for Plan H, the
plan they didn't choose, using only the terms.

### v3

A student wrote: "Plan H, because it's free forever and Harbor never charges anything. The other
plan has two accounts, which is more to manage." Which of their claims do the terms not support,
and what do the terms say instead?

### v4

A student wrote: "Plan S. Nothing sleeps, and Brightpage can't bill me. Harbor's server sleeps
after 15 minutes. Kettle's credit runs out after about three weeks; if I keep a card off it, the
worst case is the server stopping until next month. Moving is easy from either. The strongest case
for H is that it's one account." What does Plan S's extra vendor cost that this student left out?

### v5

A student wrote: "Plan S, because two specialized vendors will be faster under load and more
reliable than one that does everything, and Kettle is more secure since it runs only one program. Harbor
sleeps." Which of their reasons do the terms not support, and what difference that matters for
this app did they miss?

### v6

A student wrote: "Plan H. Plan S needs a credit card on Kettle just to sign up, and I don't want to
give one." What have they got wrong about cards, and what would having a card on file actually
risk on each vendor?

### v7

A student wrote: "Plan H. Harbor's server sleeps after 15 minutes; Kettle's doesn't, but its credit
runs out after about three weeks, in grading week. My agent can reach both hosts through their
tools, though S needs two sets of credentials. S means two accounts, copying Kettle's address into
the build, and two places to look when something breaks. Plan S is just worse for this project."
What is missing from their answer? Write it.

### v8

A student wrote: "Plan H. The sleep matters most: a grader shouldn't wait a minute. I'll ask the
agent to ping it every ten minutes so it never sleeps." Do the terms support that workaround? Say
why, and say what it would cost them if they did it.
