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
| `c-work-at-risk` | say what work is at risk before running something that rewrites the files | shown `git status` and `git diff` for a working tree they did not make, says which changes exist only on disk and which are already in the record, and says whether a named operation (a pull, or an agent rewriting a file that is open in the editor) would destroy any of them; specimen has some changes staged and some not |

## Coverage

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-git-intro-page` | `a-watch-git-basics-video` | |
| `c-commit-recovery-point` | `a-narrated-commit-restore`, `a-selfexplain-tracking-changes` | `a-commit-restore-drill`, `a-commit-own-repo` | |
| `c-work-at-risk` | `a-find-undo-assumptions`, `a-sort-dangit-recipes`, `a-predict-status-output` | `a-judge-tree-at-risk` | |

---

## Activities

### `a-read-git-intro-page`

- **serves:** `all`
- **supports:** orient
- **artifact:** W3Schools, "Git Introduction", https://www.w3schools.com/git/git_intro.asp (free, no
  account, about 5 minutes). The first page only, not the rest of the W3Schools Git tutorial. It
  holds "What is Git?", a "Key Git Concepts" list of eight terms (Repository, Clone, Stage,
  Commit, Branch, Merge, Pull, Push), "Working with Git" and "Why Git?". It names repository,
  commit, stage and history in place. It does not name uncommitted, staging area or diff.
- **verified:** 2026-09-08
- **learner does:** works through the page top to bottom, stopping at anything they cannot restate
  in their own words and asking the tutor to explain it there and then rather than reading on.
  Before finishing, must raise the three words the page never mentions (uncommitted, staging area,
  diff) and get an explanation of each. Ends by writing a one line gloss, in their own words, of
  all six words in this topic: repository, commit, uncommitted, staging area, diff, history.
- **tutor role:** explainer
- **tutor does:** explains on demand, in the page's own order, and does not lecture ahead of the
  question. Steers past Clone, Branch, Merge, Pull and Push: those are five of the page's eight key
  concepts and none of them are in this topic, so name them as out of scope rather than teach them.
  Makes sure the three missing words get raised, and raises them if the learner does not. Ends by
  asking whether they could now watch someone make a commit and follow what was happening.
- **done when:** learner can attempt a commit with the page still open beside them, and has a gloss
  for all six words, including the three the page never mentions.
- **offer as:** the short one. Five minutes of plain text, no terminal anywhere in it, no command
  line assumed, and you set the pace while the tutor fills the gaps as you go, which is the only
  reason a page this short is enough. Five of its eight key concepts are about collaborating with
  other people and are not part of this topic.

### `a-watch-git-basics-video`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** "Git Tutorial for Beginners: Learn Git in 1 Hour", Programming with Mosh,
  https://www.youtube.com/watch?v=8JJ101D3knE (free on YouTube, no account). About an hour,
  chaptered, and it is screen recording of a terminal throughout. Confirmed chapters include
  "Viewing the Staged and Unstaged Changes" (4:59) and "Viewing History" (2:12), which is why this
  is the one orientation artifact that puts a diff and a log on screen. The title, channel and
  those two chapters were confirmed; the rest of the chapter list was not checked title by title,
  so skim the chapter menu before pointing the learner at any other section.
- **learner does:** watches alone, with no tutor in the room, keeping a running list of the six
  words in this topic (repository, commit, uncommitted, staging area, diff, history) and writing a
  one line gloss of each at the moment the video shows it. Stops at "Viewing the Staged and
  Unstaged Changes" and at "Viewing History" and writes down what was actually on screen in each.
  Afterwards, and before any discussion, says in one sentence whether they could now attempt a
  commit in their own repository with the video's chapter list beside them, and names the one thing
  they would still have to look up.
- **tutor role:** none while it is being watched, then socratic questioner
- **tutor does:** stays out of it until the glosses and the readiness sentence arrive. Then answers
  each gloss with a discriminating near miss rather than a correction ("you said uncommitted means
  unsaved; the file is saved and the editor shows no dot, is it uncommitted?"). Ignores the
  branching, merging and remote chapters, which are outside this topic. Adjudicates the readiness
  claim rather than accepting it: a learner who cannot say what the staging area is has not met it,
  however confident the sentence.
- **done when:** criterion met with no help.
- **kind:** single instance
- **worked example:** if the learner stalls on the glosses, hand them one finished gloss for
  repository and let them do the other five. For everything else the video is itself the worked
  example.
- **doesn't show:** an hour of watching someone else type shows nothing about whether this learner
  can drive an agent to do the same thing, which is what `c-commit-recovery-point` is for. The
  readiness claim is self reported, so the tutor is adjudicating a sentence rather than a
  performance. And there is only one instance, which is fine for this goal (its bar is did it once
  and it never recurs) and would not be fine for any other.
- **offer as:** the long one, about an hour, and the only orientation artifact that shows you a
  real terminal: what `git status` prints, what a diff looks like, what a log looks like. It
  assumes you are willing to watch commands go past, though not to type any. Take it if five
  minutes of prose left you unable to picture any of this.

### `a-narrated-commit-restore`

- **serves:** `c-commit-recovery-point`
- **supports:** orient, deepen
- **artifact:** no external source. A throwaway repository the tutor creates in a scratch directory
  (three or four short text files, two commits already in it) and drives live in the session. 15 to
  20 minutes.
- **learner does:** watches the tutor do the whole loop (commit what is there, wreck two files, put
  them back) and, before every step, says out loud what they think the tutor will do next. Writes
  down each point where the tutor's choice differed from the prediction, plus one question about
  it. At the end writes, in their own words, the two requests they would make of an agent to get
  the same result.
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

### `a-selfexplain-tracking-changes`

- **serves:** `c-commit-recovery-point`
- **supports:** deepen
- **artifact:** Software Carpentry, "Version Control with Git", episode 4, "Tracking Changes",
  https://swcarpentry.github.io/git-novice/04-changes.html (free, CC-BY 4.0). 20 to 30 minutes. A
  worked sequence on a single file through `git status`, `git add`, `git commit`, `git diff` and
  `git diff --staged`, ending in four named challenges, among them "Choosing a Commit Message",
  "Committing Changes to Git" and "Committing Multiple Files", each with a solution on the page.
- **learner does:** reads the worked sequence without typing anything, and for each command in it
  writes one line saying why that command is there and what would be different if it were skipped.
  Then answers those three named challenges in writing, before opening the solutions, and marks
  their own answers against them.
- **tutor role:** socratic questioner
- **tutor does:** takes the why lines one at a time and pushes on any that only restate the command
  ("you wrote that `git add` stages the file; what is different about the repository afterwards,
  and what is not?"). Checks the challenge answers against the episode's own solutions and asks the
  learner to say what they got wrong before being told.
- **done when:** learner can say, for each command in the sequence, what it changed and what it
  left alone, with the episode still open.
- **offer as:** the cheapest route if you have never made a commit, because the sequence in front of
  you is already correct and all you have to do is say why each step is there. Reading and writing
  only, nothing installed, no repository of your own. It stops at committing, so it will not show
  you how to get anything back.

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

### `a-find-undo-assumptions`

- **serves:** `c-work-at-risk`
- **supports:** deepen
- **artifact:** Pro Git, 2nd edition (Chacon and Straub), section 2.4, "Undoing Things",
  https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things (free, full text online). 10 to 15
  minutes. It covers `git commit --amend`, unstaging with `git restore --staged` or
  `git reset HEAD`, and discarding with `git restore` or `git checkout --`, and it says in its own
  words that a discarded local change is gone and that "anything you lose that was never committed
  is likely never to be seen again".
- **learner does:** for each operation the section shows, writes down what it assumes about where
  your work currently lives, and what would be destroyed if that assumption were wrong. Then writes
  one sentence naming the operations they would not let an agent run without checking `git status`
  first, and why.
- **tutor role:** socratic questioner
- **tutor does:** for each answer, supplies the case that breaks it ("you said unstaging is safe
  because it only moves things out of the staging area; you also had edits in the working copy, does
  that still hold?"). Finishes by asking which of these are recoverable afterwards, and out of what.
- **done when:** learner can say, for a command they are shown, whether it only reads the record or
  overwrites files on disk, with the section still open.
- **offer as:** short, authoritative, and the one place that says in the book's own words that
  uncommitted work does not come back. It is organised by command rather than by working tree, so
  on its own it will not teach you to read a status output.

### `a-sort-dangit-recipes`

- **serves:** `c-work-at-risk`
- **supports:** deepen
- **artifact:** "Dangit, Git!?!", https://dangitgit.com (free, one page, no account, about 10
  minutes). The profanity free version of "Oh Shit, Git!?!". Nine or so short recipes for common
  git messes, among them the reflog "magic time machine", changing the last commit, committing on
  the wrong branch, undoing your changes to one file, and the "nuclear option" that resets
  everything.
- **learner does:** sorts every recipe on the page into three piles: cannot lose work, could lose
  work that exists only on disk, could lose work that is already committed. Then writes in one
  sentence the rule they used to sort, and marks the one recipe they were least sure about.
- **tutor role:** critic
- **tutor does:** contests at least two placements, including one the learner got right, and makes
  them defend it from the recipe's own text. Then asks what the whole page assumes you have already
  done before any of it can help you (committed something), and whether someone whose agent is
  rewriting a file right now could use any of these.
- **done when:** learner can say, for a recipe they are shown, what state it assumes they are in
  and what it could cost them.
- **offer as:** the shortest of these and the most fun, and it teaches the shape of the risk case by
  case rather than by principle. It assumes you are already in a mess, so it is a poor place to
  learn what a staging area is, and several recipes are about branches, which this topic leaves
  out.

### `a-predict-status-output`

- **serves:** `c-work-at-risk`
- **supports:** deepen
- **artifact:** no external source. A scratch repository the tutor drives, plus a written prediction
  from the learner. 15 minutes.
- **learner does:** is told a sequence of edits in words (edit A and stage it, edit A again, create
  B and never add it, delete C) and writes down, before seeing anything, what `git status` will
  print: which sections it will have and which files will be in each, and what `git diff` will
  show. Hands the prediction over, then marks every difference against the real output.
- **tutor role:** none while the prediction is being written, then explainer
- **tutor does:** performs the sequence in a scratch repository, shows the real `git status` and
  `git diff`, and asks the learner to account for each difference rather than accounting for it on
  their behalf. Keeps the written prediction in view so it cannot be quietly revised into agreement.
- **done when:** learner can predict which section of `git status` a given change will appear in
  before being shown, with their own notes beside them.
- **offer as:** the only one here that makes a wrong model visible to the person holding it. The
  scenario arrives in words, so this exercises predicting a status output rather than reading one
  handed to you cold, which is the reverse of what the check does. The file edited twice, once
  staged and once not, is where most predictions come apart.

### `a-judge-tree-at-risk`

- **serves:** `c-work-at-risk`
- **supports:** attempt
- **checks:** `c-work-at-risk`
- **artifact:** no external source. A `git status` and a `git diff` pasted verbatim from a scratch
  repository the tutor built per the generator below, plus one named operation. 15 minutes.
- **learner does:** reads the two outputs cold, for a working tree they have never seen, and answers
  three things in writing: which changed paths exist only on disk, which are already in the record,
  and whether the named operation would destroy any of them, naming which. Answers before asking
  any questions, then may say what they wish they had been shown.
- **tutor role:** none while the answer is being written, then critic
- **tutor does:** builds the specimen, pastes it verbatim, names the operation, and says nothing
  until the answer arrives. Then goes path by path and contests anything the two outputs do not
  support, including right answers reached by guessing. Records which of the three parts were
  right: a learner can get the durability question right and the operation question wrong.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** build a scratch repository with one commit in it, then a mixed working tree, and
  paste the verbatim output of `git status` and `git diff`. Always: some changes staged and some
  not, which this criterion requires; at least four changed paths; and the learner never sees the
  repository or how it was made. Vary: which paths; whether one file carries both staged and
  unstaged changes to itself (include it in about half the instances, it is the hardest case); an
  untracked new file; a staged deletion; a rename. Then name exactly one operation as a
  hypothetical, not run: a `git pull` that touches one of those paths, an agent rewriting one of
  those files wholesale in place, `git restore .`, or a plain `git commit`. Vary the answer too:
  about one instance in three should be one where nothing is at risk, or the learner learns that
  the answer is always yes. Easy is four paths, no same file split, and `git restore .`. Hard is
  six paths including a same file split and an untracked file, with a `git pull` that touches only
  a path having nothing uncommitted in it.
- **worked example:** work one specimen aloud, reading `git status` section by section: "Changes to
  be committed" means git has a copy of that content but no commit points at it, "Changes not
  staged for commit" means the only copy is the file on disk, "Untracked files" means git has never
  seen it at all. Then say, for each path, what the named operation would do to it.
- **doesn't show:** a pasted specimen is tidier than a real one, with no question about which
  repository you are standing in, no stash, no half finished merge. A pass shows they can read the
  output when someone puts it in front of them, not that they would stop and look before letting an
  agent run, which is the thing that actually saves the work. And it treats staged but uncommitted
  content as at risk: a learner who objects that staged content is already in git's object store
  and can sometimes be dug back out is right, and would be marked wrong.
- **offer as:** the check, and the closest thing here to the situation this goal is about: output
  you did not produce, about a working tree you did not make, and a decision about an operation you
  did not choose. Nothing to read first, and it is unforgiving if you have not yet met the staging
  area.

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
