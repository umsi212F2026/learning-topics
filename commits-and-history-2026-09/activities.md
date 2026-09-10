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

<!--
  Derivation convention, recorded so it does not get re-flagged: an activity carrying `checks`
  is a check, so it appears only in the `checks` cell and never in `study`. Activities whose
  `serves` is `all` sit on the `o-orientation` row, which is the row that carries them; they are
  not repeated on every other goal's row.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-place-the-eight-words` | `a-read-git-intro-page` | |
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
  merge conflict.
- **verified:** 2026-09-10
- **learner does:** works through the page top to bottom, stopping at anything they cannot restate
  in their own words: says what they think it means, or says they have nothing, and gets it
  explained there and then rather than reading on. Before finishing, must raise the four words the
  page never mentions (uncommitted, staging area, diff, merge conflict) and hear what each one is.
  Nothing gets written up. The obligation is a running check-my-understanding conversation, not a
  set of definitions: the eight words in this topic each have their own activity and their own
  bar, and this activity is not allowed to meet those on their behalf.
- **tutor role:** explainer
- **tutor does:** explains on demand, in the page's own order, and does not lecture ahead of the
  question. Answers in full on Merge, Pull and Push: the learner pulls the instructor's updates
  and pushes to their own repository, and that pull is what makes a merge, and a merge conflict,
  happen at all. Steers past Clone and Branch only, as out of scope for now rather than as things
  they will never need: the clone already happened on day one and their agent did it, and branches
  do not appear until their tooling starts making them later in the term. Expects merge conflict
  to need raising, because the page never says it. Makes sure the four missing words get raised,
  and raises them if the learner does not. Ends by putting the criterion question directly: could
  you now ask your agent to commit this work, and then ask it to put every file back to that
  commit, and follow what it tells you back both times, with this page still open beside you?
- **done when:** criterion met. The bar for this goal is did it once, and help while reading is
  expected, so the tutor is ruling on the learner's own indication of readiness, not on whether it
  thinks they are ready. That indication is the only thing adjudicated here. How well anything got
  restated during the read is not part of it, and a thin answer about a word is a reason to
  explain the word again, never a reason to rule this goal not met.
- **kind:** single instance
- **worked example:** if the learner goes quiet and stops flagging anything, the tutor models the
  move once on a term the page has just used, saying which part of it it can restate and which
  part it cannot, and then hands the next one back. The page is otherwise its own worked example.
- **doesn't show:** the learner is saying they feel ready, which is what this goal asks for and all
  it asks for. It shows nothing about whether they can actually direct an agent to commit or
  restore anything, and nothing about the eight words beyond having heard them named and
  explained with the page open. There is only one instance, which is fine here because this goal
  never recurs.
- **offer as:** the guided read, in a page's own order, with someone answering as you go. Plain
  text, no terminal anywhere in it, no command line assumed, and you set the pace while the tutor
  fills the gaps, which is the only reason a page this short is enough. The page is five minutes;
  the session around it is more like 25 to 30, because you stop at every term you cannot restate
  and because four of the topic's eight words (uncommitted, staging area, diff, merge conflict)
  are not on the page at all and have to be raised. Three of the page's eight key concepts are
  goals in this topic: Repository, Commit and Merge. The alternative first read is
  `a-place-the-eight-words`, which gives you a picture and asks you to place the words on it
  yourself before anyone explains anything; take this one instead if you would rather be walked
  through a text in order. This is also the entry the orientation goal is adjudicated in, and the
  other one is not.

### `a-place-the-eight-words`

