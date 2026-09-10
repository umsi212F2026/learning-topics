# Activities — commits and history

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-09-10. The learner sections of `goals.md`, where this came from, what I already have, and
what I'll use it for, are all blank, so this menu was written for someone starting cold: a guided
read, a narrated demo, worked examples before problems. If this learner has used git before, three
of the five curated entries are beneath them, and you are the first person who will find that out.
Ask before you offer.

Every entry here needs you in the session except the run of `a-commit-own-repo`, which is also the
only one that touches the learner's own repository. If a live session is not available, the only
path forward is the riskiest one.

The menu leans toward reading and watching on purpose. The depth stops at recognizing these words
and following what an agent reports back, so do not correct the skew by adding authoring tasks.

**On `o-orientation`.** `orientation`, in full: the learner has indicated they could now attempt
the real thing with the artifact still beside them. Deliberately weak evidence. The bar is did it
once, help while reading is expected, and you are the adjudicator: the ruling is on their
indication, not on whether you think they are ready.

Only `a-read-git-intro-page` carries `checks` for this goal, so the two reads are a sequence rather
than a choice. A learner who prefers the picture route in `a-place-the-eight-words` will still need
the W3Schools read afterwards to close the goal. Offer the picture on its merits, and say that the
short read follows.

**On `c-commit-recovery-point`.** Two capabilities in one criterion, commit and restore, and no
partial credit. The bar is one unaided pass, so both halves have to land in the same attempt: a
learner who commits cleanly and then botches the restore records a miss on the whole goal.

Not every instance reaches the second half. A Medium or Hard drill instance does, and so does a
later `a-commit-own-repo` run aimed at an earlier session's commit. An Easy drill instance and a
first `a-commit-own-repo` run both target the commit just made, so neither establishes "any
commit"; do not log either as met.

The adjudicator is the default fresh judge, who was not there. An attempt leaves nothing to rule on
unless the requests and the replies are written down. `a-commit-own-repo` says to keep the
transcript; `a-commit-restore-drill` does not, and you should keep one anyway.

What a met goal here does not claim: both checks examine whether the learner can ask, not whether
they can tell that the asking worked. Neither ever puts a false report in front of them, and
neither examines work that was never committed and cannot come back, which is the case that
actually costs people an afternoon. That case is demonstrated once, in `a-narrated-commit-restore`,
which cannot check anything, and is otherwise reachable only through `w-uncommitted`.

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
| `o-orientation` | `a-place-the-eight-words` | `a-read-git-intro-page` | see Check notes |
| `c-commit-recovery-point` | `a-narrated-commit-restore` | `a-commit-restore-drill`, `a-commit-own-repo` | see Check notes |

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
  explained there and then rather than reading on. Before finishing, must raise the three words the
  page never mentions (uncommitted, diff, merge conflict) and hear what each one is, and must get
  the page's Stage tied to this topic's staging area, which is the same step under a shorter name.
  Nothing gets written up. The obligation is a running check-my-understanding conversation, not a
  set of definitions: the eight words in this topic each have their own activity and their own
  bar, and this activity is not allowed to meet those on their behalf.
- **tutor role:** explainer
- **tutor does:** explains on demand, in the page's own order, and does not lecture ahead of the
  question. Answers in full on Merge, Pull and Push: the learner pulls the instructor's updates
  and pushes to their own repository, and that pull is what makes a merge, and a merge conflict,
  happen at all. Steers past Clone and Branch only, as out of scope for now rather than as things
  they will never need: the clone already happened on day one and their agent did it, and branches
  do not appear until their tooling starts making them later in the term. Expects merge conflict to
  need raising: the body never says it, and the one place the phrase appears is a left hand
  navigation link ("Merge Conflicts", under Git Advanced), so a learner who scans the sidebar may
  arrive with the phrase and nothing attached to it. Makes sure the three missing words get raised,
  and raises them if the learner does not. Says explicitly that the page's Stage ("Tell Git
  which changes you want to save next", and again under "Working with Git", where the modified
  files are selected to Stage and the staged files are Committed) is this topic's staging area:
  what the page withholds is the phrase, not the step, so the phrase gets introduced as a name for
  something the page has already said twice and not as a fourth thing the page left out. Ends by
  putting the criterion question directly: could you now ask your agent to commit this work, and
  then ask it to put every file back to that commit, and follow what it tells you back both times,
  with this page still open beside you?
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
  fills the gaps, which is what makes a page this short enough: the reading is the small half of
  the session. The body is 289 words, two or three minutes; the session around it is more like 25
  to 30, because you stop at every term you cannot restate and because three of the topic's eight
  words (uncommitted, diff, merge conflict) are not on the page at all and have to be raised. Four
  of the page's eight key concepts are goals in this topic: Repository, Commit, Merge, and Stage,
  which is the staging area under a shorter name. The alternative first read is
  `a-place-the-eight-words`, which gives you a picture and asks you to place the words on it
  yourself before anyone explains anything; take this one instead if you would rather be walked
  through a text in order. This is also the entry the orientation goal is adjudicated in, and the
  other one is not.
