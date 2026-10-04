Each question carries one case of `c-weigh-hosting-plans`. What the terms give, by case, for this app
(about twenty users, a class project, graded in the last week of the month):

- **Free limits** (case `free-limits`). Sleep: Quayline's web service sleeps after 15 minutes
  idle and the next visitor waits about a minute; its static site never sleeps; Lanternhost and
  Emberbox never sleep. Past a limit: Quayline suspends web services after 750 free hours a month (one
  service all month is up to 744 hours, a 31-day month, so it isn't reached) and, past 100 GB of
  bandwidth, bills with a card on file or suspends without one; Lanternhost pauses at 100 GB;
  Emberbox's $1 credit lasts about three weeks, so its server stops in grading week, or with a card
  on file keeps running and bills. Card: none of the three requires one; one on file lets Quayline
  bill bandwidth and Emberbox bill past its credit; Lanternhost can't bill.
- **Agent reach** (case `agent-reach`). Quayline: one official CLI and MCP server for both parts,
  which can deploy, read logs and set environment variables, and can't delete services or change
  plans. Lanternhost: a CLI that deploys and sets build settings, with deploy logs only (it runs no
  code, so there are no request logs). Emberbox: an official CLI and MCP server that can deploy, read
  logs and set environment variables; the terms state nothing it can't do.
- **Vendor count** (case `vendor-count`). Plan S's extra vendor adds a second account, a second
  set of agent credentials (its secrets), and a second dashboard and place to look when something
  breaks; Emberbox's address copied into the frontend's build is credited if named, never required.
  Moving is easy from both: ordinary `npm` builds on Quayline, plain files on Lanternhost, ordinary
  Node on Emberbox plus a small `emberbox.toml`.
- **Other case** (case `other-case`). The difference that matters most: Quayline's server sleeps
  (a grader may wait a minute) but never stops; Emberbox's never sleeps but stops in grading week
  unless a card is on file. So the strongest case for S is that nothing in it sleeps, and for Q that
  its server never stops in grading week, with one account and one agent tool. "No card means no
  bill" holds for both plans and doesn't count as a case for either. "It's simpler" alone is not a
  difference in the terms.

Not deciding for twenty users, and never a miss when left out: the 100 GB bandwidth lines, Quayline's
750-hour limit, Lanternhost having no request logs, Emberbox's `emberbox.toml`. Naming one is fine if
what is said matches the terms. A claim the terms contradict is a miss; "nothing in the terms says
this" is enough to name one that is merely unsupported. Which plan anyone chooses earns nothing
either way. Remarks about where the database goes are neither credited nor counted.

### v9

- **goal:** `c-weigh-hosting-plans`
- **cases:** free-limits
- **answer:** Plan Q: the web service sleeps after 15 minutes and wakes in about a minute (the
  static site never sleeps); past 750 hours services are suspended, and past 100 GB bandwidth is
  billed with a card on file or suspended without one. Plan S: nothing sleeps; Emberbox's credit lasts
  about three weeks, then the server stops until next month, or with a card on file keeps running
  and bills; Lanternhost pauses at 100 GB. Neither plan requires a card; one on file lets Quayline or
  Emberbox bill, and Lanternhost can't.
- **credit:** full for sleep, past a limit, and card (required, and the risk of one on file) each
  stated as the terms give them for both plans, with nothing unsupported. Half for all three on one
  plan only, or two of the three on both.

### v10

- **goal:** `c-weigh-hosting-plans`
- **cases:** agent-reach
- **answer:** Plan Q: yes, one official CLI and MCP server reaches both parts to deploy, read logs
  and set environment variables; it can't delete services or change plans. Plan S: Emberbox's CLI and
  MCP server can deploy, read logs and set environment variables; Lanternhost's CLI can deploy and
  set build settings, with deploy logs only, since it runs no code.
- **credit:** full for each host's reach stated as the terms give it, including what Quayline's tool
  can't do and that Lanternhost has only deploy logs, with nothing unsupported (such as a limit on
  Emberbox's tool the terms don't state). Half for one plan right and the other missing or wrong, or
  for both plans' reach with what the tools can't do left out.

### v11