- **serves:** `all`
- **supports:** orient
- **artifact:** Pro Git, second edition, section 1.3, "What is Git?",
  https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F (free, no account, no ads, about
  1,300 words, 8 to 10 minutes to read; 20 to 25 minutes for the whole activity). Six short
  sections ("What is Git?", "Snapshots, Not Differences", "Nearly Every Operation Is Local", "Git
  Has Integrity", "Git Generally Only Adds Data", "The Three States") and three figures, of which
  Figure 6, "Working tree, staging area, and Git directory", is the picture this activity is built
  on. There is no command anywhere on the page and no terminal output: it is prose and diagrams.
  It names repository, commit, staging area and history in place, and it gives uncommitted work a
  place without using the word, as the modified state ("you have changed the file but have not
  committed it to your database yet"). It does not name uncommitted, diff, merge or merge
  conflict.
- **learner does:** looks at the three figures and their captions only, and says what they expect
  the page to claim, before reading a word of it. Then reads it once through. Then draws their own
  version of Figure 6 and marks on it where each of the topic's eight words belongs: repository,
  commit, uncommitted, staging area, diff, history, merge, merge conflict. Says which ones the
  page gave them nowhere to put, and asks about those. Placing a word is not defining it: nothing
  written here is a definition, and this activity settles none of the word goals.
- **tutor role:** explainer
- **tutor does:** stays quiet until the prediction from the figures has been made, then says which
  parts of it the page will bear out and which it will not. While the words are being placed,
  corrects a misplacement by asking what would have to be true for the word to live where it was
  put, rather than by moving it. Supplies the four the page leaves no room for (uncommitted, diff,
  merge, merge conflict) once the learner has said they cannot place them, and ties the last two
  to the occasion this topic exists for: pulling the instructor's updates into files the learner
  has already changed, where their own work is in the way. Treats anything on the page beyond
  these eight as out of scope for now and does not go into it. Writes no commands on the sketch or
  anywhere else, and hands over no command output.
- **done when:** all eight words are placed somewhere on the sketch the learner can point at, and
  the learner says they could now attempt asking an agent for a commit and for a restore with the
  sketch beside them. This entry carries no `checks` and cannot settle `o-orientation`: the
  readiness indication that goal is adjudicated on gets taken in `a-read-git-intro-page`.
- **offer as:** the picture rather than the prose, and you go first. Same kind of thing as
  `a-read-git-intro-page` (a short free page, nothing to type, no terminal in it) and the
  differences are real: you predict from the figures before reading rather than following the
  page's order, you place all eight words yourself rather than meeting four of them where a page
  happens to mention them, and the two pages are short of different words. This one has the
  staging area and no merge; the W3Schools page has merge and no staging area. Take this one if
  lists of terms slide off you, or if what you want first is a picture of where uncommitted work
  sits relative to a commit. It settles nothing on its own, and it makes the five minute page that
  does settle the goal quick when you get to it.

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
  that put every file back to it, with the transcript still on screen. This activity cannot meet
  `c-commit-recovery-point` and carries no `checks` for that reason, however well it goes: the
  tutor performed the loop, the predictions were prompted step by step, and the two requests get
  written with the whole thing still on screen, so the activity did most of the work. Do not log a
  pass against the goal from it. The wording of `done when` here is deliberately close to the
  criterion because that is what the learner is rehearsing, not what they are being examined on.
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
  the tutor wrecks the files, asks it to put every file back to the state at the target commit.
  Then, before accepting that it worked, checks the claim the two ways this topic allows: reads
  back what the agent said it did and says whether that is actually an answer to what was asked,
  and opens one of the wrecked files and says whether the contents are the ones the target commit
  held. No command output is asked for and none is shown.
- **tutor role:** role-play partner
- **tutor does:** plays a literal minded coding agent: does exactly what it is asked, reports what
  it did, volunteers nothing and refuses nothing. Prepares the instance beforehand, notes every
  request that had to be repeated or rephrased, and afterwards tells the learner which requests
  were ambiguous and what a differently behaved agent might have done with them. Offers the worked
  example only if help is asked for.
- **done when:** criterion met with no help, on a Medium or Hard instance. An Easy instance does
  not reach the "any commit" half of the criterion, so a pass on one is not a pass on the goal
  (see the generator).
- **kind:** generator
- **generator:** build a scratch repository holding four to six short text files, with at least two
  commits in it that the learner did not make, and have the learner change two or three of the
  files. After their commit lands, wreck the tree, varying how: an overwrite with garbage, a
  deletion, a rename, an edit spread over two files. Hold fixed that the learner may only issue
  requests in words, that the recovery target is a commit that exists and is named to them, and
  that the damage is visible (they can open a file and see it is wrong) before they start. Easy:
  one file overwritten, target is the commit they just made. Medium: add a deleted file and set the
  target two commits back. Hard: also create a new file after their commit that no commit contains,
  so that "put everything back" has an answer that is not simply yes. An attempt that is meant to
  count against the criterion runs at Medium or Hard, because the criterion says any commit and
  Easy always targets the commit just made. Easy is reserved for the worked example and for a
  learner going again with help after a failure; a pass at Easy does not clear this goal, and the
  tutor should say that rather than logging it as met.
- **worked example:** work one Easy instance live, saying each request out loud before making it,
  then reading back the agent's own prose report of what it did, then opening one affected file so
  the learner watches the contents come back. No command and no command output is shown at any
  point. At the first level of help, give only the first request ("ask it to commit everything
  that is saved right now") and let the learner find the second.
- **doesn't show:** it does not show they would notice an agent that reported success and did
  nothing, because this activity tells them to check and a real session does not prompt them. It
  does not touch choosing what goes into a commit, only committing everything saved, which is all
  this criterion asks for. And a pass says nothing about work that was never committed at all,
  which is the case that actually costs people an afternoon.
- **offer as:** the real thing in a place where breaking it costs nothing. `a-commit-own-repo` also
  makes you do both halves in one sitting; the differences from it are the three that matter here:
  the repository is a throwaway you have no stake in, the agent is the tutor playing one (literal
  minded, volunteers nothing, so an ambiguous request stays ambiguous), and the damage is somebody
  else's choice, which makes this the only candidate that shows whether you can recover something
  you did not break. It needs a live session, because someone has to play the agent and someone
  has to do the wrecking.

### `a-commit-own-repo`

- **serves:** `c-commit-recovery-point`
- **supports:** attempt
- **checks:** `c-commit-recovery-point`
- **artifact:** no external source. The learner's own course repository, the one they commit to all
  term, plus their own coding agent. 15 minutes at the end of a session in which they actually
  changed something, or 20 on a later run, which has two restores in it.
- **learner does:** asks their agent to commit the work from this session, and reads what it says
  back closely enough to be sure the commit actually landed rather than assuming it did. Then,
  before anything gets damaged, three preconditions in their own hands: saves every open file,
  asks the agent whether anything is still uncommitted and gets a no (if the answer is not no,
  asks for that committed too, and only then goes on), and pastes the current
  contents of the file they are about to wreck into a scratch note outside the repository, which
  is the fallback. Then names that file, asks the agent to change it badly on purpose, and asks it
  to put that file, and then the whole tree, back to the target commit the tutor set (see the
  generator). Confirms by opening the file and reading it, not by believing the agent's report.
  Keeps the whole session transcript, their own requests and the agent's replies both, and keeps
  the request that caused the restore in the exact words they used. If the restore does not produce
  the old contents: stops there, pastes the scratch note back into the file, and brings the
  transcript to the tutor. The attempt ends and it resumes in `a-commit-restore-drill`, where the
  repository is a throwaway.
- **tutor role:** none
- **tutor does:** sets the recovery target before the learner starts (see the generator), then
  waits: the run itself is done alone, with the learner's own agent. Afterwards reads the whole
  transcript, requests and replies both, and first checks that the restore was asked for rather
  than volunteered. Then asks two things. What would you have done if the agent had said it
  restored the file and it had not? Which of these requests would have been dangerous if you had
  made it before the commit existed rather than after?
- **done when:** criterion met with no help, and the restore has to have been asked for. The
  request that caused it is preserved in the learner's own words and has to read as a request for
  the restore, not as a remark the agent chose to act on. If the agent restored anything unasked,
  or did the second half before being asked, the attempt is `criterion: unclear` however good the
  outcome looked, and the learner goes to `a-commit-restore-drill`, where the tutor is playing the
  agent and cannot volunteer.
- **kind:** generator
- **generator:** the material is whatever they actually changed that session, so no two instances
  have the same files in them. What varies deliberately is the recovery target and how much comes
  back, and the tutor sets it before the learner starts. First run: the target is the commit they
  have just made, and they bring back one file, then the whole tree. Later runs: the target is a
  commit from an earlier session, which the learner finds by asking the agent in words which
  commit was the last one before today's work and what was in it, then reading the answer; they
  ask for the whole tree back to that commit, and then for the whole tree back to today's commit,
  so the session ends where it started. Never repeat the previous run's target. Hold fixed:
  today's work is committed and the commit is confirmed landed before anything is damaged, the
  agent has been asked whether anything is still uncommitted and has said no, the file wrecked is
  one the target commit contains, the fallback copy is outside the repository, and the recovery is
  confirmed by opening the file rather than by the agent's say so. If the session produced no
  changes there is no instance, and `a-commit-restore-drill` runs instead.
- **worked example:** if they stall, show the first request from `a-commit-restore-drill` verbatim
  and let them adapt it. The wording that works on a scratch repository works here.
- **doesn't show:** the damage is one they chose and therefore already understand, so a pass does
  not show they could recognize damage they did not cause. A first run targets the commit just
  made, so a first run says nothing about the "any commit" half of the criterion; only a later
  run, aimed at an earlier session's commit, reaches it. Their own agent, unlike the tutor playing
  one, can do the second half unasked, which is why `done when` makes the request itself the thing
  being checked, and the price of that is that a run where the agent was merely helpful comes out
  `unclear` rather than met. And it carries a real risk the scratch drill does not: anything in
  the repository that was never committed will not come back.
- **offer as:** the one that happens in the repository you actually care about, on work you actually
  did, which is what makes it stick. It only runs at the end of a real working session, and it asks
  you to break a real file on purpose, which not everyone will want to do. On a later run it also
  asks you to send the whole repository back to a commit from an earlier session and then bring it
  forward again, which is the only place in this topic that happens to work you care about.


### `a-w-merge`

- **origin:** generated
- **serves:** `w-merge`
- **checks:** `w-merge`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-merge-conflict`

- **origin:** generated
- **serves:** `w-merge-conflict`
- **checks:** `w-merge-conflict`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
