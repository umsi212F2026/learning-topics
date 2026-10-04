# Learning goals: database hosting

**origin:** course

**What I want to be able to do, and what would count as having got there.**

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

_Yours to fill in. The course supplies one occasion: Problem Set 3, which puts your Problem Set 2
app, and the data in its SQLite database, on the public internet. Name any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Get your app's database deployed so its data survives.** Not writing SQL or migrations, and
not setting up the database yourself. When your agent deploys your app, it hands you a plan and
says the data is safe. This topic is enough to catch what that plan leaves out: where the data
will live, and what goes into the production database and what stays in development.

What sits past that line: choosing hosts and comparing free tiers in general belong to
cloud-hosting, and keeping the connection string and the database's password out of your code
belongs to deploy-config. Deploying automatically and debugging a deployed app come in
session 12, sign-in and any table of users it needs in session 13, and defending the app in
session 14.

## Sequence

1. orientation
2. vocabulary
3. capabilities

## Goals

### `c-catch-data-loss`

- **goal:** catch a first-deploy plan whose data won't survive a redeploy
- **criterion:** Given an agent's plan for deploying an app's database for the first time whose
  data will not survive a redeploy, and the host's rule for what it keeps, says that it won't and
  names the step that decides it. It passes when they say no and tie it to that step. For a plan
  that never says where the database lives, "no" or "can't tell", with that omission named,
  passes.
- **capability:** plan-first-deploy
- **taught elsewhere:** session 11 table activity

### `c-clear-data-survives`

- **goal:** recognise a first-deploy plan whose data will survive a redeploy
- **criterion:** Given an agent's plan for deploying an app's database for the first time whose
  data will survive a redeploy, and the host's rule for what it keeps, says that it will and names
  the step that puts the data somewhere the host keeps. It passes when they say yes and name that
  step. Faulting the plan on survival fails it.
- **capability:** plan-first-deploy
- **taught elsewhere:** session 11 table activity

### `c-catch-copied-database`

- **goal:** catch a first-deploy plan that copies or shares production's database
- **criterion:** Given an agent's plan for deploying an app's database for the first time in which
  production's database is copied from the laptop or shared with development, says that production
  does not get a database of its own, built by the code, and names the step that decides it. It
  passes when they say no and tie it to that step.
- **capability:** plan-first-deploy
- **taught elsewhere:** session 11 table activity

### `c-clear-own-database`

- **goal:** recognise a first-deploy plan that gives production a database of its own, built by
  the code
- **criterion:** Given an agent's plan for deploying an app's database for the first time in which
  production gets a database of its own, built by the code, says that it does and names the step
  that builds it. It passes when they say yes and name that step. A seed script kept in the code
  and run once against production counts as built by the code; faulting it, or faulting the plan
  on this question in any other way, fails it.
- **capability:** plan-first-deploy
- **taught elsewhere:** session 11 table activity

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation

### `w-sqlite`

- **goal:** SQLite
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a database that is a single file the backend opens itself
- **nearest confusable:** Postgres

### `w-postgres`

- **goal:** Postgres
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a database that runs as a program of its own, which the backend connects to
- **nearest confusable:** SQL
- **synonyms:** PostgreSQL

### `w-ephemeral-disk`

- **goal:** ephemeral disk
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a server's file storage that starts empty again whenever the host replaces the server
- **nearest confusable:** persistent volume
- **synonyms:** ephemeral filesystem, ephemeral storage

### `w-persistent-volume`

- **goal:** persistent volume
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** file storage space attached to a server that outlasts the server being replaced
- **nearest confusable:** database host
- **synonyms:** volume, persistent disk

### `w-redeploy`

- **goal:** redeploy
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** putting a new version of the app on its hosts in place of the running one
- **nearest confusable:** restart

### `w-seed-data`

- **goal:** seed data
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the rows your code puts in when a database is first set up
- **nearest confusable:** test data
- **synonyms:** initial data

### `w-production`

- **goal:** production
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the copy of the app that real users use, along with its data
- **nearest confusable:** development
- **synonyms:** prod, live
