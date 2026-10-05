# Activities: debug deployed

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

The minimum route, the orientation and one passed question for each of the nine words, comes to
about 47 minutes: 20 for `a-read-odin-debugging` and about 3 a word. Both capabilities are taught
in the session 12 lab and carry `taught elsewhere`, so the tutor offers the learner the lab first;
`a-locate-described-failure` is there for anyone who wants to check `c-locate-failure` outside it,
at about 3 to 5 minutes a question across seven cases.

In this topic's banks and live questions, hosts are made up, invented for each scenario and used
under one name throughout it, and an agent's account never names a real vendor. Learner-facing
text states the task, never the scoring.

## Check notes

2026-10-05: nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-connect-agent-host` | connect my coding agent to my host so it can read the deployed app's logs | With their own app deployed, connects their coding agent to the host through the host's CLI or MCP server, makes a request to the deployed app, and has the agent show the server log lines that request produced, and the latest deploy's status and build log. It passes when all three come from the deployed app rather than from localhost, and no token or password went through the chat to make the connection. Having the agent change the host's settings is not part of it. |
| `c-locate-failure` | get my agent to say where a deployed app's failure happened, and follow what it says | Given an agent's account of why a deployed app isn't working, in the agent's own terms, says which kind of failure it describes (the build failed, the app failed to start, the app is running but a request errors, the frontend can't reach the backend, or nothing has failed because the app is waking from sleep) and what a visitor to the app sees right now because of it. It passes when both are right, including for an account that never names the stage in plain words. For an account drawn from the code or a run on the laptop rather than the deployed app's logs, it passes when they say it isn't evidence about the deployed app. Fixing it is not part of it. |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-odin-debugging` | |
| `c-connect-agent-host` | `a-connect-own-host` | |
| `c-locate-failure` | `a-locate-described-failure`, `a-locate-own-failure` | |

---

## Activities

