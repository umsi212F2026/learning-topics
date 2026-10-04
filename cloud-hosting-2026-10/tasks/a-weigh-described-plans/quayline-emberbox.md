**The app.** Crumbs, a recipe-sharing class project: a React frontend built with Vite and an
Express server. About twenty users, mostly in the week it is graded, which is the last week of the
month. It has to stay up all month, so a server that stops partway through the month is down in
grading week. Its owner works through a coding agent.

**Plan Q, one vendor:** Quayline hosts the frontend (a static site) and the server (a web service).
**Plan S, a vendor for each:** Lanternhost hosts the frontend, Emberbox runs the server.

**Free-tier terms** (made-up vendors, modeled on real terms of 2026-10-01). No vendor needs a card
to sign up.

- **Quayline.** Static sites never sleep. The web service sleeps after 15 minutes without a request,
  and the next request waits about a minute; 750 free hours a month (web services only), then suspended. With a card
  on file, bandwidth past 100 GB a month is billed ($0.15 per GB); without one, services are
  suspended. One official CLI and MCP server for both parts: deploy and set environment variables;
  it can't read the web service's logs (those are only in the dashboard), and it can't delete
  services or change plans. Builds with ordinary `npm`.
- **Lanternhost.** Never sleeps. 100 GB a month, a hard cap: past it, paused until next month. The
  free plan takes no card, so it can't bill. A CLI that deploys and sets build settings; deploy
  logs only, since it runs no code. Any static host can take the files.
- **Emberbox.** $1 of credit a month, enough to keep a small server running for about three weeks;
  never sleeps. When the credit runs out the server stops until next month, or, with a card on
  file, keeps running and bills. Official CLI and MCP server: deploy, read logs, set environment
  variables. Reads a small `emberbox.toml`; the server is ordinary Node.

Answer from these terms only.

### v9

For each plan, say whether the app sleeps when nobody has used it for a while, what happens when it
passes a limit, and whether a credit card is required and what having one on file would risk.

### v10

For each plan, say whether your agent could reach every host to change its settings and read its
logs, and what it couldn't do there.

### v11

Say what Plan S's extra vendor adds, and how hard each plan would be to move to another vendor.

### v1

Make the call yourself. Choose Plan Q or Plan S, then state the strongest case the terms give for
the plan you didn't choose.

### v3

A student wrote: "Plan Q, because it's free forever and Quayline never charges anything. The other
plan has two accounts, which is more to manage." Which of their claims do the terms not support,
and what do the terms say instead?

### v5

A student wrote: "Plan S, because two specialized vendors will be faster under load and more
reliable than one that does everything, and Emberbox is more secure since it runs only one program. Quayline
sleeps." Which of their reasons do the terms not support, and what in the plans' sleep, limit and
card terms did they miss?

### v6

A student wrote: "Plan Q. Plan S needs a credit card on Emberbox just to sign up, and I don't want to
give one." What have they got wrong about cards, and what would having a card on file actually
risk on each vendor?

### v7

A student wrote: "Plan Q. Quayline's server sleeps after 15 minutes, but that's fine for a class
project. My agent can reach both hosts through their tools. Plan S is just worse for this project."
They give no case for the plan they didn't choose. Write the strongest case the terms give for
Plan S.

### v8

A student wrote: "Plan Q. The sleep matters most: a grader shouldn't wait a minute. I'll ask the
agent to ping it every ten minutes so it never sleeps." Would that workaround work under these
terms, and what would it cost?

### v2

A student chose Plan S and wrote: "A grader opening Crumbs after a quiet spell would wait a minute
on Quayline; Emberbox never sleeps." Give the strongest case for Plan Q, the
plan they didn't choose, using only the terms.

### v4

A student wrote: "Plan S. Nothing sleeps, and Lanternhost can't bill me. Quayline's server sleeps
after 15 minutes. Emberbox's credit runs out after about three weeks; if I keep a card off it, the
worst case is the server stopping until next month. Moving is easy from either. The strongest case
for Q is that it's one account." What does Plan S's extra vendor cost that this student left out?
