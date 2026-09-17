# Learning goals: coding agents

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

_Yours to fill in. The course seeded this topic, so only you can say how it reached you._

<!-- Which of A / B / C / D, and the answer to the follow-up. -->

## What I already have

_Yours to fill in. Say where your knowledge stops, not what you have heard of._

<!--
  The nearest thing already known well, and where it stops.
  This is a claim, not a verified fact — it's a self-report about one's own knowledge,
  and the assessment may contradict it.
-->

## What I'll use it for

_Yours to fill in. The course supplies two occasions: you say what your app cost when you demo
it in session 8, and you build PS2 on the same $50 a month as everything else this term. Name
any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Judge a situation with a few rules of thumb, and ask the agent for the numbers.** Enough to
decide, partway through real work, whether a better model is worth trying and whether to split
work off, and to get a cost estimate you can trust. Not estimating costs by hand, not setting up
an agent beyond choosing its model, and nothing about how a model works inside.

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

<!--
  No orientation goal, on purpose. The course removed it when seeding this topic: a general
  reading about coding agents would distract more than orient.
-->

### `c-choose-model`

- **goal:** tell when a better model might be worth trying, and when it is not
- **criterion:** given a few short situations from work with an agent, some where a better
  model is worth trying and some where it is not, says which is which and gives a
  reason for each that comes from the situation described. A general preference for cheaper,
  or for better, does not meet it.

### `c-split-chats`

- **goal:** tell when to split work off into a new chat or a subagent, and when to keep going
- **criterion:** given a few short situations partway through work with an agent, some where
  splitting helps and some where it would lose something the next step needs, says which is
  which. When arguing for a split, names a reason that applies (independence/fresh start vs. saving
  tokens) and ties it to something in the situation. Naming a reason without that tie does not
  meet it.

### `c-ask-cost-estimate`

- **goal:** ask an agent what a piece of agent work cost
- **criterion:** Can ask the agent to estimate what a run that has already happened cost, such
  as one chat. Can say what the figure it gives back is based on: which model's prices, and
  which token counts. Can say why that figure may differ from what was actually billed. "It's
  only an estimate" does not meet it.

### `w-token`

- **goal:** token
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the unit text is counted and billed in
- **nearest confusable:** word

### `w-input-tokens`

- **goal:** input tokens
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the part of a turn's bill for what the model was sent
- **nearest confusable:** output tokens
- **synonyms:** prompt tokens

### `w-output-tokens`

- **goal:** output tokens
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the part of a turn's bill for what the model wrote
- **nearest confusable:** input tokens
- **synonyms:** completion tokens

### `w-prompt-caching`

- **goal:** prompt caching
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** why input sent again can cost less than new input
- **nearest confusable:** memory
- **synonyms:** context caching

### `w-model`

- **goal:** model
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what the price table is priced by, as distinct from the program you talk to
- **nearest confusable:** agent
- **synonyms:** LLM

### `w-reasoning-effort`

- **goal:** reasoning effort
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the dial set separately from which model you picked
- **nearest confusable:** model
- **synonyms:** thinking level

### `w-context`

- **goal:** context
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what the model has in front of it on a turn, which is more than what you
  typed
- **nearest confusable:** memory
- **watch for:** thinks the model remembers earlier chats

### `w-context-window`

- **goal:** context window
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the ceiling on how much context fits
- **nearest confusable:** context
- **synonyms:** context length, context limit

### `w-compaction`

- **goal:** compaction
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what happens to a chat that nears its ceiling
- **nearest confusable:** starting a new chat
- **synonyms:** auto-compact

### `w-system-prompt`

- **goal:** system prompt
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the instructions sent ahead of anything you type
- **nearest confusable:** your first message, AGENTS.md
- **synonyms:** system message, developer instructions
