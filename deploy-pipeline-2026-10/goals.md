# Learning goals: deploy pipeline

**origin:** course

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

_Yours to fill in. The course supplies one occasion: Problem Set 3, where your app deploys itself
each time you push, and which ends with a pull request adding your app to the class showcase. Name
any others you have._

<!--
  The use, and a concrete occasion.
  If several uses apply, rank them: the top one sets the depth, the rest are cut first
  when time runs short.
-->

## Depth

**Get your app deploying itself with your agent, and know why a change isn't showing up.** Not
writing the pipeline's configuration yourself, and not finding out why a failed deploy failed.
Your agent can connect your repository to your hosts so that each push to `main` redeploys the
app. This topic is enough to catch a setup that would put a secret where it can leak or deploy
without running your tests, to confirm the pipeline really works, to catch a setup whose deploys
would wipe production's data or leave its tables behind the code, to tell why a change you made
isn't in the live app yet, and to get your app into the class showcase through a pull request.

What sits past that line: reading a failed deploy's logs to find the cause belongs to
debug-deployed, and what to do about a secret that has already leaked to session 13.

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

### `c-set-up-auto-deploy`

- **goal:** work with an agent to make an app deploy itself on each push, and confirm that it
  does
- **criterion:** Given an agent's plan for making an app's frontend and backend deploy themselves
  whenever `main` is pushed to GitHub, says what they would change before agreeing to it, and how
  they would confirm afterwards that it works. It passes when they catch a plan that would put a
  secret into the repository, such as a value written into the code or a `.env` file that git
  will commit; catch a plan that puts a secret into a frontend setting, which the build copies
  into files every visitor's browser downloads; go along with a plan that keeps secrets in the
  backend host's settings and keeps a local `.env` file that `.gitignore` covers; for a plan that
  deploys through GitHub Actions, put the host's deploy token in the repository's GitHub secrets
  rather than in the workflow file; catch a plan whose deploy doesn't wait for the app's tests to
  pass, including one that runs them in GitHub Actions while the host deploys every push on its
  own, and ask for the deploy to wait; and would confirm the pipeline by pushing a small change
  that shows in the live app only once both the frontend and the backend have deployed it, such
  as new text the page gets from the backend, and seeing it there, not by taking the agent's word
  or the host's "deployed" message for it; and by pushing a change with a failing test and seeing
  that neither part deploys it.
- **cases:**
  - `secret-in-repo`: a plan that would put a secret into the repository
  - `frontend-secret`: a plan that would put a secret into a frontend setting
  - `sound-plan`: a plan that keeps secrets in the backend host's settings, with a local `.env`
    file that `.gitignore` covers
  - `deploy-token`: a plan that deploys through GitHub Actions with a token from the host
  - `no-test-gate`: a plan whose deploy doesn't wait for the tests, including one that runs them
    in GitHub Actions while the host deploys every push on its own
  - `confirm-live`: how they would confirm that a push reaches both parts of the live app
  - `confirm-gate`: how they would confirm that a push with a failing test reaches neither
- **taught elsewhere:** session 12 lab

### `c-find-missing-change`

- **goal:** find out why a change doesn't show up in the live app
- **criterion:** Given an app that deploys itself from `main` and a change that the live app
  doesn't show, says what they would look at first (git's output, the commit's checks on GitHub,
  the host's list of deploys, or the page in the browser), is shown it, and goes on until they
  can say why and what to do next. It passes when they name the right reason: the change
  never reached `main` on GitHub (not committed, not pushed, pushed to another branch, or waiting
  in a pull request nobody has merged), so get it there; the tests failed, so the host never
  deployed it, and the tests have to pass first; the deploy failed and the old version is still
  live, so look at that deploy; the browser is showing its own old copy, so reload without its
  cache; or the host's CDN is serving an old copy, so ask for a fresh one by changing the URL, such as adding `?v=2`, to see whether
  the new version is there, and clear the CDN's cache so that every visitor gets it; or a
  frontend setting was changed on the host after the last build, so the frontend has to be built
  again before it takes effect. Finding out why a deploy failed is not part of it.
- **cases:**
  - `not-pushed`: the change never left their machine (not committed, or not pushed)
  - `not-on-main`: the change is on GitHub but not on `main` (on another branch, or in a pull
    request nobody has merged)
  - `tests-failed`: the tests failed, so the host never deployed the change
  - `deploy-failed`: the deploy failed and the old version is still live
  - `browser-cache`: the browser is showing its own old copy
  - `cdn-cache`: the host's CDN is serving an old copy
  - `old-build-setting`: a frontend setting changed on the host since the last build
- **taught elsewhere:** session 12 class

### `c-showcase-pr`

