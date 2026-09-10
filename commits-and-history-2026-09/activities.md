# Activities — commits and history

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

<!--
  Authored by curation/critique and placed by the orchestrator. Rewritten wholesale each pass,
  so don't edit it — it will be replaced.

  Dated, and short. What the tutor should know about this file as a whole before using it:
  the menu skews toward reading, two capabilities are thinner than they look, the depth
  runs heavier than goals.md asks for. Only things that survived the revision round —
  anything that got fixed doesn't belong here.

  Empty is a legitimate and good outcome. Say "nothing at file level" rather than inventing
  an observation.
-->

## Goals

| id | Goal | Criterion — what gets examined, and what counts |
| -- | ---- | ----------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-commit-recovery-point` | make use of commits | Can ask the agent to commit saved work. Can ask the agent to recover all files to where they were at any commit. |

## Coverage

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-git-intro-page` | `a-read-git-intro-page` | |
| `c-commit-recovery-point` | `a-narrated-commit-restore` | `a-commit-restore-drill`, `a-commit-own-repo` | |

---

## Activities

### `a-read-git-intro-page`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** W3Schools, "Git Introduction", https://www.w3schools.com/git/git_intro.asp (free, no
  account, about 5 minutes). The first page only, not the rest of the W3Schools Git tutorial. It
  holds "What is Git?", a "Key Git Concepts" list of eight terms (Repository, Clone, Stage,
  Commit, Branch, Merge, Pull, Push), "Working with Git" and "Why Git?". It names repository,
  commit, stage, merge and history in place. It does not name uncommitted, staging area, diff or
  rebase.
- **verified:** 2026-09-08
- **learner does:** works through the page top to bottom, stopping at anything they cannot restate
  in their own words and asking the tutor to explain it there and then rather than reading on.
  Before finishing, must raise the four words the page never mentions (uncommitted, staging area,
  diff, rebase) and get an explanation of each. Ends by writing a one line gloss, in their own
  words, of all eight words in this topic: repository, commit, uncommitted, staging area, diff,
  history, merge, rebase.
- **tutor role:** explainer
- **tutor does:** explains on demand, in the page's own order, and does not lecture ahead of the
  question. Steers past Clone, Pull and Push, which are about collaborating with other people and
  are not in this topic, naming them as out of scope rather than teaching them. Branch and Merge
  are not in that group: merge is one of this topic's words and branch is what merge presupposes,
  so answer those if they come up, and expect rebase to need raising because the page never says
  it. Makes sure the four missing words get raised, and raises them if the learner does not. Ends by
  putting the criterion question directly: could you now ask your agent to commit this work, and
  follow what it tells you back, with this page still open beside you?
- **done when:** criterion met. The bar for this goal is did it once, and help while reading is
  expected, so the tutor is ruling on the learner's own indication of readiness, not on whether it
  thinks they are ready.
- **kind:** single instance
- **worked example:** if the learner stalls on the glosses, hand them one finished gloss for
  repository and let them do the other seven. The page is otherwise its own worked example.
- **doesn't show:** the learner is saying they feel ready, which is what this goal asks for and all
  it asks for. It shows nothing about whether they can actually direct an agent to commit or
  restore anything, and nothing about the eight words beyond a gloss written with the page open.
  There is only one instance, which is fine here because this goal never recurs.
- **offer as:** the short one. Five minutes of plain text, no terminal anywhere in it, no command
  line assumed, and you set the pace while the tutor fills the gaps as you go, which is the only
  reason a page this short is enough. Three of its eight key concepts (Clone, Pull and Push) are
  about collaborating with other people and are not part of this topic, and one of the topic's
  words, rebase, is not on the page at all.

### `a-w-repository`

- **origin:** generated
- **serves:** `w-repository`
- **checks:** `w-repository`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-commit`

- **origin:** generated
- **serves:** `w-commit`
- **checks:** `w-commit`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-uncommitted`

- **origin:** generated
- **serves:** `w-uncommitted`
- **checks:** `w-uncommitted`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-staging-area`

- **origin:** generated
- **serves:** `w-staging-area`
- **checks:** `w-staging-area`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-diff`

- **origin:** generated
- **serves:** `w-diff`
- **checks:** `w-diff`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-history`

- **origin:** generated
- **serves:** `w-history`
- **checks:** `w-history`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-narrated-commit-restore`

- **serves:** `c-commit-recovery-point`
- **supports:** orient, deepen
- **artifact:** no external source. A throwaway repository the tutor creates in a scratch directory
  (three or four short text files, two commits already in it) and drives live in the session. 15 to
  20 minutes.
- **learner does:** watches the tutor do the whole loop (commit what is there, wreck two files, put
  them back) and, before every step, says out loud what they would ask an agent for at that point
  and what they expect it to tell them back. Writes down each point where what actually happened
  differed from the prediction, plus one question about it. At the end writes, in their own words,
  the two requests they would make of an agent to get the same result. They are never asked to
  name a git command, and nothing here requires them to type one.
