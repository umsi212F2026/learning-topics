# Judge one choice between two hosting plans

**Used by:** `a-judge-plan-weighings`, which serves `c-weigh-hosting-plans`. A study activity:
nothing here can meet the goal. A bank of eight students' choices, `v1` to `v8`: each sitting
shows the header above the line and one choice below it. `a-weigh-described-plans` uses these
vendors for its worked example only. The key is in `judge-plan-weighings-key.md`, for the tutor.

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

**For the choice you are given:** does it name every difference in these terms that would matter
for this app; say what Plan S's extra vendor adds in accounts, secrets and places to look when
something breaks; claim anything the terms don't support; and state the strongest case for the
plan it didn't choose? Say which it misses, if any, and one thing it should have said. Which plan
it chose doesn't count either way.

---

### v1

> Plan H. Kettle's credit lasts about three weeks, so in the last week of the month, which is
> grading week, the server stops unless I put a card on it, and then it bills. Harbor's server
> sleeps after 15 minutes and the first visitor waits a minute, but it doesn't stop. None of them
> needs a card; I'd keep none on Harbor or Kettle, since a card turns a stop into a bill, and
> Brightpage can't bill at all. Harbor gives my agent one tool for both parts; S needs two, and
> Brightpage only has deploy logs, though it runs nothing to log. S means two accounts, two sets of
> credentials for my agent, Kettle's address copied into the frontend's build, and two dashboards
> to look in when something breaks. Moving is easy either way: ordinary npm and Node, plain files,
> plus Kettle's config file. The best case for S: nothing in it ever sleeps, so no grader ever
> waits a minute, and Brightpage can never bill me.

### v2

> Plan S. A grader opening Crumbs after a quiet spell would wait a minute on Harbor; Kettle never
> sleeps. Kettle's credit only lasts about three weeks, so I'd need it to cover grading week, or
> put a card on and accept it bills; no vendor needs a card to sign up. My agent would need two
> tools and two sets of credentials instead of Harbor's one, and Kettle's address has to go into
> the frontend's build. Two accounts, two places to look. Moving off either is ordinary Node and
> plain files. The strongest case for H: it never stops, one account, one tool for my agent, and
> no card on file means nothing can bill.

### v3

> Plan H, because it's free forever and Harbor never charges anything. The other plan has two
> accounts, which is more to manage.

### v4

> Plan S. Nothing sleeps, and Brightpage can't bill me. Harbor's server sleeps after 15 minutes.
> Kettle's credit runs out after about three weeks; if I keep a card off it, the worst case is the
> server stopping until next month. Moving is easy from either. The strongest case for H is that
> it's one account.

### v5

> Plan S, because two specialized vendors will be faster and more reliable than one that does
> everything, and Kettle is more secure since it runs only one program. Harbor sleeps. Plan S is
> two accounts and two places to look, and my agent needs two logins. The best case for H is
> simplicity.

### v6

> Plan H. Plan S needs a credit card on Kettle to keep it running, and I don't want to give one.
> Harbor's sleep is annoying but fine for a class project. My agent can do everything on Harbor
> through one tool. S would be two accounts and the server's address would have to be copied into
> the frontend. The best case for S is that nothing sleeps.

### v7

> Plan H. Harbor's server sleeps after 15 minutes; Kettle's doesn't, but its credit runs out after
> about three weeks, in grading week. A card on Harbor would mean being billed past 100 GB, and a
> card on Kettle would mean being billed once the credit is gone. My agent can reach Harbor and
> Kettle through their tools, though S needs two sets of credentials; Brightpage only has deploy
> logs. Moving off either is easy. S does mean two accounts, copying Kettle's address into the
> build, and two places to look when something breaks. Plan S is just worse for this project.

### v8

> Plan H. The sleep matters most: a grader shouldn't wait a minute. Wait, that's the plan I'm
> choosing. Fine: I'll ask the agent to ping it every ten minutes so it never sleeps. One account,
> one tool for my agent, one place for logs. S is two accounts, two sets of secrets and two
> dashboards, and its server stops after three weeks. The best case for S is that nothing in it
> sleeps, and Brightpage can never bill.
