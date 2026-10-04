# Learning goals: cloud hosting

**origin:** course
**study by:** 2026-10-06, 1 of 3

**What I want to be able to do, and what would count as having got there.**

<!--
  Everything in HTML comments is guidance, not content. It doesn't appear in a rendered
  view, so this reads clean if you leave it in — but delete each one as you fill its
  section and the file stays short.

  This is the layout for <area>-<yyyy>-<mm>/goals.md in your learning-topics repository,
  created blank by
  workflows/learn/tools/new-topic.mjs. Don't edit this file; edit the copy.
  Later phases read that file and answer to it; they write to their own.

  IDS LIVE HERE, in the Goals section below, and this is the only place they are assigned.
  Everything downstream keys on them: activities.md's `serves` and `checks`, and every line
  of evidence/attempts.jsonl and status.jsonl.

  The rule:

    Two to four lower-case words with hyphens between, conventionally prefixed — `c-` for a
    capability, `w-` for a word, `o-` for an orientation. `c-read-unseen-diagram`,
    `w-persistence`.

    THE PREFIX IS A READING AID AND NOTHING ELSE. No program decides anything from it; what
    kind of goal this is, if the question even arises, is answered by its slots. What is
    checked is that a goal id doesn't start with `a-`, which activities.md's entries do — a
    log line carries both side by side, and the prefix is what makes that parse at a glance.

    AIM AT WHAT THE THING IS, not at how the entry is phrased. `token, and what it costs` is
    `w-token-cost`, not `w-token-and-what-it-costs`. Stopwords carry nothing and you will be
    reading these in a log.

    UNIQUE WITHIN THE TOPIC — across the goals here and across activities.md's entries,
    including its dropped ones, which keep their ids. Nothing checks you as you write; a
    duplicate surfaces later when workflows/learn/tools/survey.mjs walks the folder, and by then attempts point
    at it.

  AN ID IS PERMANENT. Reword an entry and the id stays — the log already points at it, and a
  rename orphans everything recorded against it. An entry that becomes a genuinely different
  capability is a new entry with a new id, not a rename.

  Words added by workflows/learn/tools/new-word.mjs carry ids too; that script takes the id and never invents
  one. See workflows/learn/skills/add-topic/SKILL.md.
-->

## Where this came from

_Yours to fill in. Nobody can answer this one for you._

<!-- Which of A / B / C / D, and the answer to the follow-up. -->

## What I already have

_Yours to fill in. Say where your knowledge stops, not what you have heard of._

<!--
  The nearest thing already known well, and where it stops.
  This is a claim, not a verified fact — it's a self-report about one's own knowledge,
  and the assessment may contradict it.
-->

## What I'll use it for

_Yours to fill in. The course supplies two occasions: the session 11 lab, where your table writes
one prompt asking an agent to compare cloud hosting providers, each of you runs it and signs up
for accounts, and the table discusses why the answers differed; and Problem Set 3, which puts your
Problem Set 2 app on the public internet. Name any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Choose a vendor for each part of your app, and check what your agent says about them.** Not
setting a deploy up, and not comparing every vendor on the market. Your agent can research hosting
providers and walk you through signing up, but what it knows about prices and free tiers can be
out of date, and it will not tell you when it is. This topic is enough to say which kind of host
your frontend and backend need, to check a claim about a free tier against the vendor's own pages, and
to choose between plans knowing what each one costs you if the app sleeps, outgrows its limits or
has to move.

What sits past that line: connecting your app to GitHub so it deploys itself, keeping config and
secrets out of your code, and where the database lives and keeping its data safe once it is hosted
are each a topic of their own. Sign-in belongs to Part B of Problem Set 3, not to this topic.

<!--
  Which of: recognize it / read it / modify something existing / author from scratch /
  judge someone else's work. One line on why that's enough.
-->

## Sequence

1. orientation
2. vocabulary
3. c-place-app-parts
4. c-check-vendor-claims
5. c-weigh-hosting-plans

## Goals

### `c-place-app-parts`

- **goal:** say which kind of host the frontend and the backend each need, and whether a hosting
  plan covers them
- **criterion:** Given an app with a React frontend and an Express backend, and a hosting plan
  listing each vendor and what it offers, says which part each vendor would host, and names any
  part the plan leaves without a host or puts on a host that cannot run it, or says both are
  covered. It passes when every gap and mismatch is found and nothing is named that isn't one,
  including for a plan where one vendor hosts both, or where the backend serves the built
  frontend itself. Where the database is kept is not part of it.
