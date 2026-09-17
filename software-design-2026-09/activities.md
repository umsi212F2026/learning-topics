# Activities — software design

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `c-write-success-criteria` | say what done looks like for an app, in a form anyone could check | For an app idea, their own or one they are given, first says in a sentence or two what the app is for, in their own words, then writes the success criteria they would want in its spec. It passes when someone who never heard the idea could use the finished app and say of each criterion whether it was met, and when an app that runs but misses what they said it is for would fail at least one of them. A list of the app's features does not count as saying what it is for. |
| `c-choose-approach` | choose between approaches an agent proposes, for a reason that belongs to this app | Given two or three approaches to the same app, each with its tradeoffs, and a description of the app's situation that includes facts with no bearing on the choice, picks one, says what that choice gives up, and gives a reason that comes from something in the app's situation as described. A reason that would hold for any app, including that the agent recommended it, does not meet it. |

## Coverage

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `c-write-success-criteria` | `a-read-brainstorming-skill`, `a-read-spec-kit-post`, `a-critique-agent-excerpt`, `a-judge-spec-kit-criteria`, `a-outwit-literal-builder` | `a-criteria-for-pitch`, `a-criteria-for-own-idea` | |
| `c-choose-approach` | `a-read-brainstorming-skill`, `a-read-spec-kit-post`, `a-critique-agent-excerpt`, `a-sort-choice-reasons`, `a-same-options-two-situations` | `a-choose-from-proposals`, `a-choose-in-own-brainstorm` | |

---

## Activities

### `a-read-brainstorming-skill`

- **serves:** `c-write-success-criteria`, `c-choose-approach`
- **supports:** orient
- **artifact:** Superpowers, `skills/brainstorming/SKILL.md`, the instructions the learner's own
  coding agent follows when it designs an app with them. Pinned to release v6.3.0 (August 12,
  2026), which is also what `main` holds as of September 17, 2026:
  https://github.com/obra/superpowers/blob/b36e0829c6d0140e93cfef2ca599b1b07d4a7797/skills/brainstorming/SKILL.md
  (free, no account). The copy installed for the course may be a later version. About 2,300
  words, of which the last 300 are the "Visual Companion" section and about 260 are a flow diagram
  written as graph code; 15 minutes of reading, 30 to 40 for the activity. It is written to the
  agent, not to the person, and calls the learner "your human partner" or "the user". It names in
  place: spike (one of its three paths), spec (the design doc it writes and asks the person to
  review), plan (the writing-plans step that follows the spec), success criteria and constraints
  (what its clarifying questions are for), architecture (a section of the design it presents), and
  YAGNI ("YAGNI ruthlessly"). It does not name MVP or tech stack. The two capabilities in this
  topic each have a step of their own in its Architectural checklist: step 3, clarifying questions
  asked one at a time to understand purpose, constraints and success criteria, and step 4, two or
  three approaches proposed with trade-offs and the agent's recommendation.
- **verified:** 2026-09-17
- **learner does:** reads the file top to bottom, stopping at any term they cannot restate in their
  own words (spec, plan, spike, YAGNI, architecture, success criteria, constraints, approval gate):
  says what they think it means, or that they have nothing, and hears it explained before reading
  on. Then goes back to the Architectural checklist, the path a new app gets, and for each of its
  nine steps says one line: what the agent will ask me or put in front of me here, and whether I
  have to answer, choose, approve, or do nothing. Finishes by naming the step where they will be
  asked what success looks like and the step where they will be asked to pick an approach, and
  says which of the two they expect to find harder, and why.
- **tutor role:** explainer
- **tutor does:** explains on demand, in the file's order, and does not lecture ahead of the
  question. Translates "your human partner" as "you" whenever it gets in the way. Steers past the
  flow diagram, the "Design for isolation and clarity" and "Working in existing codebases"
  subsections, and the Visual Companion section, saying they are the agent's business: how the app
  is organized inside is the agent's to work out, per the depth in `goals.md`. Makes sure four
  points land, and raises any the learner does not: the agent asks one question per message and
  prefers multiple choice, so the learner's answers are short but come often; the agent leads with
  its own recommendation, so the learner will be choosing with a recommendation already in front of
  them; the spec is written only after the learner has approved the design section by section, and
  the learner is then asked to review the spec before any plan is written; and the Spike and
  Bounded paths write no spec at all, so on a small change the clarifying questions are the only
  place to say what done looks like. Ends by putting the question directly: with this file beside
  you, could you now take part in a brainstorming session for your own app idea, answer what it
  asks you about success, and pick among the approaches it offers?
- **done when:** each of the nine Architectural steps has a line saying what it asks of the
  learner, and the learner has named the step where they will be asked what success looks like and
  the step where they will be asked to pick an approach.