- **goal:** `c-weigh-hosting-plans`
- **cases:** vendor-count
- **answer:** the extra vendor adds a second account, a second set of agent credentials, and a
  second dashboard and place to look when something breaks (Emberbox's address copied into the
  frontend's build may also be named). Moving is easy from both: ordinary `npm` builds on Quayline;
  plain files on Lanternhost, which any static host can take; ordinary Node on Emberbox, plus its small
  `emberbox.toml`.
- **credit:** full for accounts, secrets (the agent's second credentials, or the copied address)
  and places to look, and how hard each plan is to move, each as the terms give it, with nothing
  unsupported. Half for the extra vendor's cost without moving, or moving without the cost.

### v1

- **goal:** `c-weigh-hosting-plans`
- **cases:** other-case
- **answer:** either plan, then the strongest case for the other. For S: nothing in it ever
  sleeps, so a grader never waits a minute. For Q: its server never stops, while Emberbox's stops in
  grading week unless a card is on file; and one account and one agent tool for both parts.
- **credit:** full for a choice and a case for the other plan that rests on a difference in the
  terms that matters for this app (S never sleeps; Q never stops in grading week), with nothing
  unsupported. Half for a true case that rests only on a difference that doesn't decide anything
  here (bandwidth, logs, `emberbox.toml`), or on "it's simpler" alone.

### v2

- **goal:** `c-weigh-hosting-plans`
- **cases:** other-case
- **answer:** Quayline's server never stops, while Emberbox's stops in grading week unless a card is on
  file; and one account and one agent tool for both parts, with nothing to copy between vendors.
  The cost the student named, a minute's wait after 15 idle minutes, is the one Q carries.
- **credit:** full for a case that rests on Quayline's server not stopping in grading week, or on one
  account and one agent tool, stated as the terms give it, with nothing unsupported. "No card means
  no bill" holds for S too and doesn't count. Half for a case that rests on "simpler" alone, or on
  a difference that doesn't decide anything here.
- **tutor note:** if `v1` was served before, ask how this case compares with the one they gave
  there for the plan they didn't choose.

### v3

- **goal:** `c-weigh-hosting-plans`
- **cases:** free-limits
- **answer:** "free forever" and "never charges anything" are not supported: with a card on file,
  Quayline bills bandwidth past 100 GB a month. The terms say no card is needed, and without one
  Quayline suspends rather than bills. The two accounts point is right.
- **credit:** full for both claims named as unsupported and what the terms say instead (no card
  needed; a card on file lets Quayline bill; without one it suspends). Half for one claim, or both
  named with nothing the terms say instead.

### v5

- **goal:** `c-weigh-hosting-plans`
- **cases:** free-limits
- **answer:** faster under load, more reliable and more secure appear nowhere in the terms. Missed:
  Emberbox's credit lasts about three weeks, so its server stops in grading week unless a card is on
  file, and then it bills.
- **credit:** full for the three reasons named as unsupported and Emberbox's stop (or the card risk
  that comes with avoiding it) named as missed. Half for one of the two.

### v6

- **goal:** `c-weigh-hosting-plans`
- **cases:** free-limits
- **answer:** no vendor needs a card to sign up; the terms say so in their first line. A card on
  file is a risk, not a requirement: on Quayline it lets bandwidth past 100 GB be billed, on Emberbox it
  keeps the server running past the credit and bills; Lanternhost can't bill at all.
- **credit:** full for the terms' first line named as contradicting the claim, and the risk of a
  card on file stated for Quayline and Emberbox. Half for one of the two.
- **tutor note:** if `v3` was served before, ask what each said about a card.

### v8

- **goal:** `c-weigh-hosting-plans`
- **cases:** free-limits
- **answer:** yes: a ping every ten minutes beats the 15-minute sleep, and one service awake all
  month is up to 744 hours, under Quayline's 750, so nothing is suspended and, with no card on file,
  nothing is billed. It costs nothing in these terms, though it leaves only a few hours' margin.
- **credit:** full for "supported" with both reasons (ten minutes is under 15, and the hours stay
  under 750). Half for "supported" with one reason. None for "unsupported", which the terms
  contradict.

### v4

- **goal:** `c-weigh-hosting-plans`
- **cases:** vendor-count
- **answer:** a second set of agent credentials and a second tool, and a second dashboard and
  place to look when something breaks. Emberbox's address copied into the frontend's build may also be
  named. Their "moving is easy from either" is right.
- **credit:** full for the agent's second credentials (or second tool) and the second place to
  look, with nothing unsupported; Emberbox's address is credited if named, never required. Half for
  one of the two.
- **tutor note:** if `v11` was served before, ask which of what they named there this student
  left out.

### v7

- **goal:** `c-weigh-hosting-plans`
- **cases:** other-case
- **answer:** the strongest case for Plan S: nothing in it ever sleeps, so no grader waits a minute.
- **credit:** full for a case for S that rests on its never sleeping (or another difference in the
  terms that matters for this app), with nothing unsupported. Half for a case that rests on
  "simpler", or on a difference that doesn't decide anything here (bandwidth, logs).
- **tutor note:** if `v1` or `v2` was served before, ask how this case compares with the ones given
  there.
