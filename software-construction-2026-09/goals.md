# Learning goals: software construction

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

_Yours to fill in. The course supplies two occasions: the in-class lab where your agent adds a
server and a database to your app, and Problem Set 2. In both, Superpowers tests and reviews the
work between agents, and you step in when it asks you to check something, when it finishes, and
when what it built is not what you wanted. Name any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Know when to step in, and what to ask.** Not authoring, and not auditing either. With
Superpowers, writing tests, running them, reviewing the work and acting on the reviews all happen
between agents, and it is built not to stop and ask you. You will not write a test, read test
code, or read the reports its agents pass to each other.

You step in at a few moments: when the agent asks you to check something by hand, when the run
ends and it lists the decisions it made on your behalf, when you try what it built and it is not
what you wanted, and, rarely, when it hits a failure it could not resolve. What this topic buys is
enough to act well at those moments: telling whether a check handed to you really needs a person,
and asking whether something was tested and recognizing a hollow answer. When what it built is
not what you wanted, you describe it the way the React apps topic practiced, and finding the cause
is the agent's job. Diagnosing the problem yourself, and debugging by hand, are past that line.

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

### `c-ask-tested`

- **goal:** ask whether something was tested, and tell a real answer from a hollow one
- **criterion:** Given one thing the app should do and the agent's answer to "has this been
  tested?", says whether the answer shows a test that would fail if that one thing broke, or that
  it can't tell from the answer. It is judged on what the answer says, not on the test code.
  Unless the answer settles it, says what to ask the agent next: a question whose honest answer
  has to name one test and what it checks, or say there is none. An answer about the whole suite,
  such as "all 24 tests pass", is not an answer about one thing. Nor is a named test that would
  still pass if that one thing broke, such as one that checks a note was accepted without checking
  it was saved, or one that runs against a mock instead of the real database.

### `c-judge-manual-test`

- **goal:** tell when a check really needs a person, and when the agent should automate it
- **criterion:** Given an agent's request to test something in the app by hand, says whether a
  program could do the check instead, for example the agent driving a headless browser. If it
  could, says what the automated test would do in the app and what it would check, well enough
  that the agent could write it. If it could not, names what the check needs that only a person
  can supply. "Automate it", with no account of what the test would check, does not meet it.

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation

### `w-tdd`

- **goal:** test-driven development
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a rule about which gets written first, the test or the code
- **nearest confusable:** writing tests
- **synonyms:** TDD, test-first development, red-green-refactor

### `w-failing-test`

- **goal:** failing test
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a test's verdict that is not always bad news
- **nearest confusable:** a broken test
- **synonyms:** red test

### `w-regression`

- **goal:** regression
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a step backwards, caused by a change
- **nearest confusable:** a new bug; regression in statistics

### `w-mock`

- **goal:** mock
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what a test puts where the real database or service would be
- **nearest confusable:** a test dataset
- **synonyms:** stub, fake, test double

### `w-code-review`

- **goal:** code review
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a second reader's pass over a change before it is accepted
- **nearest confusable:** testing
- **synonyms:** review

### `w-spec-review`

- **goal:** spec compliance review
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the review that asks whether the change does what was asked
- **nearest confusable:** code quality review
- **synonyms:** spec review

### `w-root-cause`

- **goal:** root cause
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the reason underneath, not the thing you noticed first
- **nearest confusable:** the symptom

### `w-test-suite`

- **goal:** test suite
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** everything that runs when the agent says it ran the tests
- **synonyms:** the tests

### `w-test-coverage`

- **goal:** test coverage
- **criterion:** vocabulary
- **supply:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** how much of the code the tests reach
- **nearest confusable:** how well tested the code is
- **synonyms:** code coverage, coverage