- **cases:**
  - `gap`: a plan that leaves a part with no host
  - `mismatch`: a plan that puts a part on a host that cannot run it
  - `all-covered`: a plan where both parts are covered and nothing should be named
  - `one-vendor-both`: a plan where one vendor hosts both parts
  - `backend-serves`: a plan where the backend sends the built frontend itself
- **taught elsewhere:** session 11

### `c-check-vendor-claims`

- **goal:** find out whether what an agent says about a hosting vendor is true today
- **criterion:** Given a claim an agent made about a hosting vendor's free tier, finds on the
  vendor's own current pages the sentence that settles it, and says whether the claim still
  holds. Opening a deep link the agent gave to the vendor's page, and reading the sentence there,
  counts. Taking the agent's word for it, or a blog post's or a forum's, does not meet it, and
  neither does asking the agent whether it is sure.
- **taught elsewhere:** session 11

### `c-weigh-hosting-plans`

- **goal:** choose between hosting plans for an app, knowing what each would cost
- **criterion:** Given two hosting plans for an app's frontend and backend, one putting both with
  a single vendor and one using a separate vendor for each, and each vendor's free-tier terms,
  says for each plan whether the app sleeps when idle, what happens when it passes a limit, and
  whether a credit card is required and what having one on file risks; says what the extra
  vendor adds in accounts, secrets and places to look when something breaks, and
  how hard each plan would be to move to another vendor; and chooses one and states the strongest
  case the terms give for the plan they didn't choose. It passes when each of these is stated as
  the terms give it, the case for the other plan rests on a difference that matters for a class
  project with few users, and nothing is named that the terms don't support. Which plan they
  choose is not part of it, and neither is where the database is kept.
- **cases:**
  - `free-limits`: whether each plan sleeps, what happens past a limit, and whether a card is
    required and what one on file risks
  - `vendor-count`: what the extra vendor adds, and how hard each plan is to move
  - `other-case`: choosing a plan and making the strongest case for the other
- **taught elsewhere:** session 11

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation

### `w-deploy`

- **goal:** deploy
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** putting the app where anyone's browser can reach it
- **nearest confusable:** build
- **synonyms:** ship, go live

### `w-build`

- **goal:** build
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** turning your code into what gets sent to the hosts
- **synonyms:** production build

### `w-static-host`

- **goal:** static host
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a host that hands out the frontend's files as they are
- **nearest confusable:** server host
- **synonyms:** static site hosting

### `w-server-host`

- **goal:** server host
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a host that keeps your backend running
- **synonyms:** app host, web service

### `w-database-host`

- **goal:** database host
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** where the app's data is kept once it leaves your laptop
- **nearest confusable:** server host
- **synonyms:** managed database

### `w-free-tier`

- **goal:** free tier
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what a vendor lets you use without paying, up to a limit
- **nearest confusable:** free trial
- **synonyms:** free plan, hobby plan

### `w-idle-sleep`

- **goal:** sleep
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a free app being switched off while nobody is using it
- **nearest confusable:** a crash
- **synonyms:** spin down, scale to zero

### `w-cold-start`

- **goal:** cold start
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the wait while a sleeping app wakes for its first request
- **nearest confusable:** a slow server
- **synonyms:** spin-up time

### `w-overage`

- **goal:** overage
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** use past what your plan includes, and the charge for it
- **nearest confusable:** hitting a limit that pauses the app
- **synonyms:** overage charges

### `w-lock-in`

- **goal:** lock-in
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what it would cost you to move to another vendor
- **nearest confusable:** a contract
- **synonyms:** vendor lock-in

### `w-domain`

- **goal:** domain
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the name people type to reach your app
- **nearest confusable:** a URL
- **synonyms:** domain name

### `w-dns`

- **goal:** DNS
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the lookup from a name to where the app is
- **nearest confusable:** a domain
- **synonyms:** Domain Name System

### `w-https`

- **goal:** HTTPS
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the padlock in the address bar
- **nearest confusable:** HTTP
- **synonyms:** TLS, SSL

### `w-cdn`

- **goal:** CDN
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** copies of your files kept close to wherever the visitor is
- **nearest confusable:** static host
- **synonyms:** content delivery network, edge network

### `w-instance`

- **goal:** instance
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** one running copy of your app on a host's machine
- **nearest confusable:** server host
- **synonyms:** dyno