- **tutor role:** explainer
- **tutor does:** performs it, narrating what is being weighed at each step, including at least one
  false start: tries to recover a change that was never committed and shows that it is simply gone.
  Pauses before each command for the learner's prediction. Afterwards takes the learner's two
  requests and says what a literal minded agent would do with each of them.
- **done when:** learner can name, in order, the requests that produce a commit and the requests
  that put every file back to it, with the transcript still on screen.
- **offer as:** the one to take before you have done any of this yourself. It shows the deliberation
  and the false starts that a finished example has edited out, which is the one thing reading
  cannot give you. It needs a live session and cannot be done alone.

### `a-commit-restore-drill`

- **serves:** `c-commit-recovery-point`
- **supports:** attempt
- **checks:** `c-commit-recovery-point`
- **artifact:** no external source. A scratch repository the tutor builds per the generator below,
  in a directory the learner has no stake in. 20 minutes.
- **learner does:** works only by asking in words, never by typing a git command and never by
  copying one they were shown. First asks the agent to commit the work as it stands. Then, after
  the tutor wrecks the files, asks it to put every file back to the state at that commit. Then asks
  for evidence that it worked, and says what the evidence shows.
- **tutor role:** role-play partner
- **tutor does:** plays a literal minded coding agent: does exactly what it is asked, reports what
  it did, volunteers nothing and refuses nothing. Prepares the instance beforehand, notes every
  request that had to be repeated or rephrased, and afterwards tells the learner which requests
  were ambiguous and what a differently behaved agent might have done with them. Offers the worked
  example only if help is asked for.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** build a scratch repository holding four to six short text files, with at least two
  commits in it that the learner did not make, and have the learner change two or three of the
  files. After their commit lands, wreck the tree, varying how: an overwrite with garbage, a
  deletion, a rename, an edit spread over two files. Hold fixed that the learner may only issue
  requests in words, that the recovery target is a commit that exists and is named to them, and
  that the damage is visible (they can open a file and see it is wrong) before they start. Easy:
  one file overwritten, target is the commit they just made. Medium: add a deleted file and set the
  target two commits back. Hard: also create a new untracked file after their commit, so that "put
  everything back" has an answer that is not simply yes.
- **worked example:** work one instance live, saying each request out loud before making it and
  showing `git status` after each one. At the first level of help, give only the first request
  ("ask it to commit everything that is saved right now") and let the learner find the second.
- **doesn't show:** it does not show they would notice an agent that reported success and did
  nothing, because this activity requires them to ask for evidence and a real session does not. It
  does not touch choosing what goes into a commit, only committing everything saved, which is all
  this criterion asks for. And a pass says nothing about work that was never committed at all,
  which is the case that actually costs people an afternoon.
- **offer as:** the real thing, in a place where breaking it costs nothing, and the only candidate
  that makes you do both halves (commit, then recover) in one sitting. It needs a live session,
  because someone has to play the agent and someone has to do the wrecking.

### `a-commit-own-repo`

- **serves:** `c-commit-recovery-point`
- **supports:** attempt
- **checks:** `c-commit-recovery-point`
- **artifact:** no external source. The learner's own course repository, the one they commit to all
  term, plus their own coding agent. 15 minutes at the end of a session in which they actually
  changed something.
- **learner does:** asks their agent to commit the work from this session. Then names one file that
  commit contains, asks the agent to change it badly on purpose, and asks it to put that file, and
  then the whole tree, back to the commit just made. Confirms by opening the file rather than by
  believing the agent's report. Keeps the wording of every request they made.
- **tutor role:** none
- **tutor does:** waits: this one is done alone, with the learner's own agent. Afterwards reads the
  transcript and asks two things. What would you have done if the agent had said it restored the
  file and it had not? Which of these requests would have been dangerous if you had made it before
  the commit existed rather than after?
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the instance is whatever they actually changed that session, so it is fresh every
  time and nothing has to be varied deliberately. Hold fixed: a commit exists before anything is
  wrecked, the file wrecked is one that commit contains, and the recovery is confirmed by opening
  the file rather than by the agent's say so. If the session produced no changes there is no
  instance, and `a-commit-restore-drill` runs instead.
- **worked example:** if they stall, show the first request from `a-commit-restore-drill` verbatim
  and let them adapt it. The wording that works on a scratch repository works here.
- **doesn't show:** the damage is one they chose and therefore already understand, so a pass does
  not show they could recognize damage they did not cause. Their own agent, unlike the tutor
  playing one, may do the second half unasked and the learner still passes. And it carries a real
  risk the scratch drill does not: anything made after the commit and never committed will not come
  back.
- **offer as:** the one that happens in the repository you actually care about, on work you actually
  did, which is what makes it stick. It only runs at the end of a real working session, and it asks
  you to break a real file on purpose, which not everyone will want to do.


### `a-w-merge`

- **origin:** generated
- **serves:** `w-merge`
- **checks:** `w-merge`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-rebase`

- **origin:** generated
- **serves:** `w-rebase`
- **checks:** `w-rebase`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
