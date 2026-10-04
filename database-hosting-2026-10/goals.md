# Learning goals: database hosting

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

_Yours to fill in. The course supplies one occasion: Problem Set 3, which puts your Problem Set 2
app, and the data in its SQLite database, on the public internet. Name any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Get your app's database deployed, and then change its tables without losing what is
there.** Not writing SQL or migrations, and not setting up the database yourself. When your agent
deploys your app, and again whenever a new feature needs new tables, it hands you a plan and says
the data is safe. This topic is enough to catch what that plan leaves out: where the data will
live, what goes into the production database and what stays in development, and what has to
happen, in what order, before a change to the tables reaches real users' data.

What sits past that line: choosing hosts and comparing free tiers in general belong to
cloud-hosting, and keeping the connection string and the database's password out of your code
belongs to config-and-secrets. Deploying automatically and debugging a deployed app come in
session 12, sign-in and any table of users it needs in session 13, and defending the app in
session 14.

## Goals

<!--
  ONE LIST, one entry per goal, whatever kind of goal it is. A capability, a word and an
  orientation are the same kind of thing here and reach every tool through one code path;
  what differs between them is which SLOTS they carry.

  THE EIGHT SLOTS, what each one asks, and every value in use, are in
  workflows/learn/skills/goal-setting/references/slots.md. Read it before writing a slot you haven't written
  before; a value nothing implements is refused at read time, by name. Every slot takes exactly
  one value.

  EVERY SLOT DEFAULTS, and an ordinary capability carries none of them:

      ### `c-read-unseen-diagram`

      - **goal:** read a diagram I haven't seen and say what it claims
      - **criterion:** given an unseen diagram, names every element and says what the flow
        does, including what it rules out

  That is a complete entry. `criterion` is the only field an ordinary capability writes, and
  it is the one that does the work: it may need a judgment call when the time comes — most
  will — but it has to say what's being examined, or whoever checks it later invents the
  object as well as the verdict.

  A WORD carries four slots, and workflows/learn/tools/new-word.mjs writes them for you. Don't type them:

      ### `w-schema`

      - **goal:** schema
      - **criterion:** vocabulary
      - **supply:** vocabulary
      - **bar:** one production pass
      - **group:** vocabulary
      - **what it names:** the promised shape of the thing, not the thing
      - **nearest confusable:** type
      - **synonyms:** DDL

  The last three are not slots — they are INPUTS TO THE VOCABULARY SUPPLY, which reads them
  when it instantiates a move. DEFINE checks against *what it names* and rejects a bare
  synonym as an answer; DISTINGUISH needs the confusable and is never aimed at a synonym;
  INTERPRET may set its sentence using one. Any future supply will want its own fields, and
  they go the same way: bullets nothing else reads.

  WHAT IT NAMES is a pointer, not a definition — "the promised shape", not what a schema is.
  Topology, the same latitude the interview has: enough to recognize the word when it turns
  up, never enough to pass DEFINE with.

  NEAREST CONFUSABLE is one or more things the word sometimes gets confused with. Optional,
  and OMIT THE LINE rather than leaving it empty: an empty optional field is a default written
  down. The agent supplies it from its own knowledge rather than asking the learner.

  SYNONYMS are OTHER NAMES for the same thing, the ones a learner will meet outside this
  course. Optional on the same terms: omit the line when there is none. They do three jobs.
  DEFINE rejects one as an answer, because "an AI agent is a bot" names the thing again rather
  than saying what it is. DISTINGUISH is never aimed at one: there is no difference to name,
  so a learner who says exactly that would be right and would fail anyway. And INTERPRET may
  set its unseen sentence using one, so the word has to be recognised under a name the lecture
  never used.

  Put only names here. A phrase that reads like a definition rather than a label is not a
  synonym, and DEFINE would then reject the very answer it should accept.

  A word may carry a further line where this learner has a specific wrong idea waiting for
  them — `- **watch for:** thinks an API key is a password`. Rare. It is a HINT TO WHOEVER
  SETS THE MOVE, not an extra thing to satisfy: aim a CATCH or a DISTINGUISH at it and the
  confusion gets tested by the ordinary bar.

  Words are APPEND-ONLY and adding one is not a revision of these goals. A word that turns up
  mid-topic gets an entry and nothing else happens. That matters: hitting a word you don't
  have is the commonest way a topic grows, and it must not cost a goal-setting session.

  GIVING ONE UP IS NOT A DELETION EITHER. A learner who decides a word doesn't matter gets a
  `retired` line in the status log naming it — `record-status.mjs <topic> retired <goal-id>
  --reason "…"` — and the entry stays here untouched. It stops being offered, stops coming
  back in review and leaves its group's fraction, and the attempts it already has stay in the
  log pointing at an id that is still where they left it. Removing the entry instead would
  orphan those lines, which survey reports as a problem.

  If meeting the vocabulary bar would leave them unable to do the thing, it isn't a word —
  it's a capability, and it gets an ordinary entry with a criterion someone thought about.

  THE ORIENTATION ENTRY is shipped below, filled in, in every topic. It carries five slots and
  they are not yours to change. Delete it only if `what I already have` says this learner has
  seen the area laid out before; then say so there and let curation write
  `n/a — already oriented`.

  HOW MANY CAPABILITY ENTRIES. Usually one is enough — a second means the use needs a
  genuinely separate ability, not a restatement of the first. Past about three, something has
  been scoped wrong.

  THE ABSENCE OF ANY CAPABILITY ENTRY IS LOAD-BEARING. "This file has no goal in the default
  group" is what the rest of the workflow reads as *goal setting hasn't happened* — it's the
  state add-topic leaves, and it's what routes a topic to goal setting. Words and the
  orientation entry are in their own groups and don't count towards it. So never write a
  placeholder capability entry; an empty section is the honest signal.