- **goal:** get a change into a repository I can't push to, through a pull request
- **criterion:** Given a repository they can't push to, such as the class showcase, and a change
  to make in it, says how the change gets there with their agent's help: copy the repository
  into their own account, make the change on a branch of that copy, push it, and open a pull
  request from that branch into the original repository; and, once it is open, says what to do
  when one of its checks fails. It passes when they put the change in their own copy, not in
  the original or in their app's repository; open the pull request from their copy's branch
  into the original, not the other way round; and fix a failing check by pushing to the same
  branch, not by opening a new pull request.
- **cases:**
  - `where-to-push`: where the change goes before there is a pull request
  - `pr-direction`: which repository and branch the pull request goes from and into
  - `failing-check`: a check fails on their open pull request
- **taught elsewhere:** session 13 lab

### `c-deploy-keeps-data`

- **goal:** make sure a self-deploying app treats its production database on purpose
- **criterion:** Given an agent's plan for how an app that deploys itself on every push to `main`
  gives its production database its tables and starting rows, and how a change to those tables
  reaches production, says what they would change before agreeing to it, and how they would
  confirm afterwards that a push leaves production's data in place. It passes when they catch a
  plan whose backend, every time it starts, deletes and recreates its tables or inserts its
  starting rows again, so each deploy or restart wipes or duplicates what users added; catch a
  plan that ships code needing a new table or column while nothing changes production's tables,
  or that changes them by dropping and recreating the tables, and ask for the change to be
  applied to production's tables, keeping their rows, when that version deploys; go along with a
  plan whose backend creates any missing tables when it starts, whose starting rows go in once,
  and whose table changes are applied as a deploy step; and would confirm it by adding something
  through the live app, pushing a change that redeploys the backend, and seeing, once that deploy
  is live, that the thing is still there.
- **cases:**
  - `seed-every-start`: the backend deletes and recreates its tables, or inserts its starting rows
    again, every time it starts
  - `schema-not-applied`: code needing a new table or column ships with nothing changing
    production's tables, or with the tables dropped and recreated
  - `sound-plan`: missing tables created on start, starting rows put in once, table changes
    applied as a deploy step
  - `confirm-data`: how they would confirm that a push leaves production's data in place
- **taught elsewhere:** session 12 class

### `o-orientation`

- **goal:** get the shape of this area before working on any particular part of it
- **criterion:** orientation
- **adjudicator:** tutor
- **bar:** did it once
- **recurrence:** never
- **is_required:** no
- **group:** orientation

### `w-auto-deploy`

- **goal:** auto-deploy
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a host redeploying the app by itself whenever the repository changes
- **nearest confusable:** redeploy
- **synonyms:** continuous deployment, CD

### `w-push`

- **goal:** push
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** sending your commits from your machine up to GitHub
- **nearest confusable:** commit

### `w-branch`

- **goal:** branch
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a separate line of commits that can grow without changing main
- **nearest confusable:** a fork

### `w-pull-request`

- **goal:** pull request
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** asking, on GitHub, for one branch to be merged into another, where it can be looked at first
- **nearest confusable:** merge; push
- **synonyms:** PR, merge request

### `w-branch-protection`

- **goal:** branch protection
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** GitHub rules that stop anyone pushing straight to a branch such as main
- **nearest confusable:** a private repository
- **synonyms:** ruleset

### `w-github-actions`

- **goal:** GitHub Actions
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** GitHub running jobs described in a file in the repository when something happens to it
- **nearest confusable:** the course's skill file for updating course repos; auto-deploy

### `w-env-file`

- **goal:** .env file
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a file of named values your app reads on your own machine
- **nearest confusable:** the host's environment variables
- **synonyms:** dotenv file

### `w-gitignore`

- **goal:** .gitignore
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the list of files git leaves out of every commit
- **nearest confusable:** removing a file from the repository

### `w-build-time`

- **goal:** build time
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** the moment a value gets fixed into the frontend's files
- **nearest confusable:** runtime

### `w-cache`

- **goal:** cache
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a saved copy, in the browser or on the way to it, kept so it need not be
  fetched again
- **nearest confusable:** a backup

### `w-cache-invalidation`

- **goal:** cache invalidation
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** making a cache stop handing out its old copy
- **nearest confusable:** reloading the page; redeploy; cache busting
- **synonyms:** purge

### `w-ci`

- **goal:** CI
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** running the tests automatically on every push and reporting whether they
  passed
- **nearest confusable:** auto-deploy; a test suite
- **synonyms:** continuous integration

### `w-check`

- **goal:** check
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** a pass or fail result GitHub shows beside a commit or pull request
- **nearest confusable:** a test
- **synonyms:** status check

### `w-fork`

- **goal:** fork
- **criterion:** vocabulary
- **bar:** one production pass
- **group:** vocabulary
- **what it names:** your own copy, on GitHub, of a repository someone else owns
- **nearest confusable:** a clone