- **offer as:** the source itself: the actual instructions your agent will follow in the lab, read
  from the agent's side, so nothing in your own session comes as a surprise. The most exact of the
  two orienting reads and the least friendly, because it is written to an agent as rules and red
  flags and never explains why a spec comes before a plan. `a-read-spec-kit-post` is the
  explanation written for people; take this one if you want to know precisely what your own agent
  will do and when it will stop and wait for you.

### `a-read-spec-kit-post`

- **serves:** `c-write-success-criteria`, `c-choose-approach`
- **supports:** orient
- **artifact:** Den Delimarsky, "Spec-driven development with AI: Get started with a new open
  source toolkit", The GitHub Blog, September 2, 2025,
  https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/
  (free, no account; about 1,900 words, billed as 9 minutes; 30 minutes for the activity). Written
  for developers about GitHub's Spec Kit, which is a different tool from the Superpowers skills
  the course uses, but it explains the same sequence in plain prose: Specify ("what you're
  building and why", "what success looks like"), Plan ("your desired stack, architecture, and
  constraints", and "multiple plan variations to compare and contrast different approaches"),
  Tasks, Implement. It names spec, plan, stack, architecture and constraints in place, and
  describes success criteria without using the phrase. It does not name MVP, YAGNI or spike. One
  install command appears in the middle and can be skipped.
- **verified:** 2026-09-17
- **learner does:** reads it once through, stopping at any term they cannot restate (spec, plan,
  stack, architecture, constraints) to say what they think it means and hear it explained. Then,
  without looking back, writes one line each for Specify and for Plan: what that document is
  about, and what the person, not the agent, has to do at that step. Then finds the two sentences
  that give the person's role ("Your primary role is to steer", and later "your role isn't just to
  steer. It's to verify.") and says what steering and what verifying would each look like in their
  own lab session.
- **tutor role:** explainer
- **tutor does:** explains on demand and does not lecture ahead of the question. Corrects one thing
  the post gets wrong for this learner, and raises it if the learner does not: the post has the
  person supply the stack and the architecture at the Plan step, but at this topic's depth which
  technologies the app uses and how it is organized inside are the agent's to work out. What stays
  the learner's is the constraints only they know (who will use it, how long it has to last, when
  it is needed) and the choice between approaches by what each would mean for the app. Ties "what
  success looks like" in the Specify step to `c-write-success-criteria`, and "compare and contrast
  different approaches" to the moment in their own session when the agent offers two or three and
  recommends one. Ties verifying, at this topic's depth, to what the learner reviews and approves
  before anything is built: each section of the design as the agent presents it, and then the spec,
  before any plan is written. If the learner answers with testing the finished app, says that
  checking the app against what was agreed is a later topic, and asks what there is to verify before
  any code exists. Treats Tasks and Implement as things to know exist and no more. Ends by asking
  directly: with this post beside you, could you now take part in designing an app with your agent,
  say what done looks like, and choose among the approaches it proposes?
- **done when:** both one-line summaries exist, and the learner has said what steering and verifying
  would each look like in their own session, with verifying placed at the approvals of the design
  and the spec rather than at testing the finished app.
- **offer as:** the explanation written for people rather than for the agent: why the document
  about what gets built comes before the document about how, in nine minutes of plain prose.
  Gentler than `a-read-brainstorming-skill` and less exact about your own agent, since it
  describes a different tool whose steps only roughly line up with the one you will use, and it
  hands you technology decisions this course leaves to the agent. Take it first if the skill file
  reads like rules without reasons.

### `a-critique-agent-excerpt`

- **serves:** `c-write-success-criteria`, `c-choose-approach`
- **supports:** deepen
- **artifact:** no external source. An excerpt from a brainstorming session that the tutor builds
  fresh each time, as described in `tutor does`, laid out the way the agent in
  `a-read-brainstorming-skill` presents its approaches and then its design. 25 to 30 minutes.
- **verified:** 2026-09-17
- **learner does:** reads the pitch and the person's answers to the agent's questions, then the
  agent's messages one at a time, as if they were that person in the session. Before approving
  each message, writes what they would ask the agent or push back on, as the message they would
  actually send, or says they would approve it as it stands and why. Is not told how many problems
  there are, or whether there are any. Reads the agent's reply to each pushback and says whether it
  settles the point before moving on. At the end, says which of their pushbacks would change what
  gets built, and how.
