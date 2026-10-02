# Judge one choice between two hosting plans

**Used by:** `a-judge-plan-weighings`, which serves `c-weigh-hosting-plans`. A study activity:
nothing here can meet the goal. A bank of eight students' choices, `v1` to `v8`: each sitting
shows the header above the line and one choice below it. `a-weigh-described-plans` uses these
vendors for its worked example only. The key is in `judge-plan-weighings-key.md`, for the tutor.

**The app.** Crumbs, a recipe-sharing class project: a React frontend built with Vite, an Express
server, and a Postgres database (its agent switched it from SQLite). About twenty users, mostly in
the week it is graded. Its owner works through a coding agent.

**Plan H, one vendor:** Harbor hosts the frontend, the server and the database.
**Plan S, a vendor per part:** Brightpage the frontend, Kettle the server, Ledger the database.

**Free-tier terms** (made-up vendors, modeled on real terms of 2026-10-01). No vendor needs a card
to sign up.

- **Harbor.** Static sites never sleep. The web service sleeps after 15 minutes without a request,
  and the next request waits about a minute; 750 free hours a month, then suspended. Postgres, 1
  GB: expires 30 days after creation, deleted after 14 more days unless upgraded ($7 a month).
  With a card on file, bandwidth past 100 GB a month is billed ($0.15 per GB); without one,
  services are suspended. One official CLI and MCP server for all three parts: deploy, read logs,
  set environment variables; can't delete services or change plans. Builds with ordinary `npm`;
  database exports with `pg_dump`.
- **Brightpage.** Never sleeps. 100 GB a month, a hard cap: past it, paused until next month. The
  free plan takes no card, so it can't bill. A CLI that deploys and sets build settings; deploy
  logs only, since it runs no code. Any static host can take the files.
- **Kettle.** $1 of credit a month, enough to keep a small server running all month; never
  sleeps. If the credit runs out the server stops until next month, or, with a card on file, keeps
  running and bills. Official CLI and MCP server: deploy, read logs, set environment variables.
  Reads a small `kettle.toml`; the server is ordinary Node.
- **Ledger.** 0.5 GB, never expires. Stops after 5 minutes without queries, wakes in under a
  second. Past 0.5 GB, writes are refused; nothing deleted. Can't be billed. Official MCP server
  and CLI that can run SQL, including SQL that changes or deletes data; its docs advise using it
  only on development databases. Standard Postgres, `pg_dump`.

**For the choice you are given:** does it name every difference in these terms that would matter
for this app; say what Plan S's extra vendors add in accounts, secrets and places to look when
something breaks; claim anything the terms don't support; and state the strongest case for the
plan it didn't choose? Say which it misses, if any, and one thing it should have said. Which plan
it chose doesn't count either way.

---

### v1

> Plan S. Harbor's free database expires after 30 days and is deleted two weeks later unless I pay
> $7 a month, and the project runs longer than that. Ledger's never expires. Harbor's server sleeps
> after 15 minutes and the first visitor waits a minute; Kettle's doesn't sleep, though if the $1
> runs out it stops. Ledger's database also stops when idle but wakes in under a second, so nobody
> will notice. None of the four needs a card, and I wouldn't put one on Harbor or Kettle, because then a spike gets billed instead of
> paused; Brightpage and Ledger can't bill at all. Harbor gives my agent one tool for everything;
> with S it needs three, and Brightpage has no request logs, though there's nothing running there to
> log. S means three accounts, three sets of tokens for my agent, Ledger's connection string has to
> go into Kettle's settings and Kettle's address into the frontend's build, and when something
> breaks I have three dashboards to look in. Moving is easy either way: ordinary Node, plain files,
> and `pg_dump`, plus Kettle's config file. The best case for H: one account, one place to look, one
> tool for my agent, and if I'd pay $7 the database problem goes away.

### v2

> Plan H. One account is simpler, and my agent can reach everything through one MCP server and read
> every log in one place. The sleep is the real cost: a grader opening the app after a quiet spell
> waits a minute. The database expires after 30 days, so I'd either finish and present within six
> weeks or pay $7. Harbor doesn't need a card and I'd keep none on it, so going past 100 GB suspends it instead of billing
> me; at twenty users that won't happen. Moving off is ordinary npm and `pg_dump`. The best case for
> S: nothing in it expires, the server never sleeps, and Brightpage and Ledger can never bill me.
> But it is three accounts, three sets of credentials for my agent, two connection settings to wire
> between them (the database string into Kettle, Kettle's address into the build), and three places
> to look when something breaks.

### v3

> Plan H, because it's free forever and Harbor never charges anything. The other plan has three
> accounts, which is more to manage.

### v4

> Plan S. Nothing sleeps, nothing expires, and Brightpage and Ledger can't bill me. Harbor's server
> sleeps after 15 minutes and its database is deleted after six weeks. If I keep a card off Kettle,
> the worst case is the server stopping until next month. Moving is easy from either. The strongest
> case for H is that it's one account.

### v5

> Plan S, because three specialized vendors will be faster and more reliable than one that does
> everything, and Ledger is more secure since it's only a database. Harbor sleeps and its database
> expires. Plan S is three accounts and three places to look, and my agent needs three logins. The
> best case for H is simplicity.

### v6

> Plan H. Plan S needs a credit card on Kettle to keep it running, and I don't want to give one.
> Harbor's sleep is annoying but fine for a class project. Its database expires after 30 days, so
> I'd pay $7 for the last month. My agent can do everything on Harbor through one tool. S would be
> three accounts and the secrets would have to be copied between them. The best case for S is that
> nothing sleeps.

### v7

> Plan S. Harbor's database expires and its server sleeps; Kettle and Brightpage don't sleep, and
> Ledger only pauses briefly. A card on Harbor would mean being billed past 100 GB. My agent can
> reach Harbor, Kettle and Ledger through their tools, though it would need three sets of
> credentials; Brightpage only has deploy logs. Moving off either is easy. S does mean three
> accounts and wiring the database string and server address between them, and three places to look
> when something breaks. Plan H is just worse for this project.

### v8

> Plan H. The sleep matters most: a grader shouldn't wait a minute. Wait, that's the plan I'm
> choosing. Fine: I'll ask the agent to ping it every ten minutes so it never sleeps. The database
> expires in 30 days, so I'll make a new free one each month. One account, one tool for my agent,
> one place for logs. S is three accounts, three sets of secrets and three dashboards. The best case
> for S is that nothing in it expires or sleeps, and two of its vendors can never bill.