-->

### `c-plan-first-deploy`

- **goal:** say what has to be in place for an app's database the first time it is deployed
- **criterion:** Given an app that ran on localhost with a SQLite file, and an agent's plan for
  deploying it for the first time, names every step the plan is missing or gets wrong, or says
  that none is. It passes when they catch a plan that keeps the data in a file on a disk the host
  wipes; one that uses the development database as production, or copies its test rows across;
  one that has the tables made by hand instead of by the code's migrations running on deploy; one
  that puts the test fixtures into production instead of only the seed data the app needs to
  start; and one with no check, from the deployed app after a redeploy, that what was put in is
  still there. They must name nothing that isn't a problem. Setting the connection string, and
  keeping the database's password out of the repository, are not part of it.
- **origin:** course

### `c-plan-migration`

- **goal:** say what has to happen to change the tables of a deployed app that holds data
- **criterion:** Given a change to the tables of a deployed app that already holds users' data,
  and an agent's plan for making it, names every step the plan is missing or has in the wrong
  order, or says that none is. It passes when they require the migration to be tried first on a
  development database holding a copy of production; a backup of production taken just before,
  and a way back by restoring it; the migration run as part of the deploy, before the new code
  answers requests; and a check afterwards, from the deployed app, that the data already there
  survived. They must also ask whether the app has to be stopped while the migration runs;
  answering that is not part of it. They must name nothing that isn't a problem. Writing the
  migration is not part of it.
- **origin:** course

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation
- **origin:** course

### `w-sqlite`

- **goal:** SQLite
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a database that is a single file the backend opens itself
- **nearest confusable:** Postgres
- **origin:** course

### `w-postgres`

- **goal:** Postgres
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a database that runs as a program of its own, which the backend connects to
- **nearest confusable:** SQL
- **synonyms:** PostgreSQL
- **origin:** course

### `w-ephemeral-disk`

- **goal:** ephemeral disk
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a server's file storage that starts empty again whenever the host replaces the server
- **nearest confusable:** persistent volume
- **synonyms:** ephemeral filesystem, ephemeral storage
- **origin:** course

### `w-persistent-volume`

- **goal:** persistent volume
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** file storage space attached to a server that outlasts the server being replaced
- **nearest confusable:** database host
- **synonyms:** volume, persistent disk
- **origin:** course

### `w-redeploy`

- **goal:** redeploy
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** putting a new version of the app on its hosts in place of the running one
- **nearest confusable:** restart
- **origin:** course

### `w-seed-data`

- **goal:** seed data
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the rows your code puts in when a database is first set up
- **nearest confusable:** fixture
- **synonyms:** initial data
- **origin:** course

### `w-production`

- **goal:** production
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the copy of the app that real users use, along with its data
- **nearest confusable:** development
- **synonyms:** prod, live
- **origin:** course

### `w-backup`

- **goal:** backup
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a copy of the data as it stood at one moment, kept apart from the database
- **nearest confusable:** a commit of the code
- **synonyms:** snapshot, database dump
- **origin:** course

### `w-restore`

- **goal:** restore
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** putting a backup's data back into a working database
- **nearest confusable:** backup
- **origin:** course

### `w-downtime`

- **goal:** downtime
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a stretch when the app is deliberately stopped, so nobody can use it
- **nearest confusable:** sleep
- **synonyms:** maintenance window
- **origin:** course

### `w-rollback`

- **goal:** rollback
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** going back to the version that worked after a change goes wrong
- **nearest confusable:** restore
- **synonyms:** revert, roll back
- **origin:** course