- **tutor role:** critique target
- **tutor does:** builds the excerpt before the session, and writes where the learner cannot see it
  a list of what is planted. The excerpt opens with a pitch made as in the generator in
  `a-criteria-for-pitch` at Easy, followed by the person's answers to the agent's clarifying
  questions: a sentence on what the app is for, the constraints (who uses it, on what devices, how
  long it has to last), and three or four success criteria that someone who never heard the idea
  could settle by using the finished app. Then come two messages from the agent, in the voice of a
  coding agent following the brainstorming skill: first two or three approaches with trade-offs,
  one of them recommended; then the design section that restates what the app is for and its
  success criteria. Plants two to four flaws, at least one in each message, drawn from this list
  and varied across instances: the approaches are named and argued only as technologies ("a
  real-time database: live sync, flexible schema"), with nothing on what each would mean for the
  people using the app; two of the approaches differ only in technology and would give the same
  app; the recommended approach has pros and no cons; the recommendation's reason would hold for
  any app ("the most scalable"); one of the person's criteria is reworded into one nobody could
  settle by using the app ("the app is intuitive", "sign-ups sync reliably"); one of the person's
  criteria is dropped, or replaced by a feature ("has a sign-up page"); the purpose is restated as
  a list of what the app does. Also leaves at least one thing that looks suspicious and is sound:
  an approach named by a technology whose description does say what it means for the app, or a
  reworded criterion that anyone could still settle. Shows the pitch and the answers, then each
  agent message in turn, and does not hint. Answers each pushback in role, as the agent: a specific
  pushback gets a real revision; a vague one ("can you make that clearer?") gets a reworded message
  that keeps the flaw, so the learner has to say what exactly is wrong. If the learner approves
  everything without a single pushback, asks them, before revealing anything, to say why each
  message was fine, to tell having understood from having given up. After the last message, steps
  out of role and goes through the list: for each flaw the learner did not catch, asks what the app
  would have been if they had approved it; for each pushback on something that was sound, asks
  what the change would have cost.
- **done when:** every agent message has a pushback or an approval with a reason, and every planted
  flaw has been either caught or, after the reveal, explained by the learner in terms of what
  approving it would have done to the app. This entry carries no `checks`: neither criterion in
  `goals.md` asks for judging what an agent hands over, so nothing here can settle a goal.
- **offer as:** the one that puts in front of you what an agent actually hands over, flaws and all:
  approaches argued as technologies, a recommendation with its costs left out, your criteria
  reworded into ones nobody could check. The closest thing here to the moments in your own session
  when the agent waits for your approval, and the only one where the agent answers back. Uses both
  halves of the topic at once, so it suits a learner who has already done something for each goal.
  Works on a pitch, so no idea of your own is needed.

### `a-judge-spec-kit-criteria`

- **serves:** `c-write-success-criteria`
- **supports:** deepen
- **artifact:** two short passages from GitHub's Spec Kit, which tell a coding agent how to write
  success criteria. (1) The "Success Criteria Guidelines" subsection near the end of
  https://github.com/github/spec-kit/blob/b60057692cd726ea56331ec47f9ebc3e8877d8f7/templates/commands/specify.md
  (pinned to September 9, 2026): four rules (measurable, technology-agnostic, user-focused,
  verifiable), four "Good examples" and four "Bad examples". (2) The "Success Criteria" section of
  https://github.com/github/spec-kit/blob/756d63212987152564ed0a52ddfd7f8e9b504e09/templates/spec-template.md
  (pinned to May 12, 2026), whose placeholders SC-001 to SC-004 each carry an example. Twelve
  example criteria in all, under 300 words; 25 to 30 minutes for the activity. Everything else in
  both files is agent machinery and is not part of this.
- **verified:** 2026-09-17
- **learner does:** does not open the files. Takes the twelve examples as the tutor shows them, one
  at a time with no label, and for each says whether a person who has never heard of the app could
  use the finished app and say whether the criterion was met, and if so, what that person would do
  to find out. Once Spec Kit's label for it is revealed, marks any disagreement between their ruling
  and the label, and says why. Then picks an app of their own choosing, says in a sentence what it
  is for, and rewrites two of the examples that failed so that one person using that app could
  settle them. Last, says what Spec Kit's four rules never ask about a set of criteria, however well
  each one is written.
- **tutor role:** socratic questioner
- **tutor does:** before the session, pulls the twelve examples out of the two files and strips
  everything around them: headings, the "Good" and "Bad" labels, the SC numbers, the rules, and any
  suggested fix or comment beside an example. Shuffles them so that good and bad are mixed. Shows
  them one at a time and stays quiet on each until the learner has ruled on it. Where a ruling
  looks wrong, asks what the person would actually do with the finished app to decide, rather than
  giving the answer. Then reveals Spec Kit's label for that example ("Good", "Bad", or offered as
  the example for one of SC-001 to SC-004), with Spec Kit's suggested fix where it gives one, before
  showing the next. After the twelfth, shows the four rules. Holds this key and accepts a
  well-argued disagreement with it: "Users can complete checkout in under 3 minutes" and SC-001
  ("Users can complete account creation in under 2 minutes") can be settled by one person with a
  timer. "System supports 10,000 concurrent
  users", SC-002, SC-003 ("90% of users successfully complete primary task on first attempt"),
  SC-004 ("Reduce support tickets ... by 50%") and "Task completion rate improves by 40%" need many
  users, a baseline, or a support desk, so no one person using the app can settle them, though
  Spec Kit labels or offers every one of them as good. "95% of searches return results in under 1
  second" is arguable. The four "Bad examples" fail this test too, and not only for naming a
  technology, and "Users see results instantly", the fix Spec Kit suggests for one of them, can be
  settled only once "instantly" means something. If the learner does not reach the last question
  alone, asks: imagine an app that meets all four good examples and is still useless for what it
  was built for; which of the four rules would have caught that? (None: they judge each criterion
  on its own.)
