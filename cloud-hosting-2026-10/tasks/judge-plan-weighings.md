# Judge eight choices between two hosting plans

**Used by:** `a-judge-plan-weighings`, which serves `c-weigh-hosting-plans`. A study activity:
nothing here can meet the goal. `a-weigh-described-plans` uses the vendors below for its worked
example only. The key is in `judge-plan-weighings-key.md`, for the tutor.

## The app

Crumbs is a recipe-sharing app for a class project: a React frontend built with Vite, an Express
server, and a Postgres database (its agent switched it from SQLite so the database could have its
own host). About twenty people will use it, mostly classmates, mostly in the week it is graded. Its
owner works through a coding agent.

## Two plans

- **Plan H, one vendor.** Harbor hosts the frontend as a static site, the server as a web service,
  and the database.
- **Plan S, a vendor for each part.** Brightpage hosts the frontend, Kettle runs the server, Ledger
  hosts the database.

## The vendors' free-tier terms

These vendors are made up, so these terms don't go out of date; each is modeled on terms real
vendors offered on 2026-10-01.

**Harbor**

- Static sites: free, never sleep.
- Web services: free; a service that gets no request for 15 minutes is put to sleep, and the next
  request waits about a minute while it wakes. 750 free hours a month across the account; past
  that, every web service is suspended until the month ends.
- Postgres: free, 1 GB. A free database expires 30 days after it is created; after a 14-day grace
  period it is deleted unless upgraded to a paid plan ($7 a month).
- Card: not needed to sign up. With a card on file, bandwidth past 100 GB a month is billed at
  $0.15 per GB. Without one, services are suspended instead.
- Agent access: an official command-line tool and MCP server that can deploy, read logs, and set
  environment variables for any of the three. They cannot delete services or change plans.
- Moving: services build from your GitHub repository with ordinary `npm` commands; the database
  can be exported with the standard Postgres tool (`pg_dump`).

**Brightpage**

- Free; never sleeps. 100 GB of bandwidth a month, a hard cap: past it, the site is paused until
  the next month. The free plan takes no card, so nothing can be billed.
- Agent access: a command-line tool that can deploy and set build settings. Brightpage runs no code
  of yours, so it has deploy logs but no logs of requests.
- Moving: it hosts a folder of files; any static host can take them.

**Kettle**

- $1 of free credit a month, which keeps a small server running all month; it never sleeps. If the
  credit runs out, the server stops until next month. With a card on file, it keeps running and the
  extra is billed.
- Card: not needed to sign up.
- Agent access: an official command-line tool and MCP server; can deploy, read logs, and set
  environment variables.
- Moving: Kettle reads a small `kettle.toml` file the agent writes; the server itself is ordinary
  Node.

**Ledger**

- Free, 0.5 GB, never expires. The database stops after 5 minutes without queries and wakes in
  under a second. Past 0.5 GB, writes are refused; nothing is deleted.
- Card: not needed, and the free plan can't be billed.
- Agent access: an official MCP server and command-line tool that can run SQL, including SQL that
  changes or deletes data. Ledger's docs advise using it only on development databases.
- Moving: standard Postgres; export with `pg_dump`.

## For each choice, answer

Eight students each chose a plan and said why. For each one: does it name every difference in
these terms that would matter for this app; does it say what Plan S's extra vendors add in
accounts, secrets and places to look when something breaks; does it claim anything the terms don't
support; and does it state the strongest case for the plan it didn't choose? Say which of these it
misses, if any. Which plan it chose doesn't count either way.

Then write the list of differences you would expect a complete answer to name.

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