- **check note:** The closing question is compound: commit, then restore, then follow the report
  back both times. A hedged answer, comfortable with asking for the commit and unsure about the
  restore, is not the indication this criterion asks for. Take it as `criterion: unclear`, explain
  the restore half again, and put the question again, rather than reading it as a yes.

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
- **verified:** 2026-09-10
- **learner does:** looks at the three figures and their captions only, and says what they expect
  the page to claim, before reading a word of it. Then reads it once through. Then draws their own
  version of Figure 6 and marks on it where each of the topic's eight words belongs: repository,
  commit, uncommitted, staging area, diff, history, merge, merge conflict. Says which ones the page
  gave them nowhere to put, and asks about those. Uncommitted is a case of its own and is not one
  of them: the page does give it a place, as the modified state, so what to look for is the place
  and not the word, and "there is somewhere for this, but the page never calls it uncommitted" is
  the right answer here. Placing a word is not defining it: nothing written here is a definition,
  and this activity settles none of the word goals.
- **tutor role:** explainer
- **tutor does:** stays quiet until the prediction from the figures has been made, then says which
  parts of it the page will bear out and which it will not. While the words are being placed,
  corrects a misplacement by asking what would have to be true for the word to live where it was
  put, rather than by moving it. Supplies the three the page leaves no room for (diff, merge, merge
  conflict) once the learner has said they cannot place them, and ties the last two to the occasion
  this topic exists for: pulling the instructor's updates into files the learner has already
  changed, where their own work is in the way. Handles uncommitted the other way round, because the
  page places it and withholds only the word: if the learner cannot find where it goes, points at
  the modified state in Figure 6 and the sentence beside it ("you have changed the file but have
  not committed it to your database yet") and lets the word land on a place the page already gave
  them, rather than supplying it as a fourth thing the page is missing. Treats anything on the page
  beyond these eight as out of scope for now and does not go into it. Writes no commands on the
  sketch or anywhere else, and hands over no command output.
- **done when:** all eight words are placed somewhere on the sketch the learner can point at, and
  the learner says they could now attempt asking an agent for a commit and for a restore with the
  sketch beside them. This entry carries no `checks` and cannot settle `o-orientation`: the
  readiness indication that goal is adjudicated on gets taken in `a-read-git-intro-page`.
- **offer as:** the picture rather than the prose, and you go first. Same kind of thing as
  `a-read-git-intro-page` (a short free page, nothing to type, no terminal in it) and the
  differences are real: you predict from the figures before reading rather than following the
  page's order, you place all eight words yourself rather than meeting five of them where a page
  happens to mention them, and the two pages are short of different words. This one names the
  staging area and puts uncommitted work in a picture, but never says merge; the W3Schools page
  says merge, and names the same step "Stage" without ever using the phrase staging area. Take this
  one if lists of terms slide off you, or if what you want first is a picture of where uncommitted
  work sits relative to a commit. It settles nothing on its own, and taking it first is what leaves
  the page that does settle the goal (289 words, two or three minutes of reading) with almost
  nothing left to explain when you get to it.
- **check note:** This entry cannot close `o-orientation`, however well its `done when` goes. It
  takes exactly the readiness indication the criterion asks for, but only an entry carrying
  `checks` can finish a goal, so log nothing against the goal from it and treat the indication as
  rehearsal for the one that counts. The W3Schools read in `a-read-git-intro-page` still has to
  follow, and what to budget for it is its session and not its reading: the page is two or three
  minutes, the session built on it is billed at 25 to 30, and taking this activity first is what
  makes it shorter, though by how much neither entry commits to. Offer the picture on its merits,
  and say that the short read follows.
  `done when` asks for all eight words placed somewhere the learner can point at, but three of
  them (diff, merge, merge conflict) have nowhere on the page to go and arrive from you. Read that
  half of `done when` as a completeness check on the sketch rather than as evidence about those
  three. Nothing here is evidence about any word; the word goals have their own supply.
  Take the prediction from the figures before you say anything at all, and have it written down.
  You answer it before the read rather than after, so the page itself never checks it, and an
  unwritten prediction quietly becomes "yes, that is what I thought."
  No `kind` is given; treat it as a single instance.

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
- **check note:** This is the only place in the topic where the learner sees real commands and
  real output, and the depth in `goals.md` allows it on one condition: that someone is narrating
  it as it goes. The narration is the load-bearing part, not the output. Do not leave anything on
  screen unexplained while you move on, do not hand them a hunk to work out for themselves, and if
  they ask what a line means, answer it rather than turning it into a test. Making sense of output
  unaided is still past the line for this course; watching you make sense of it is the whole point
  of the exception.
  Because the commands are visible here, the predictions slide easily. `learner does` asks what
  they would ask an agent for at that point and what they expect it to tell them back, not what
  command comes next. If a prediction comes back as a command, take it, then put the question again
  in the form the entry asks for. That form is what they will need in `a-commit-restore-drill` and
  in their own sessions, and this is the one activity where the screen is quietly pulling them the
  other way.
  Get each prediction said out loud before you act, and written down. The entry asks them to write
  the divergences afterwards, which is how a prediction quietly turns into "yes, that is what I
  thought." The record has to exist before the reveal or it is worth nothing.
  Make the false start land. Trying to recover a change that was never committed, and finding it
  simply gone, is the only place in this topic the learner is shown that case, and nothing
  afterwards examines it, not here and not in either check. Give it room, and say plainly that this
  is the one failure their agent cannot undo for them.
  Two smaller things. The two requests they write at the end are worth keeping: that is the wording
  they will reuse when they reach `a-commit-restore-drill`. And seeing "staging area" or a diff on
  screen settles none of the word goals, which come from their own supply. No `kind` is given here;
  treat it as a single instance.

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
- **check note:** Write the session down as it happens, the learner's requests and your replies as
  the played agent, verbatim. The adjudicator for this goal is a fresh judge who was not in the
  room, and this entry, unlike `a-commit-own-repo`, preserves nothing for them to rule on.
  Two places to run this harder than it reads. `learner does` has them open one wrecked file, but
  the criterion says all files, and on a Medium or Hard instance the deleted or renamed one is
  exactly what a learner will not think to open, so have them account for every damaged thing
  rather than one. And the Hard instance's new file, the one no commit contains, is built into the
  material but nothing asks the learner to notice it: ask them what cannot come back and why,
  because nothing else in this topic examines that.
  Easy is for the worked example and for a second try with help. A pass at Easy does not clear the
  goal.

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
- **check note:** Set the recovery target before they start. `tutor role: none` describes the run
  only, and the generator does not work without you: which commit you name is the difference
  between a first run and one that reaches the "any commit" half of the criterion.
  A first run, aimed at the commit they just made, does not clear this goal however well it goes,
  for the reason the entry's own `doesn't show` gives. Only a later run, aimed at an earlier
  session's commit, reaches the whole criterion. Do not log a first run as met.
  Their agent's "nothing is uncommitted" is a claim, not proof, and it is the kind of claim this
  topic teaches them not to take on trust. Untracked and ignored files are what it routinely
  misses, and the scratch note covers one file, not the tree they are about to send backwards. Look
  at the repository yourself before a whole-tree restore to an earlier session's commit, or keep
  that move in `a-commit-restore-drill`, where the repository is a throwaway.
  When they ask the agent which commit came before today's work, expect the answer to arrive with
  hashes and dates in it. Tell them beforehand that they can ask for it in words and do not have to
  read the rest. Expect the transcript you read afterwards to contain commands and diffs their own
  agent printed, which is not the same thing as the learner having been asked to interpret them.


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