- **done when:** every example has a ruling with a reason, two failing ones have been rewritten
  for an app whose purpose the learner stated first, and the learner has said what the rules miss
  about a set of criteria taken together.
- **offer as:** judging criteria someone else wrote before writing your own, and the someone is a
  widely used agent tool rather than examples invented for the exercise, so you also see what an
  agent may hand you. Short, and needs no app idea to start. Its limit: every example is judged on
  its own, so it exercises only the half of the goal about whether a stranger could check a
  criterion, never whether a set of them would catch an app that misses its point.
  `a-outwit-literal-builder` is the one that does.

### `a-outwit-literal-builder`

- **serves:** `c-write-success-criteria`
- **supports:** deepen, attempt
- **artifact:** no external source. An app idea, either a pitch made by the generator in
  `a-criteria-for-pitch` at Easy or Medium, or an idea of the learner's own; the tutor plays a
  builder. 20 to 30 minutes.
- **verified:** 2026-09-17
- **learner does:** says in a sentence or two what the app is for, then writes the success
  criteria they would want in its spec. Hands both to the builder, reads the builder's description
  of the app it would ship, and revises: rewrites the purpose sentence, rewrites criteria, adds or
  removes them. Repeats until the builder can no longer find a way through, or four rounds have
  run. After each round, writes one line saying what the builder exploited.
- **tutor role:** role-play partner
- **tutor does:** plays a builder who has never heard the idea, is given only the learner's
  purpose sentence and criteria, and wants to finish as fast as possible, but is honest: it reads
  the purpose sentence in good faith and never sets out to defeat it. Each round, in role, says two
  things. First, an app such a builder might plausibly ship, working only from the purpose sentence
  and the criteria, that meets every criterion to the letter and still fails the stated purpose,
  described in two or three sentences as what a user would see and be able to do; or, if it can
  find none, says so. Plausible means a hurried builder could ship it believing it served the
  purpose: a club sign-up sheet whose list shows only on the phone it was made on, when the point
  was that every officer sees who is coming. It does not mean a trick no honest builder would
  think of: a chore rota that gives every chore to the same person, when the purpose sentence says
  nobody should feel they do more than their share. Second, any criterion it could not tell it had
  met just by using what it built ("I can't tell whether 'easy to use' is met"). Suggests no fixes.
  Stops after four rounds even if the builder still gets through. At the end, steps out of role
  and asks which of the learner's first criteria were really features, and which revision did the
  most work. If the builder still got through after four rounds, also goes through the gap that is
  left: what the last app shows the criteria still fail to catch, and what kind of criterion would
  catch it. The activity is then not done, and a later session picks it up from the learner's last
  revision. If the idea came from a pitch, also compares the learner's purpose sentence with the
  pitch and asks whether it says what the app is for or restates what it does.
- **done when:** in role, the builder can find no app it might plausibly ship that meets every
  criterion and still misses the stated purpose, and can say of every criterion whether it was met.
  Four rounds that end with the builder still getting through do not meet this. This entry carries
  no `checks`: the builder does the examining round by round and points at each weakness, which is
  the work the criterion wants the learner's criteria to survive without anyone's help.
- **offer as:** hands-on and adversarial: you write criteria and someone tries to satisfy them
  while building the wrong thing, so every weakness comes back as a concrete bad app rather than a
  comment. The fastest way to feel why a list of features is not a set of success criteria.
  Needs a live session, and works better with a small idea than a big one.

### `a-criteria-for-pitch`

- **serves:** `c-write-success-criteria`
- **supports:** attempt
- **checks:** `c-write-success-criteria`
- **artifact:** no external source. A pitch the tutor generates per the generator below and shows
  in the session, so that it is in the transcript word for word. 15 to 20 minutes.
- **verified:** 2026-09-17
- **learner does:** reads the pitch, as many times as they like, and asks nothing about the idea.
  Writes, in order: a sentence or two saying what the app is for, in their own words; then the
  success criteria they would want in its spec, as a list, written for someone who will never see
  the pitch and has only the purpose sentence and the finished app. Submits both as written.
