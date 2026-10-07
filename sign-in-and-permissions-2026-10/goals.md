# Learning goals — sign in and permissions

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

  THE ORIGIN LINE. Only a topic the course ships carries one, as `**origin:** course` on its
  own line between the title above and `## Goals`. Leave it out of a topic you built yourself:
  absent means `learner`. Every goal inherits the topic's origin unless it carries an
  `- **origin:**` of its own, which is how a goal a student adds to a course topic stays
  theirs. survey.mjs reports a header value that is neither `course` nor `learner`.

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

_Yours to fill in. The course supplies one occasion: Part B of Problem Set 3, where your app's
single password gives way to sign-in through Google or GitHub, and you decide who may do what.
Name any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Get sign-in and permissions into your app with your agent, and check that they hold.** Not
writing the sign-in code yourself, and not building a password system of your own. Your agent
can register your app with Google or GitHub and write the code that signs people in. This topic
is enough to follow what happens when someone signs in, to decide who may do what in your app and
catch a plan that wouldn't really enforce it, to keep the sign-in secret out of places it can
leak, and to know which requests would show that the rules hold.

What sits past that line: how tokens are built and signed, and cryptography. Sign-in that works on
localhost and fails on the live app is a job for your agent with the host's logs, as in
debug-deployed. Defending a live app against abuse belongs to session 14.

<!--
  Which of: recognize it / read it / modify something existing / author from scratch /
  judge someone else's work. One line on why that's enough.
-->

## Sequence