### `a-read-odin-debugging`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** three free pages, no account, read in this order as one sitting.
  1. **Read first:** The Odin Project, "Deployment" (Node path),
     https://www.theodinproject.com/lessons/node-path-nodejs-deployment, from the heading
     "Debugging and troubleshooting deployments" down to, and not including, "Assignment". This is
     the section cloud-hosting's orientation told students to skip. Read in full: the three
     opening paragraphs, On deployment, After deployment and One final tip. Skim Node version
     compatibility and Going further with troubleshooting tools (Sentry is out of scope). About
     640 words, 4 to 5 minutes. What it gives: the two stages where problems turn up ("during
     deployment and right after"); build logs, "the stream of output you'll see after kicking off
     a new deployment", whose errors "look like the stack traces you've already seen"; the 500
     page, "deliberately vague"; application logs, "the output of your application as it's
     running"; and backtracking "to the last working version". Odin's advice to paste an error into
     a search engine assumes you read the log yourself; in this course the agent reads it.
  2. **Then:** Render, "Troubleshooting Your Deploy",
     https://render.com/docs/troubleshooting-deploys. Read the opening paragraph ("an app that runs
     fine locally might fail to deploy"), 1. Check the logs, and under Common errors only the
     bullet Misconfigured health checks and the two lists under 500 Internal Server Error and 502
     Bad Gateway. Skip 2. Ensure matching versions and configuration, the other errors, and When to
     contact support. About 450 words, 3 to 4 minutes. What it gives: a failed deploy's logs and a
     running app's logs as two different places; a health check that cancels a deploy when it gets
     no answer; a 500 as "an uncaught exception" in the app, against a 502 when the host can't get
     an answer from it; and timeouts.
  3. **Last:** Render, "Render MCP Server", https://render.com/docs/mcp-server. Read the opening
     paragraph and its list, What is MCP?, and under Setup only the warning that the server
     "supports potentially destructive operations, including modifying a service's environment
     variables and triggering deploys", then the Troubleshooting example prompts ("Pull the most
     recent error-level logs for my API service"). Skip the per-tool setup steps and the table of
     supported actions. About 200 words, 2 minutes.
  About 1,300 words: 10 minutes of reading, 15 with the two stops. Render is one host among
  several a learner may be on; the tutor says so, and that theirs has the same things under its
  own names. Words in place: stack trace, build log, health check, gateway error (as "502 Bad
  Gateway"), timeout, MCP server, and the idea behind rollback in Odin's "last working version".
  Deploy status and CLI are not named in the reading; the tutor names them at stop 2. Two of the
  five kinds of failure in `c-locate-failure`, an app waking from sleep and a frontend that can't
  reach its backend, are in none of the three pages; the tutor brings them in at stop 1.
- **verified:** 2026-10-05
- **learner does:** reads Odin first, with their own deployed app (or, before it is deployed, their
  Problem Set 2 app) in mind, then the two Render pages. Stops twice and answers before reading on;
  "I don't know yet" is an honest answer:
  1. After Odin: **sketches the path a change takes from a push to a visitor's screen as four
     boxes, build, start, a request to the running backend, and the frontend calling the
     backend**, and marks which of Odin's two stages each box is in and which log, if either, the
     build log or the application log, would show a failure there.
  2. After Render's two pages: says how their agent could get at those two logs on their own host
     (or on Render, if they haven't chosen one): through a CLI it runs, or through the host's MCP
     server; and names one thing they would not want the agent to do with that access.
  Then the close, about 5 minutes, with the sketch and the reading still beside them: two quick
  rehearsals, neither judged, each answered in a sentence or two. First, the tutor gives a short
  agent account of a failure and the learner says which box on the sketch it happened at and what
  a visitor sees. Second, the tutor names a host and the learner says how they would let their
  agent read its logs, and what must not go through the chat to set that up. Then answers the
  question the tutor puts: with your sketch and the reading beside you, could you now attempt these
  two things for real: connecting your coding agent to your host so it can show you the deployed
  app's logs, and saying from your agent's account where a deployed app's failure happened and
  what a visitor sees because of it?
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you put a missing package at the request box; when would the host first have needed
  that package?"). At stop 1, adds the two failures the reading doesn't cover if the sketch has no
  place for them, quoting: for waking, Render's free-instance page, https://render.com/docs/free,
  where a free web service that "goes 15 minutes without receiving any inbound traffic" spins
  down, and spinning back up "takes about one minute"; for a frontend that can't reach its
  backend, MDN's "CORS errors" page,
  https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS/Errors, where "the browser
  console will present an error like 'Cross-Origin Request Blocked'", so the server log can show
  nothing wrong at all; and says a frontend still calling `localhost` works on the laptop that runs
  the backend and nowhere else. At stop 2, names deploy status (the host's one-word verdict on the
  latest deploy, such as live or failed) and CLI if the learner hasn't, and if they named nothing
  they'd keep the agent from doing, points at Render's warning about changing settings and
  triggering deploys. Says fixing a failure, and watching the logs of an app that is already in use
  (session 14), are out of scope. Connects nothing and makes no change to the learner's app or host.
  At the close, sets the two rehearsals from the generator below and grades neither; if an answer
  shows a misunderstanding (a failed build meaning the site is down, when the last version is still
  live; a 502 meaning a bug in the app's code), explains it once and moves on. Then puts the
  readiness question as written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops,
  the rehearsals, or whether the tutor thinks they are ready. A plain yes to both parts is
  `criterion: met`. A hedge on either part, with no plain no, is `criterion: unclear`: explain the
  hedged part once more and put the question again; a second hedge stays `unclear`, and the tutor
  offers an activity on that capability, or the session 12 lab. A plain no to either part is
  `criterion: not met`: record it, ask what is missing, and offer to go back over the stop that
  bears on it, or an activity on it; don't put the question again in the same sitting. This goal
  isn't required, so a no never blocks anything else the learner wants to try.
- **generator:** vary the two rehearsal items; hold the rest fixed. Rehearsal one is one question
  from `a-locate-described-failure`'s generator at Easy, case `failed-build` or `request-error`,
  on a made-up app and host. Rehearsal two names one host: the learner's own if they have chosen
  it, otherwise Render or Railway. Fixed: the reading and its two stops, then the two rehearsals in
  that order, neither graded, then the readiness question word for word. Difficulty doesn't vary:
  this settles an indication, not a capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about either capability: the stops and rehearsals are helped, ungraded and of the
  easiest kind, nothing is connected, and only one of the seven cases of `c-locate-failure` is
  rehearsed. It shows nothing about the nine words, which have their own supply.
- **offer as:** this topic's orientation, deliberately one entry holding a sequence: the debugging
  section of the Odin lesson you read half of for cloud-hosting, then two short Render pages on
  what its logs and errors look like and how an agent gets at them, then a short close where you
  say whether you have the shape. About 20 minutes: 15 for the reading and its stops, 5 for the
  close.

### `a-connect-own-host`

- **serves:** `c-connect-agent-host`
- **supports:** attempt
- **checks:** `c-connect-agent-host`
- **artifact:** no external source. The learner's own deployed app, their own host account and
  their own coding agent, in the session 12 lab or at home after it. 20 to 40 minutes, depending
  on the host. Help to point at: for an MCP server, Render's "Render MCP Server",
  https://render.com/docs/mcp-server, which connects through a sign-in in the browser; for a CLI,
  Railway's CLI page, https://docs.railway.com/cli, whose `railway login` opens a browser and whose
  `railway logs`, `railway logs --build` and `railway deployment list` cover all three things.
  Other hosts have their own CLI or MCP server pages.
- **verified:** 2026-10-05
- **learner does:** connects their coding agent to the host their backend runs on, through the
  host's CLI or MCP server, signing in themselves. Then opens the deployed app in a browser and
  does one thing in it that calls the backend, noting the time, and asks the agent to show three
  things: the server log lines that request produced, the latest deploy's status, and that deploy's
  build log. Shows the tutor what the agent showed for each of the three, and says, for each, how
  they know it came from the host and not from their laptop.
- **tutor role:** none
- **tutor does:** before the attempt, says once: sign in yourself, in the browser or in your own
  terminal, and tell the agent to read only, since an MCP server can change settings and start
  deploys. Waits during the attempt, writing down any help word for word. Then checks each of the
  three against the learner's evidence: the log lines show the request they made (its path, and a
  time within a minute or two of theirs) with the host's own timestamps or instance names, not
  output from `npm run dev` or a `localhost` address; the deploy status names the backend's latest
  deploy, whose commit or time matches their latest push to the backend; and the build log is that
  deploy's. Then, and only after the attempt (it is never announced beforehand), asks how they
  signed the agent in to the host: in the browser or their own terminal, or by giving the agent a
  token or password. Does not ask for the agent's transcript or its list of commands. A token or
  password given to the agent fails the attempt, and the tutor tells the learner to revoke it on
  the host and make a new one. Rules, and records the attempt labeled
  `a-connect-own-host/<host>-<cli or mcp>`. If the agent
  changed a setting or started a deploy along the way, says so and how to stop it next time, but
  that alone doesn't fail the attempt. Offers to let the session 12 lab stand for this goal, as
  `taught elsewhere` allows.
- **done when:** criterion met with no help: all three from the deployed app, and no token or
  password through the chat.
- **generator:** the material is the learner's own app, host and agent, so this stays live and no
  two instances match; nobody sets the difficulty, which is the host's. Varies: the host, whether
  it is reached by CLI or MCP server, and the request the learner makes. Fixed: the request is one
  that reaches the backend (loading the frontend's files alone produces no server log line); the
  three things are shown by the agent, not read off the host's dashboard by the learner; the
  connection is made with no secret in the chat. Lines from the host's own request or HTTP log
  count as server log lines for the request. If the backend prints nothing per request and the host
  keeps no request log, the learner first adds one log line to the route the request hits (a
  `console.log` naming the route, or a request-logging middleware), pushes it, and makes the
  request once that deploy is live; that deploy is then the latest, whose status and build log
  count. Where the frontend and backend are on different
  hosts, the backend's host is the one connected, and its latest deploy is the one whose status and
  build log count; connecting the frontend's host too is welcome and not required. Where the
  backend serves the built frontend, there is one host. On a review visit, the learner makes a
  fresh request and has the agent show the three again, in a new session of the agent.
- **worked example:** if the learner is stuck connecting, the first level of help is the host's
  own CLI or MCP page, read together, starting from the sign-in step; if stuck on the log lines,
  ask "what would the request you just made look like in the log, and when did you make it?" Either
  records the attempt as helped.
- **doesn't show:** one host, connected once; a pass doesn't show they could do it on a host whose
  CLI or MCP server works differently. The request is one the learner chose and knows succeeded or
  failed, so a pass doesn't show they could find the lines for a failing request among many. The
  pass on the no-secret clause rests on the learner's own account of how they signed the agent in:
  the tutor reads no transcript, so a token or password that went through the chat and goes
  unmentioned is not caught. The session 12 lab teaches the same connection where a person can
  watch it. A secret typed into the agent's config file or their own terminal outside the chat is
  not examined, and neither is whether the agent's access is read-only.
- **offer as:** the real thing, on your own app and host, and the same task as the session 12 lab;
  do it there if you can. 20 to 40 minutes, most of it the host's sign-in.
- **check note:** The sign-in advice you give before the attempt is part of the task statement,
  given to everyone. Don't count it as help when you rule. That does mean a pass on the no-secret
  clause shows only that the learner followed a stated instruction, as reported by them
  afterwards.

  You see only what the learner shows you. Whether the agent fetched the three things, rather than
  the learner copying them off the host's dashboard, rests on the learner's account just as the
  sign-in does. Where it's easy, ask to see the agent's output with the command or tool call that
  produced it.

### `a-locate-described-failure`

- **serves:** `c-locate-failure`
- **supports:** attempt
- **checks:** `c-locate-failure`
- **artifact:** no external source. A made-up app and host, and an agent's account of one incident
  on it, from this activity's bank or written live per the generator below. 3 to 5 minutes a
  question.
- **verified:** 2026-10-05
- **learner does:** reads the scenario's setup and the one account served, and answers in two or
  three sentences the question every account ends with: "From your agent's account, where did
  things go wrong, if they did, and what does someone visiting the app right now see? If the
  account can't tell you, say why."
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never names the
  kinds of failure or says which ones a scenario holds. When the generator is run live, writes the
  key into the record before showing anything. Gives help whenever it is asked for, and records the
  attempt as helped. A remark about how to fix the failure is neither credited nor counted against
  them. Labels the attempt with the question's path, or `a-locate-described-failure/<case>-<level>`
  when run live, and records the case with `--cases`.
- **done when:** full credit on the question, with no help: for every case but `local-only`, both
  the kind of failure and what a visitor sees right now are right; for `local-only`, they say the
  account isn't evidence about the deployed app. Half credit is not met.
- **generator:** a scenario is one made-up app shaped like Problem Set 2: a React frontend built to
  static files, an Express backend and a database, with a line on what the app does (a club
  sign-up sheet, a study-room finder, a recipe box). The setup names the made-up host of each part,
  in one of three arrangements: frontend and backend on two hosts; one host running them as two
  services; or the backend serving the built frontend itself. It says whether the backend's host
  puts it to sleep when nobody has visited for a while, and that the app has been live and working
  before, except in any incident a question sets at the app's first deploy, which that question's
  own line says. Host names are invented per scenario and never a real vendor's. **Each question is a
  separate incident** on that app, and the setup says the questions are independent. A question
  gives one line on what the student did or noticed ("I pushed a change that adds a search box",
  "a friend says the sign-up page is broken"), then the agent's account, 3 to 8 lines, written as a
  coding agent writes after reading the host through its CLI or MCP server: what it looked at, a
  few quoted log or status lines, and its reading of them. Then the fixed question quoted under
  `learner does`. Log lines are realistic Node, npm, Vite and browser output (`Error: Cannot find
  module 'dotenv'`, `Exited with status 1`, `TypeError: Cannot read properties of undefined
  (reading 'map')` with an `at /app/server/routes/...` line, `GET /api/rooms 500`, a browser
  console's "blocked by CORS policy"), with the host's own wording for statuses invented to match
  the made-up host.

  **Every question carries exactly one case**, named on its rubric `cases:` line, and each case
  fixes what the account must contain and what the key says a visitor sees:
  - `failed-build`: the build log shows an error and the latest deploy's status is failed; nothing
    after the build ran. Key: visitors see the version before this push, unchanged, because a
    failed build replaces nothing; the change isn't there. (Hard variant: the question's line
    says this was the first deploy, so there is no app at the address yet.)
  - `failed-start`: the build succeeded, then the process exited or never answered as it started
    (a module missing at run time, a setting the code needs at start, listening on the wrong port so
    the health check fails). The account must say whether the host kept the previous version
    serving. Key: if it did, visitors see the previous version, the change isn't there, and to them
    it looks like nothing happened; if it didn't (the first deploy of the backend, or a restart
    that keeps exiting), visitors get the host's error where the backend should answer: with the
    frontend on its own host, the page loads but everything that needs data fails; with the backend
    serving the frontend, the host's error page and no app.
  - `request-error`: the latest deploy is live and the app answers, and one request fails with a
    stack trace in the server log, at one route. Key: visitors can use the app, except the one
    action that hits that route, which shows an error or does nothing.
  - `wrong-address`: the frontend loads at its deployed address, and the browser console or
    network panel there shows its calls to the backend going to a wrong or local address
    (`GET http://localhost:3001/api/rooms net::ERR_CONNECTION_REFUSED`, or an old or misspelled
    host address that doesn't resolve); the backend's log on the host, quoted for the same minutes,
    shows no such request arriving. The account quotes both the browser side and the backend's log,
    so it is never drawn from the laptop alone. Key: every visitor sees the page, but nothing that
    needs the backend appears or works.
  - `cors-blocked`: the frontend loads, the backend's log shows the request arriving and answered
    normally, and the browser console shows the answer blocked by CORS. Key: every visitor sees the
    page, but nothing that needs the backend appears or works.
  - `waking`: no error anywhere; the backend's log shows it stopping after a quiet spell and starting
    again on a request, with the next requests succeeding; the student noticed only that the first
    load was slow. Key: nothing has failed; the first visitor after a quiet spell waits up to about a
    minute (a loading page, or a page whose data appears late), then the app works.
  - `local-only`: the account is drawn from the code (the agent read the files and found a likely
    bug) or from a run on the laptop (`npm run dev` works, so the agent concludes something about
    the deployed app), and quotes nothing from the host. Key: it isn't evidence about the deployed
    app; full credit needs only that, and saying the agent should read the host's logs is welcome
    and not required.

  How hard, by how the account is worded:
  - Easy: the account names the stage in plain words ("the build failed", "the server is
    erroring on that route"). Never in the bank and never set as a check: Easy hands over the kind,
    and the criterion asks for it from accounts that don't. It exists only for the orientation's
    ungraded rehearsal.
  - Medium: no plain stage words anywhere ("build failed", "failed to start", "crashed",
    "CORS", "can't reach", "wrong address", "never reached", "asleep", "cold start" are not used
    outside quoted log lines): only
    statuses, exit codes, HTTP codes and quoted log lines, with the agent's reading in its own
    jargon. For `local-only`, the account doesn't say in plain words where it looked ("I read the
    code", "I ran it locally", "on your machine" are not used): it quotes lines from the code (a
    path under `src/` or `server/`) or from a laptop run (`npm run dev` output, a `localhost:5173`
    address), and draws its conclusion about the deployed app from them.
  - Hard: Medium, plus one of: a red herring (a warning in the build log of a deploy that went
    live; an error from an earlier day still in the log); a visitor answer that turns on one stated
    fact (the previous version still serving, or this being the first deploy); or, for
    `local-only`, an agent that writes as if it had checked ("I reproduced it") with nothing from
    the host. An account never draws a conclusion its own quoted lines contradict. An account may
    explain its red herring away ("the rimraf line is a deprecation notice"), since judging a log
    line unaided is beyond this goal; a question whose only Hard feature is a red herring the
    account explains counts as Medium, not Hard.

  A credit statement: full when both the kind (in the learner's own words, matching the case) and
  what a visitor sees match the key, or for `local-only` when they say it isn't evidence about the
  deployed app; half when one of the two is right; none otherwise. A scenario carries all seven cases
  across its questions, one each, every one at Medium or Hard and at least one at Hard. No
  question's text gives away another's answer. A scenario's setup states the task
  and how long an answer should be, never the scoring.
- **worked example:** shown only as help when the learner asks for it, which records the attempt as
  helped. Work a different account aloud: find the last thing that went right (the build finished;
  the server printed that it was listening; the request reached the server), then the first thing
  that didn't, and name the box; then ask what a visitor's browser asks for and which version, if
  any, is answering. For a 502 against a 500, cite Render's "Troubleshooting Your Deploy",
  https://render.com/docs/troubleshooting-deploys, under Runtime errors. At the first level of help
  on a real attempt, ask only "where did the last thing that went right happen?"
- **doesn't show:** the accounts are written to be clear and true to their own log lines, so a pass
  doesn't show the learner would catch an agent drawing the wrong conclusion from its logs, or
  would ask the agent for logs it didn't fetch. Hosts are made up, so a pass says nothing about a
  real host's status words. The learner answers one account at a time, knowing a check is on. The
  `waking` and `failed-start` keys depend on host behavior the setup states (whether a failed
  deploy leaves the old version serving, how long waking takes); a learner who knew their own host
  behaves otherwise could be right there and marked wrong. `wrong-address` and `cors-blocked` share
  a visitor key, so on those two only the kind of failure tells them apart.
- **offer as:** the check you can do any time, without a deployed app: an agent's account of one
  incident on a made-up app, 3 to 5 minutes a question, one kind of failure each. Take it if you
  missed the session 12 lab, or to review.
- **check note:** On `wrong-address` and `cors-blocked`, the criterion asks only for "the frontend
  can't reach the backend". An answer saying the page's calls to the backend aren't getting
  answers through has the kind right on either case. Don't require the learner to name CORS or the
  wrong address, even though `doesn't show` says only the kind tells the two apart.

  For the visitor half, credit an answer that captures what the key turns on, not every detail of
  it. That means: whether the rest of the app works (`request-error`), whether the old version or
  nothing is at the address (`failed-build`, `failed-start`), and a wait followed by normal use
  (`waking`). An answer that leaves out the part the key turns on is half credit.

  A scenario holds one question per case, so a learner who has worked several of its questions can
  sometimes narrow the last ones by elimination. Where you can, move to a different scenario
  before a learner works a single scenario's last two questions.

  For a 502 against a 500, the worked example cites Render's page under "Runtime errors". The
  orientation's reading assignment names that page's "500 Internal Server Error" and "502 Bad
  Gateway" lists instead, so look for the material under those headings if the section names
  differ.

### `a-locate-own-failure`

- **serves:** `c-locate-failure`
- **supports:** attempt
- **checks:** `c-locate-failure`
- **artifact:** no external source. The learner's own deployed app when it actually misbehaves, in
  the session 12 lab or while working on Problem Set 3, and their agent's account of why. It can
  run before `c-connect-agent-host` is met: an agent not yet connected to the host can only answer
  from the code or a laptop run, which is the `local-only` case. 5 to 10 minutes, whenever it
  happens.
- **verified:** 2026-10-05
- **learner does:** asks their agent why the deployed app isn't working, and gets its account. Before
  the tutor says anything, says in two or three sentences what kind of failure the account
  describes, if any, and what someone visiting the app right now sees; or, if the agent answered
  from the code or a laptop run, that this isn't evidence about the deployed app.
- **tutor role:** none
- **tutor does:** reads the agent's account and the log or status lines it quotes, and writes the key
  into the record before hearing the learner: the case (one of the seven named in
  `a-locate-described-failure`'s generator) and what a visitor sees. If the quoted lines don't
  settle it, or the agent's reading of them disagrees with what they show, says "not judged" and
  records no attempt, rather than guessing; after the learner has answered, says where the reading
  and the lines part, and a learner who spotted it is told so. Also notes whether the account names
  the stage in plain words (as the Easy level in `a-locate-described-failure` describes, or for
  `local-only`, says plainly it read the code or ran on the laptop). Waits, writing down any help
  word for word. Rules and labels the attempt `a-locate-own-failure/<case>`; records the case with
  `--cases` only when the account didn't name the stage plainly, and otherwise records the attempt
  without it, since it handed over the kind. Does not help fix the failure as part of this; that comes after.
- **done when:** criterion met with no help, on the one case this incident carries.
- **generator:** the material is whatever goes wrong with the learner's own app, so this stays live
  and nobody sets the case or the difficulty. Fixed: the account is the learner's own agent's, word
  for word, and the key comes from the lines it quotes from the host, or their absence. An agent
  that guessed from the code is the `local-only` case, and the only one possible before the agent
  is connected. On review visits, use the next real incident; until all seven cases have passed, offer
  `a-locate-described-failure` for the ones that haven't come up.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "did that line come from the build log or from the running app's log?", and the attempt is
  recorded as helped.
- **doesn't show:** which cases come up is luck, and `waking`, `wrong-address` or `cors-blocked`
  may never come up on a learner's own app. The learner usually knows what they last changed, which can stand
  in for reading the account. The key rests on the tutor's reading of what the agent quoted. A real
  agent usually names the stage plainly, and such an incident credits no case, so many incidents
  here end as practice.
- **offer as:** the real thing: your own app, your own agent's account, the first time something
  breaks. Any time from the session 12 lab on; `a-locate-described-failure` covers the cases your
  app hasn't had.
- **check note:** When the agent's account names the stage plainly (as the Easy level in
  `a-locate-described-failure` describes), don't record a ruled attempt. Record it as `criterion:
  unchecked` and treat the incident as practice. The recording tool refuses a ruled attempt on
  this goal without `--cases`, and an attempt with no cases would count toward all seven. Rule, and
  pass `--cases`, only when the account left the kind for the learner to work out.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