- **tutor role:** none
- **tutor does:** generates the instance before the session and writes the key (see the generator)
  where the learner cannot see it. Shows the pitch and waits. Afterwards sends the attempt to the
  judge in the usual way; the transcript has to hold the pitch and the learner's text verbatim. An
  attempt on an Easy instance is never sent to the judge, and is recorded with
  `criterion: unchecked`. The key is for the debrief and is not sent to the judge, which is not
  given the tutor's view. After the ruling, pass or not, plays one round of the builder from
  `a-outwit-literal-builder` against the learner's criteria, so they see what a miss would look
  like, and then goes through the key.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** write a pitch of four to six sentences in the voice of someone who wants the app
  built: a friend, a student organization officer, a small shop owner, a coach, a relative. The app
  is small enough to build in a lab session or a problem set: an interactive app with some state,
  or, for an instance aimed at Problem Set 2, one where several people see and change the same
  data. Vary the domain (campus life, a club, a household, a small business, a hobby, a class), who
  the app is for (the person pitching, a group they belong to, their customers), and what prompted
  it (a recurring annoyance, a missed deadline, an argument, a lost sale). Hold fixed: the pitch
  names at least three things the app should do; it never states the app's purpose in a sentence
  the learner could copy, so the purpose has to be read off the situation; and the purpose is
  served by something the finished app shows or lets someone do, not only by an outcome visible
  over months or across many people, so criteria a stranger could check are able to capture it.
  Easy: the situation states the problem plainly and each named feature maps directly onto it.
  Medium: the pitch leads with its feature list, and the problem appears in a single sentence of
  situation. Hard: every feature the pitch names could be built and the app would still miss what
  it is for (a chore rota whose point is that nobody feels they do more than their share, pitched
  as a list of chores with checkboxes and reminders), or one named feature works against the
  purpose. Counted attempts run at Medium or Hard, because at Easy the named features line up with
  the purpose so closely that a feature list can pass the runs-but-misses half by accident. Easy is
  for the worked example and for a retry with help. The key, written before the pitch is shown: one
  sentence on what the app is for, and a description of one app that has every named feature and
  still misses that purpose. A different purpose the pitch supports is acceptable in the debrief;
  the key is a reference, not the answer.
- **worked example:** work one Easy instance live, out loud. Read the pitch, then say a
  feature-list version of the purpose first ("it's an app with a list, checkboxes and reminders"),
  say why that describes what it does rather than what it is for, and replace it. Write three
  criteria, and for each one say what a stranger would do with the finished app to decide whether
  it was met. Then describe an app a hurried but honest builder might ship that meets all three,
  and ask whether it misses the purpose; if it does, add the criterion that catches it. At the
  first level of help, give only the question: what would the person who pitched this be
  disappointed by, even if every feature they named worked?
- **doesn't show:** a pitch hands the learner a complete, tidy situation written to exercise this
  criterion, so a pass does not show they could do the same with the half-formed idea of a real
  brainstorming session, or that they would notice what they had not been told. The judge reads
  the pitch along with the criteria, so it is not quite the someone who never heard the idea: a
  criterion that leans on a detail only the pitch gives ("Dana can see who hasn't paid") can look
  checkable to it and would not be to a stranger. It does not show they would keep the agent to
  these criteria once it proposes its own wording in the spec. And it says nothing about checking
  the finished app against the criteria, which is a later topic.
- **offer as:** practice on someone else's idea, where nothing of yours is at stake, the difficulty
  is set, and every instance is new, so it can come back in review as often as needed. The only
  check here that controls how hard the idea is. It feels more artificial than your own idea, and
  a pitch is tidier than anything a real person says.

### `a-criteria-for-own-idea`

- **serves:** `c-write-success-criteria`
- **supports:** attempt
- **checks:** `c-write-success-criteria`
- **artifact:** no external source. The learner's own app idea: the one they bring to the in-class
  lab where their agent designs an app with them, the Problem Set 2 app, or any other. 15 minutes,
  before the brainstorming session for that idea starts.
- **verified:** 2026-09-17
- **learner does:** in a study session with the tutor, before starting the brainstorming session
  and before telling any agent anything about the idea, writes a note straight into the tutor
  session: first a sentence or two saying what the app is for, in their own words; then the success
  criteria they would want in its spec. Says nothing else about the idea in that session, before or
  after the note. Later, starts the brainstorming session, and may paste the note in when the agent
  asks about success.
- **tutor role:** none
- **tutor does:** runs it at the start of a session, before anything about the idea has come up; if
  something has, the note waits for a session of its own. Asks first whether any agent has heard
  the idea yet; if one has, there is no instance. Then sets the task and waits: the note is written
  alone. As soon as the note is in, sends the judge the transcript up to and including it, which
  holds nothing about the idea but the note, because the judge is exactly the someone who never
  heard it. Labels the attempt with the occasion and the date after a slash, never with anything
  that describes the app (`a-criteria-for-own-idea/lab-2026-09-24`, `/ps2-2026-10-08`,
  `/other-2026-10-15`), because the label reaches the judge too. In a later session, once the agent
  has written its spec, asks the learner whether the spec kept their criteria or rewrote them, and
  which version they would rather have the app held to.
- **done when:** criterion met with no help, on a note written, as the transcript records, before
  any agent had heard the idea. Criteria written after an agent's questions, or taken from its spec,
  are not an instance however good they are.