<!--
  THE ORDER THE GOALS ARE TACKLED IN, decided by goal-setting. One numbered line per set,
  earliest first, and no preferred order inside a set: the tutor chooses among a set's open
  goals at random. Study offers from the first set that still has an open goal, and a learner
  who wants a goal from a later set just says so.

  THIS SECTION SITS ABOVE `## Goals` ON PURPOSE. The end of the file is then always the end of
  Goals, so a goal appended there (new-word.mjs does) is never lost inside this section. Write
  new entries under `## Goals`; a `###` entry written here is not read as a goal, and survey.mjs
  says so.

  AN ITEM IS A GROUP (`vocabulary`), A CAPABILITY SLUG (`weigh-hosting-plans`, naming all of
  that capability's parts) OR A GOAL ID (`c-weigh-sleep`), separated by commas, backticks
  allowed:

      2. vocabulary, c-weigh-sleep

  THE MOST SPECIFIC MENTION WINS. A goal goes in the set that lists its id; failing that, the
  set that lists its capability slug; failing that, the first set that lists its group. So a
  capability named by id can sit with the words, and a word named by id can come last. A word
  added mid-topic lands wherever its group is listed, with no edit here. Any item listed in
  two sets is reported: a goal can't be in two places, and a second mention of a slug or a
  group can never place anything, since the first already has.

  EVERY GOAL MUST LAND IN A SET. There is no catch-all, and a goal named nowhere is a problem
  survey.mjs reports, as it does an item that matches nothing and an item listed in two sets.
  The three standard groups, orientation, vocabulary and capabilities, may stay listed
  while nothing is in them yet; any other name has to match a group, slug or goal. A topic
  with no Sequence section at all is a decision not yet made, not a problem: it is worked in
  the order orientation, vocabulary, capabilities, then any other group, until goal-setting
  writes the section.
-->

1. orientation
2. vocabulary
3. capabilities

## Goals

<!--
  ONE LIST, one entry per goal, whatever kind of goal it is. A capability, a word and an
  orientation are the same kind of thing here and reach every tool through one code path;
  what differs between them is which SLOTS they carry.

  THE EIGHT SLOTS, what each one asks, and every value in use, are in
  workflows/learn/skills/goal-setting/references/slots.md. Read it before writing a slot you haven't written
  before; a value nothing implements is refused at read time, by name. Every slot takes exactly
  one value.

  EVERY SLOT DEFAULTS, and an ordinary capability carries none of them (the eighth, `capability`,
  has no default value: it is simply absent unless you write it):

      ### `c-read-unseen-diagram`

      - **goal:** read a diagram I haven't seen and say what it claims
      - **criterion:** given an unseen diagram, names every element and says what the flow
        does, including what it rules out

  That is a complete entry. `criterion` is the only field an ordinary capability writes, and
  it is the one that does the work: it may need a judgment call when the time comes — most
  will — but it has to say what's being examined, or whoever checks it later invents the
  object as well as the verdict.

  A WORD carries three slots, and workflows/learn/tools/new-word.mjs writes them for you. Don't type them:

      ### `w-schema`

      - **goal:** schema
      - **criterion:** vocabulary
      - **bar:** one production pass
      - **group:** vocabulary
      - **what it names:** the promised shape of the thing, not the thing
      - **nearest confusable:** type
      - **synonyms:** DDL

  The last three are not slots. They are INPUTS TO THE `a-words` GENERATOR, which reads them
  when it instantiates a move. DEFINE checks against *what it names* and rejects a bare
  synonym as an answer; DISTINGUISH needs the confusable and is never aimed at a synonym;
  INTERPRET may set its sentence using one. Any future generator that wants its own fields
  puts them the same way: bullets nothing else reads.

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

  ANY GOAL may carry `- **taught elsewhere:** PS2; session 5 in-class activity`, naming where
  else it is taught. The instructor writes it on assigned topics, and goal setting writes it
  when a learner says something is covered in class. It is not a slot and TOOLS IGNORE IT; only
  the tutor reads it, to offer the learner the choice of learning the goal there. Omit the line
  when there is nothing to name.

  A CAPABILITY SPLIT INTO PARTS. When one criterion could only be checked with a very long
  question, write the capability as several goals, each with its own criterion, and give them
  the same `- **capability:** read-unseen-diagram` slug: two to four lower-case words, hyphens,
  no prefix. They stay ordinary goals in their group, met and reviewed one by one; survey
  prints them together under the slug with a fraction. One part alone is reported, since a
  group of one is just a goal.

  CASES, WHEN ONE CRITERION JOINS SEVERAL. A criterion that says "and" or "including", or is
  two-sided (decline the risky, allow the safe), is met by one pass on its easiest case unless
  the cases are named. Name them in a `cases` slot right after `criterion`, one sub-bullet each:
  a backticked id, a colon, one line saying what the case is.

      - **criterion:** given a request, declines one that would expose a secret and goes
        ahead with one that wouldn't
      - **cases:**
        - `declines-risky`: a request that would put a secret in the chat or a file
        - `allows-safe`: a request involving no secret

  A case id is one to three lower-case words with hyphens, unique within its goal, and
  permanent once attempts point at it, like a goal id. The criterion stays prose; the cases
  say which parts of it must each be shown. THE GOAL'S OWN BAR MUST HOLD FOR EACH CASE, so the
  goal is met once every case has been passed. It is still one goal with one review clock.
  Reach for cases before a `capability:` split: split only when the parts are genuinely
  separate skills, each worth reviewing on its own. survey.mjs reports a malformed or
  duplicate id and a slot left empty.

  THE ORIENTATION ENTRY is shipped below, filled in, in every topic. It carries six slots and
  they are not yours to change. Delete it only if `what I already have` says this learner has
  seen the area laid out before; then say so there and let curation write
  `n/a: already oriented`.

  HOW MANY CAPABILITIES. Usually one is enough: a second means the use needs a genuinely
  separate ability, not a restatement of the first. Past about three, something has been scoped
  wrong. A capability split into parts that share a `capability:` slug counts once, and a goal
  with no slug counts as one.

  THE ABSENCE OF ANY CAPABILITY ENTRY IS LOAD-BEARING. "This file has no goal in the default
  group" is what the rest of the workflow reads as *goal setting hasn't happened* — it's the
  state add-topic leaves, and it's what routes a topic to goal setting. Words and the
  orientation entry are in their own groups and don't count towards it. So never write a
  placeholder capability entry; an empty section is the honest signal.
-->

### `c-set-up-sign-in`

- **goal:** work with an agent to add sign-in through Google or GitHub to an app, on localhost
  and on the live app
- **criterion:** Given an agent's plan for adding sign-in through Google or GitHub to a described
  app whose frontend and backend are on separate hosts, says which steps are theirs to do and what
  they would change before agreeing to it. It passes when they say that they register the app
  with the provider themselves, which gives them a client ID and a client secret; give the
  provider a redirect URL for localhost and another for the live app, and with GitHub, which
  allows only one per registered app, register the app twice; put the client secret into the
  backend host's settings themselves rather than hand it to the agent, while the client ID may go
  in the frontend; catch a plan that asks the provider for more of the user's account than the
  app needs, such as their repositories when the app only shows their name; and go along with a
  plan in which the backend trades the code the provider sends back for who the user is, and
  keeps the provider's id for that user rather than a password.
- **cases:**
  - `register-yourself`: who registers the app with the provider, and what that gives them
  - `two-redirects`: redirect URLs for localhost and the live app, including GitHub's one-per-app
    limit
  - `secret-placement`: where the client secret and the client ID each go
  - `too-much-scope`: a plan that asks for more of the user's account than the app needs
  - `sound-plan`: a plan whose backend trades the code for the user's identity and keeps their
    provider id
- **taught elsewhere:** session 13

### `c-review-permissions`

- **goal:** work with an agent to give an app levels of who may do what, and confirm that the
  server enforces them
- **criterion:** Given a table of who may do what in a described app and an agent's plan for
  enforcing it, says what they would change before agreeing to it, and how they would confirm
  afterwards that the rules hold. It passes when they catch a table that leaves out something one of its levels
  could try to do, such as deleting, or leaves out someone who isn't signed in at all; catch a
  plan that enforces a rule only in React, such as hiding the Edit button from everyone but the
  owner; catch a plan in which the server takes the user's word for who they are, such as a user
  id the frontend sends with the request, rather than the session; go along with a plan that
  checks every rule on the server against the signed-in user and keeps only the provider's id
  for each user and perhaps an email; and say which requests would confirm the rules, rather
  than what the page shows, and what each should get back: a request to a protected path with no
  sign-in is refused with 401, and a second account, signed in, is refused the owner's actions
  with 403.
- **cases:**
  - `incomplete-table`: a table missing an action, or missing someone who isn't signed in
  - `react-only`: a plan that enforces a rule only in the frontend
  - `trusts-frontend`: a plan whose server believes a user id the frontend sends
  - `sound-plan`: a plan that checks every rule on the server against the signed-in user
  - `confirm-401`: the request that would show someone not signed in is turned away
  - `confirm-403`: the request that would show a second account is refused the owner's actions
- **taught elsewhere:** session 13

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation

### `w-authentication`

- **goal:** authentication
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** finding out who someone is

### `w-authorization`

- **goal:** authorization
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** deciding what someone may do
- **nearest confusable:** authentication
- **synonyms:** permissions, access control

### `w-oauth`

- **goal:** OAuth
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the standard way an app lets you sign in with an account you already have elsewhere
- **nearest confusable:** basic auth; giving the app your Google password

### `w-identity-provider`

- **goal:** identity provider
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the outside service that vouches for who the user is, such as Google or GitHub
- **nearest confusable:** your host
- **synonyms:** IdP, sign-in provider

### `w-client-secret`

- **goal:** client secret
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the private value that proves to the provider a request comes from your app's server
- **nearest confusable:** client ID; the user's password

### `w-redirect-url`

- **goal:** redirect URL
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the address in your app the provider sends the user back to after signing in
- **nearest confusable:** the app's own URL
- **synonyms:** callback URL, redirect URI

### `w-scope`

- **goal:** scope
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** what your app asks the provider to let it see or do with the user's account
- **nearest confusable:** role

### `w-session`

- **goal:** session
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the server remembering that this browser has signed in, until sign-out or expiry
- **nearest confusable:** signing in

### `w-401`

- **goal:** 401
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the status code for a request from someone not signed in
- **synonyms:** Unauthorized
- **watch for:** takes the name Unauthorized to mean signed in but not allowed

### `w-403`

- **goal:** 403
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the status code for a request from someone signed in but not allowed to do this
- **nearest confusable:** 401; 404
- **synonyms:** Forbidden

### `w-role`

- **goal:** role
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a named level of what a group of users may do in your app
- **nearest confusable:** an account
- **synonyms:** permission level

### `w-rotate`

- **goal:** rotate
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** replacing a secret with a new one and making the old one stop working
- **nearest confusable:** deleting the secret from the repository

### `w-env-example`

- **goal:** .env.example
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a committed file listing the settings the app needs, without their real values
- **nearest confusable:** .env file
