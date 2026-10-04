# Learning goals: cloud hosting

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

### `c-place-app-parts`

- **goal:** say which kind of host the frontend and the backend each need, and whether a hosting
  plan covers them
- **criterion:** Given an app with a React frontend and an Express backend, and a hosting plan
  listing each vendor and what it offers, says which part each vendor would host, and names any
  part the plan leaves without a host or puts on a host that cannot run it, or says both are
  covered. It passes when every gap and mismatch is found and nothing is named that isn't one,
  including for a plan where one vendor hosts both, or where the backend serves the built
  frontend itself. Where the database is kept is not part of it.
- **origin:** course

### `c-check-vendor-claims`

- **goal:** find out whether what an agent says about a hosting vendor is true today
- **criterion:** Given an agent's answer comparing hosting vendors, says how they would find out
  which of its claims about free tiers, limits and credit cards still hold. It passes when what
  they describe checks each claim against the vendor's own current pages, not against the
  agent, a blog post or a forum; would catch a free tier the vendor has since withdrawn, a limit
  that has changed, and a credit card requirement the answer left out; and says what they would
  add to the prompt so that every claim in the next answer comes with what they need to check it.
  Asking the agent whether it is sure does not meet it.
- **origin:** course

### `c-weigh-hosting-plans`

- **goal:** choose between hosting plans for an app, knowing what each would cost
- **criterion:** Given two hosting plans for the same app, one putting the frontend and backend
  with a single vendor and one using a separate vendor for each, along with each vendor's
  free-tier terms, chooses one and says why. It passes when they name each difference in the terms that
  would matter for a class project with few users (whether the app sleeps, what happens when it
  passes a limit, whether a credit card is required and what having one on file risks, whether
  their agent can reach the host to change its settings and read its logs, and how hard it would
  be to move); say what the extra vendors add in accounts, secrets and places to
  look when something breaks; name nothing the terms don't support; and state the strongest case
  for the plan they didn't choose. Which plan they choose is not part of it, and neither is where
  the database is kept.
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

### `w-deploy`

- **goal:** deploy
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** putting the app where anyone's browser can reach it
- **nearest confusable:** build
- **synonyms:** ship, go live
- **origin:** course

### `w-build`

- **goal:** build
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** turning your code into what gets sent to the hosts
- **nearest confusable:** deploy
- **synonyms:** production build
- **origin:** course

### `w-static-host`

- **goal:** static host
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a host that hands out the frontend's files as they are
- **nearest confusable:** server host
- **synonyms:** static site hosting
- **origin:** course

### `w-server-host`

- **goal:** server host
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a host that keeps your backend running
- **nearest confusable:** static host
- **synonyms:** app host, web service
- **origin:** course

### `w-database-host`

- **goal:** database host
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** where the app's data is kept once it leaves your laptop
- **nearest confusable:** server host
- **synonyms:** managed database
- **origin:** course

### `w-free-tier`

- **goal:** free tier
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what a vendor lets you use without paying, up to a limit
- **nearest confusable:** free trial
- **synonyms:** free plan, hobby plan
- **origin:** course

### `w-idle-sleep`

- **goal:** sleep
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a free app being switched off while nobody is using it
- **nearest confusable:** a crash
- **synonyms:** spin down, scale to zero
- **origin:** course

### `w-cold-start`

- **goal:** cold start
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the wait while a sleeping app wakes for its first request
- **nearest confusable:** a slow server
- **synonyms:** spin-up time
- **origin:** course

### `w-overage`

- **goal:** overage
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** use past what your plan includes, and the charge for it
- **nearest confusable:** hitting a limit that pauses the app
- **synonyms:** overage charges
- **origin:** course

### `w-lock-in`

- **goal:** lock-in
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what it would cost you to move to another vendor
- **nearest confusable:** a contract
- **synonyms:** vendor lock-in
- **origin:** course

### `w-domain`

- **goal:** domain
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the name people type to reach your app
- **nearest confusable:** a URL
- **synonyms:** domain name
- **origin:** course

### `w-dns`

- **goal:** DNS
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the lookup from a name to where the app is
- **nearest confusable:** a domain
- **synonyms:** Domain Name System
- **origin:** course

### `w-https`

- **goal:** HTTPS
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the padlock in the address bar
- **nearest confusable:** HTTP
- **synonyms:** TLS, SSL
- **origin:** course

### `w-cdn`

- **goal:** CDN
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** copies of your files kept close to wherever the visitor is
- **nearest confusable:** static host
- **synonyms:** content delivery network, edge network
- **origin:** course

### `w-instance`

- **goal:** instance
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** one running copy of your app on a host's machine
- **nearest confusable:** server host
- **synonyms:** dyno
- **origin:** course