- **kind:** generator
- **generator:** the instance is whichever app idea the learner currently has, so what varies is
  the idea, and each idea is used once; ideas that differ only in wording are the same idea.
  `served.mjs` lists the occasions and dates already used, and the tutor asks the learner whether
  this idea is one they wrote a note for then. Hold fixed: the note is written in the tutor session
  before any agent has heard the idea, the learner says nothing else about the idea there, and the
  judge gets that transcript and a label that says nothing about the app. Difficulty is not
  controlled. If the idea is so small that saying what it does and saying what it is for come to
  the same thing, run `a-criteria-for-pitch` at Medium or Hard instead. If the learner has no new
  idea, there is no instance; run `a-criteria-for-pitch`.
- **worked example:** the worked example from `a-criteria-for-pitch`, done on a generated pitch and
  never on the learner's own idea, so that nothing in their note is borrowed from it. At the first
  level of help: what would disappoint you about this app even if every feature you have in mind
  worked?
- **doesn't show:** the learner knows their own idea far better than any pitch, so saying what it
  is for is easier here, and the judge standing in for a stranger is the only protection against
  criteria that lean on what is in the learner's head. That no agent had heard the idea before the
  note rests on the learner's word in the transcript. How hard the instance is goes uncontrolled,
  so a pass on a very small idea says little. A learner has only a few ideas a term, so this entry
  cannot carry review for months; `a-criteria-for-pitch` has to. And it does not show they will
  hold the agent to these criteria once it proposes its own.
- **offer as:** the real thing, on the idea you actually care about, at the moment the course will
  ask it of you, so what you write goes straight into your lab session. Nobody watches while you
  write it. The catch is one attempt per idea, and a small idea makes it easy.

### `a-sort-choice-reasons`

- **serves:** `c-choose-approach`
- **supports:** deepen
- **artifact:** no external source. A set the tutor builds fresh each time, as described in `tutor
  does`. 15 to 20 minutes.
- **verified:** 2026-09-17
- **learner does:** reads a situation description for a small app, the two or three approaches an
  agent offered for it, and which one a classmate picked. Then sorts eight reasons the classmate
  might give for that pick into groups of their own making, with no categories supplied, and names
  each group. Then states in one sentence the rule that separates a reason that belongs to this app
  from the rest. Then writes a reason of their own for the classmate's pick, one that is not among
  the eight, and what the pick gives up.
- **tutor role:** socratic questioner
- **tutor does:** builds the set before the session. The situation and approaches are made as in
  the generator in `a-choose-from-proposals` at Medium, except that the description carries three
  facts that bear on the choice, all favoring the same approach, and the classmate's pick is that
  approach. Eight reasons for that pick, shuffled: two drawn from facts that bear on the choice, one
  from each of two of those three facts, so that the third bearing fact appears in no reason; two
  that would hold for any app ("it's simpler", "it's what the agent recommended", "it scales
  better", "it's the modern way"); two drawn from facts in the description that have no bearing on
  this choice; one drawn from a fact that is not in the description at all but sounds as if it
  might be; and one that only restates the approach's own pros. Does not reveal how the set was
  built until the learner has stated a rule and written their own reason. Then, for any reason the
  rule put in the wrong group, asks what would have to be true of the app for it to count, and asks
  the learner to strike from the description every fact their rule says had no bearing. Uses a new
  situation every time.
- **done when:** the learner's rule sorts a fresh reason the tutor makes up on the spot; the reason
  they wrote for the pick comes from a fact that bears on the choice and that none of the eight
  reasons used; and they have said what the pick gives up.
- **offer as:** recognition before production: somebody else's reasons, sorted, so you find the
  line between a reason about this app and a reason about any app before you have to write one.
  Quick and cheap to repeat. The rule you state at the end is the thing to take into a check.
  `a-same-options-two-situations` has you choose and justify from the start instead.

### `a-same-options-two-situations`

- **serves:** `c-choose-approach`
- **supports:** deepen
- **artifact:** no external source. A pair of situations the tutor builds fresh each time, as
  described in `tutor does`. About 20 minutes.
- **verified:** 2026-09-17
- **learner does:** reads a situation description and the two or three approaches offered for it;
  picks one, says what the pick gives up, and gives the reason. Then reads a second situation for
  what looks like the same app, with the same approaches, and does the same without changing the
  first answer. Only then puts the two side by side and says which facts made the picks differ,
  and which facts appeared in either description and made no difference. If they picked the same
  approach both times, says whether that was right, and if not, which fact they read past.
- **tutor role:** socratic questioner
- **tutor does:** builds the pair before the session. The approaches are made as in the generator
  in `a-choose-from-proposals`, with no recommendation marked. The two situations share most of
  their sentences and differ in one or two facts that change which approach fits (only the person
  pitching uses it, on one phone, against six club officers who all need to see the same list; it
  is for one event next Saturday, against it has to last the whole year). Each also carries two or
  three facts with no bearing on the choice, and at least one of those differs between the two
  descriptions too, so that spotting what changed is not enough to find what mattered. Shows the
  first situation alone and gets the first answer before showing the second. Afterwards asks, of
  each reason the learner gave, whether it would have been just as true in the other situation,
  and if so why it was a reason at all.
- **done when:** the learner has named the fact or facts that changed the choice, and has said of
  each of their own reasons whether it would have held in the other situation. This entry carries
  no `checks`: the second situation points back at what mattered in the first, which is part of
  the work the criterion wants done alone.
- **offer as:** the one that shows the same approaches can be right for one app and wrong for
  another, which is what a reason that belongs to this app comes down to. More active than
  `a-sort-choice-reasons`, since you choose and justify from the start rather than sorting someone
  else's reasons, and a little longer.

### `a-choose-from-proposals`

- **serves:** `c-choose-approach`
- **supports:** attempt
- **checks:** `c-choose-approach`
- **artifact:** no external source. An instance the tutor generates per the generator below, laid
  out the way a brainstorming agent presents approaches, and shown in the session so that it is in
  the transcript word for word. 10 to 15 minutes.
- **verified:** 2026-09-17
- **learner does:** reads the situation and the approaches, and asks nothing about the app. Writes
  a reply they could send to the agent, a few sentences long: which approach they pick, what that
  pick gives up, and why.
- **tutor role:** none
- **tutor does:** generates the instance before the session and writes the key (see the generator)
  where the learner cannot see it. Shows the instance and waits. Afterwards sends the attempt to the
  judge in the usual way; the transcript has to hold the instance and the reply verbatim. An attempt
  on an Easy instance is never sent to the judge, and is recorded with `criterion: unchecked`. The
  key is for the debrief and is not sent to the judge. After the ruling, goes through the key with
  the learner: which facts bore on the choice, which did not, and whether the recommendation, if
  there was one, fit.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** write a situation description of six to nine sentences for a small app of the
  kind built in a lab session or a problem set: who uses it and how many of them, on what devices,
  how long it has to last, who will look after it, when it is needed, and what the person already
  has. Include two or three facts that bear on the choice and two or three that do not (the app's
  name or colors, the year a club was founded, that the person prefers dark mode, which laptop they
  own). Then write two or three approaches the way a brainstorming agent offers them: a short name,
  two sentences on what the approach means for the app and the people using it, and its pros and
  cons. The two sentences and the pros and cons speak about the approach in general, as they would
  for any app of its kind, and never mention a fact from this situation: "everyone with the link
  sees the same list", never "fits, since all six officers need the list". The approaches differ in
  what the app does for people, not only in which technology is used: data kept on one device
  against data shared by everyone who uses it; one core task working completely against every
  feature working partly; an off-the-shelf form or spreadsheet against a custom app; changes seen
  live against changes seen on refresh; open to anyone with the link against signing in. Where an
  approach is named by a technology, its description still says what that means for the app. Hold
  fixed: every approach would work; none is best in every situation; each one's cons are real; and
  the reply asked for is always the pick, what it gives up, and the reason. Easy: two approaches,
  one fact decides it and is stated plainly, one fact with no bearing, no recommendation. Medium:
  three approaches, one marked "(recommended)" with a one-sentence justification that would hold for any app ("the most flexible"); two relevant facts
  pointing the same way; two or three facts with no bearing. Across instances, vary whether the
  recommended approach is the one the facts favor, so that neither following it nor avoiding it
  works as a strategy. Hard: as Medium, except the relevant facts pull in different directions, so
  the pick has a real cost that has to be named, and at least one fact with no bearing sounds
  technical and important ("their laptop has 16 GB of memory"). Counted attempts run at Medium or
  Hard; Easy is for the worked example and for a retry with help. The key, written before the
  instance is shown: which facts bear on the choice and in which direction, which do not, which
  approach fits best, and what it gives up. A different pick is acceptable in the debrief if its
  reason comes from a fact that bears on it; the key is a reference, not the answer.
- **worked example:** work one Easy instance live, out loud. Read the approaches first and say what
  each would mean for the people using the app. Then read the situation and strike out each fact
  with no bearing, saying why. Make one false start on purpose: pick for a reason that would hold
  for any app ("the simpler one is always better"), notice that it would be just as true of any
  other app, and replace it with the fact in the description that actually decides it. Finish with
  what the pick gives up, in one sentence. At the first level of help, ask only: which sentence in
  the description, if it were different, would change your pick?
- **doesn't show:** the instances are built to have a defensible answer and clean trade-offs, and a
  real agent's proposals are messier: it may offer approaches that differ only in technology, leave
  out the cons of the one it recommends, or ask before the learner knows enough to choose. A pass
  does not show the learner would notice any of that. The situation arrives complete, so it does
  not show they would know which facts about their own app to tell the agent in the first place.
  And a written reply does not show they would hold to a choice when a live agent argues back.
- **offer as:** controlled practice: a fresh instance every time, difficulty set, and a
  recommendation that is sometimes wrong for the situation, which is the pressure a real agent
  puts on you. Short, and it can come back in review as often as needed. Tidier than a real
  session; `a-choose-in-own-brainstorm` is the one that isn't.

### `a-choose-in-own-brainstorm`

- **serves:** `c-choose-approach`
- **supports:** attempt
- **checks:** `c-choose-approach`
- **artifact:** no external source. The learner's own brainstorming session with their coding agent,
  in the in-class lab or on Problem Set 2, at the step where the agent proposes two or three
  approaches (step 4 of the Architectural checklist, see `a-read-brainstorming-skill`), and the
  transcript of that session. About 10 minutes at that step, plus reading the transcript
  afterwards.
- **verified:** 2026-09-17
- **learner does:** at the start of the session, tells the agent: when you propose approaches, give
  me each one with its trade-offs stated in general, without saying which things I have told you
  about my app make it fit or not, and do not tell me which you recommend until I have chosen. When
  the approaches arrive, writes their reply before asking the agent anything else: which approach,
  what it gives up, and why, in terms of the app as they have described it so far. Sends it, then
  asks for the agent's recommendation and notes whether it agreed. Keeps the whole transcript.
- **tutor role:** none
- **tutor does:** waits: the session is the learner's. The situation the criterion speaks of is
  everything the learner and the agent had established about the app before the approaches
  arrived; whatever in it has no bearing on this choice is the criterion's facts with no bearing.
  Afterwards reads the transcript up to and including the learner's reply and decides, by the rules
  in `done when`, whether it holds an instance. If it does, sends the judge that part of the
  transcript in the usual way; if not, sends nothing and records the attempt with
  `criterion: unchecked`. Then reads the rest of the transcript with the learner and asks: if the
  agent recommended something different, what would it have had to know about your app to be
  right?
- **done when:** criterion met with no help. If the agent tied an approach to the app anyway,
  whether by recommending it with reasons or by trade-offs that name something established about
  the app ("fits, since all six officers need the list"), and the learner's reason repeats a link
  the agent already made, the attempt is `unaided: unclear`. There is no instance if the agent
  offered only one approach, or approaches with no trade-offs: ask it for two or three with
  trade-offs, or run `a-choose-from-proposals` instead. There is also no instance if no set of
  approaches in the session differs in what it means for the app, or if nothing established before
  the approaches arrived is without bearing on the choice; in either case run
  `a-choose-from-proposals` at Medium or Hard instead.
- **kind:** generator
- **generator:** the instance is whatever choice of approaches the learner's own session produces,
  so each session is new; what varies is the app and how many approaches arrive. Hold fixed: the
  instruction to keep trade-offs general and hold back the recommendation is given at the start;
  the reply is written before anything else is asked of the agent; the transcript is kept whole. If
  a session reaches more than one choice between approaches, the first one where the approaches
  differ in what they mean for the app is the instance. Difficulty is not controlled.
- **worked example:** the worked example from `a-choose-from-proposals`, shown before the session
  and never during it. If the learner asks for help at the choice point, the attempt is aided;
  give only the question: which thing you have told the agent about your app, if it were
  different, would change your pick?
- **doesn't show:** the learner built the situation themselves over the course of the session, so
  they already know which facts matter, and the facts with no bearing are whatever happened to come
  up rather than facts planted to mislead; that makes this easier than a Hard generated instance.
  Asking the agent to hold back its recommendation removes the pressure the criterion most wants
  resisted, so a pass here does not show the learner would choose well with a recommendation in
  front of them; `a-choose-from-proposals` at Medium or Hard does. Difficulty goes uncontrolled, and
  a learner has only a few such sessions a term, so this entry cannot carry review.
- **offer as:** the real decision in your real session, where the approach you pick is the one your
  app gets built with. Nothing to prepare except one sentence to your agent at the start. Less
  controlled than `a-choose-from-proposals`, and easier in one important way: you asked the agent
  not to lead with its own pick.

### `a-w-spec`

- **origin:** generated
- **serves:** `w-spec`
- **checks:** `w-spec`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-plan`

- **origin:** generated
- **serves:** `w-plan`
- **checks:** `w-plan`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-success-criteria`

- **origin:** generated
- **serves:** `w-success-criteria`
- **checks:** `w-success-criteria`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-constraint`

- **origin:** generated
- **serves:** `w-constraint`
- **checks:** `w-constraint`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-mvp`

- **origin:** generated
- **serves:** `w-mvp`
- **checks:** `w-mvp`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-yagni`

- **origin:** generated
- **serves:** `w-yagni`
- **checks:** `w-yagni`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-spike`

- **origin:** generated
- **serves:** `w-spike`
- **checks:** `w-spike`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-architecture`

- **origin:** generated
- **serves:** `w-architecture`
- **checks:** `w-architecture`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-tech-stack`

- **origin:** generated
- **serves:** `w-tech-stack`
- **checks:** `w-tech-stack`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
