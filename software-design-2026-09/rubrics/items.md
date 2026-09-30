# Rubrics: The words of software design

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-define-spec

- **type:** free
- **goal:** w-spec
- **move:** DEFINE
- **answer:** the written statement of what the app should be and do, and of what would count as
  it being done, settled with you before anything is built. It says what gets built and for whom,
  not how the building will be done, and it is what the finished app is held to.
- **credit:** full credit for saying it is the document that sets out what the app should be and
  do, agreed before the building starts. Full credit also for an answer that names what counts as
  done as part of it. Do not accept another name for it: "a specification", "a design doc", "the
  requirements document". Do not accept the steps the agent will follow or the order of the work,
  which is the plan. Half credit for "the document the agent writes at the start" with nothing
  about what is in it. No credit for "the code", "the prompt you gave it", or "the finished app's
  documentation".

### q-spec-vs-plan

- **type:** free
- **goal:** w-spec
- **move:** DISTINGUISH
- **answer:** the spec is about what gets built: what the app is for, what it should do, and what
  would count as done. The plan is about how it gets built: the work broken into pieces and put in
  an order, each piece small enough to check when it is finished. The plan follows from the spec
  and decides nothing about what the app is for.
- **credit:** full credit for the what against the how, in either wording: "the spec says what the
  app should be, the plan says how the agent will build it, step by step". Half credit for an
  answer that only gives the order ("the spec comes first, then the plan") with nothing about what
  each one is about. Do not accept incidental differences: which is longer, which is more formal,
  which one the agent writes (it writes both), or that one is for you and the other for the agent.

### q-spec-describes-finished-code

- **type:** free
- **goal:** w-spec
- **move:** CATCH
- **answer:** the spec comes before the code, not after it. It is what the app gets built from, so
  approving it is the moment you can still change what gets built, and skimming it gives that
  moment away. "It works when it's done" only means the app matches the spec; if the spec said the
  wrong thing, a working app is the wrong app, and nothing about it working tells you otherwise.
- **credit:** full credit for saying the spec is written before the build and is what the app is
  built from, so reading it is the chance to fix what gets built. Full credit also for the second
  half on its own: a working app only shows it matches the spec, not that the spec matched what
  they wanted. Half credit for "the order is backwards" with nothing about why reading it matters.
  Do not accept a different quibble as the error: that specs are good practice, that the agent
  makes mistakes when it writes code, that they should have tested the app, or that skimming is
  lazy.

### q-define-plan

- **type:** free
- **goal:** w-plan
- **move:** DEFINE
- **answer:** the document that says how the app will be built: the work broken into pieces, in an
  order, each one small enough that you can tell when it is done. It takes what the spec already
  settled and works out the route to it.
- **credit:** full credit for saying it sets out how the work gets done, as pieces or steps in an
  order. Full credit also for an answer that adds that each piece can be checked on its own. Do
  not accept another name for it on its own; "the implementation plan" with no more gets half
  credit. Do not accept what the app will do, its features, or what counts as done, which is the
  spec. Half credit for "the agent's to-do list" with nothing about it being the how or about the
  pieces being checkable. No credit for a schedule of dates or an estimate of how long it will
  take.

### q-plan-step-three-done

- **type:** mcq
- **goal:** w-plan
- **move:** INTERPRET
- **answer:** 4
- **credit:** the plan cuts the work into pieces that can each be finished and checked, and the
  agent is reporting where the work stands: the first three pieces are done and checked, and the
  last four have not been started. 1 and 2 read a part-built app as a finished one. 3 reads the
  steps as features: a step is a piece of the building, and one feature can take several steps
  while one step may touch no feature you would name.

### q-plan-first-then-decide

- **type:** free
- **goal:** w-plan
- **move:** CATCH
- **answer:** a plan says how the work will be done, so it cannot settle what the app should be.
  There is nothing for it to be a plan of until what gets built has been agreed, which is the
  spec's job, and reading back a list of building steps is a poor way to find out what the app is
  for or what would count as done.
- **credit:** full credit for saying the plan is about how rather than what, so what the app should
  be has to be settled first, in the spec, and the plan follows from that. Half credit for "the
  spec comes first" with no reason. Do not accept a different quibble as the error: that it will
  take longer, that plans change anyway, that the agent will make mistakes, or that they should
  have read the plan more carefully.

### q-define-success-criteria

- **type:** free
- **goal:** w-success-criteria
- **move:** DEFINE
- **answer:** the statements in the spec that settle what will count as the app being done and
  doing its job, written so that someone who never heard the idea could use the finished app and
  say of each criterion whether it was met. They are what "finished" gets judged against, rather than a
  list of the parts the app will have.
- **credit:** full credit for saying they are what counts as the app being done, or what has to be
  true of the finished app, settled in advance. Full credit also for an answer that leads with
  their being checkable by someone using the app. Do not accept just another name for them, such as
  "acceptance criteria". Do not accept the tests, or a list of the app's features. Half credit for
  "what the app has to do" with nothing about settling when it is done or about anyone being able
  to check.

### q-criteria-vs-tests

- **type:** free
- **goal:** w-success-criteria
- **move:** DISTINGUISH
- **answer:** success criteria are agreed with you in ordinary words before anything is built, and
  they say what has to be true of the finished app for it to be doing its job, so that anyone
  using it could settle them. Tests are code the agent writes and runs against what it has built,
  checking that the pieces behave the way the code expects. An app can pass every test and still
  fail its success criteria, because the tests only check what somebody thought to write down as
  code.
- **credit:** full credit for both sides: criteria are agreed up front, in words, about what the
  finished app must be true of, and tests are code run against the build. Full credit also for an
  answer that makes the point with passing tests not meaning the criteria are met. Half credit for
  "criteria are in English and tests are code" with nothing about what each is for. Do not accept
  that they are the same thing said twice, that criteria are just vaguer tests, or that tests come
  first.

### q-criteria-are-features

- **type:** free
- **goal:** w-success-criteria
- **move:** CATCH
- **answer:** those are the parts the app will have, a feature list, not statements about what the
  finished app has to be true of. All three could be built and the app could still fail to tell
  anybody whether they know what YAGNI stands for: the Check button could accept anything typed,
  or nothing at all. A criterion says what someone using the app would find: that a person who
  types the right five words is told they are right, and a person who types something else is told
  they are wrong.
- **credit:** full credit for naming them as features or parts rather than statements of what the
  finished app must do, or for showing that an app with all three could still miss what the app is
  for. Half credit for saying they do not say what counts as done, without saying they are
  features. Do not accept a different quibble as the error: that there should be more of them,
  that they are too short, that they say nothing about how the app looks, or that they do not
  mention React.

### q-define-constraint

- **type:** free
- **goal:** w-constraint
- **move:** DEFINE
- **answer:** a limit that comes from the situation the app has to live in rather than from
  anyone's choice about the design: who has to be able to use it, on what devices, by when, for
  how long, and with whom looking after it. It rules some designs out before any of them are
  compared, and no amount of cleverness in the design makes it go away.
- **credit:** full credit for a limit set from outside the design that the app has to fit inside
  and that no design choice can remove. Full credit also for an answer that gives the sense with an
  example, such as "it has to work on their phones, and that's not up to me". Half credit for "a
  limit" with nothing about where it comes from or that it is not yours to drop. Do not accept "a
  requirement" or "something the app has to do", which is the other thing. No credit for "a
  problem", "a bug", or "something the agent refuses to do".

### q-constraint-vs-requirement

- **type:** free
- **goal:** w-constraint
- **move:** DISTINGUISH
- **answer:** a requirement is something you are asking the app to do. You chose it, and you can
  drop it or put it off if it costs too much. A constraint is a limit the app has to fit inside
  that comes from the situation rather than from what you want: the six officers each have their
  own phone, the event is next Saturday, nobody will look after it after the term. Requirements
  can be traded away against each other; constraints have to be designed around.
- **credit:** full credit for both sides: a requirement is something asked of the app and can be
  given up, a constraint comes from outside, is not yours to give up, and rules designs out. Half
  credit for an answer that gets one side right and leaves the other vague. Do not accept
  "constraints are negative and requirements are positive" as the whole answer, or that
  constraints are only about time and money.

### q-constraint-rules-out

- **type:** mcq
- **goal:** w-constraint
- **move:** INTERPRET
- **answer:** 2
- **credit:** the no-installation constraint is what removes the two approaches, so it has a price
  you can now see, and relaxing it would bring them back. Whether to relax it is a separate
  decision that the agent's report does not make for you. 1 reads it as the agent arguing rather
  than as a limit that removes options. 3 overreaches: those approaches are fine for an app that
  may install something, just not for this one. 4 treats the constraint as a requirement, one
  more thing to trade against the benefits; a constraint rules out whatever does not fit inside
  it, and the agent is right to apply it that way.

### q-define-mvp

- **type:** free
- **goal:** w-mvp
- **move:** DEFINE
- **answer:** the smallest version of the app that is still worth putting in front of someone to
  use for real: it does the one thing the app is for, end to end, well enough that a real user
  gets the point of it, and everything else is left out for now.
- **credit:** full credit for the smallest or first version that is actually worth giving to
  someone to use, doing the thing the app is for. Do not accept the letters spelled out, or "a
  minimal product", which names it again. Half credit for "the smallest version" with nothing
  about it being worth using or doing what the app is for. No credit for "a demo", "a rough
  draft", "a prototype", or "the first half of the features".

### q-mvp-vs-prototype

- **type:** free
- **goal:** w-mvp
- **move:** DISTINGUISH
- **answer:** an MVP is a real version, meant to be used for real and kept, cut down to the least
  that is still worth using. A prototype is built to show or try something out, so a person can
  react to it or a question can be answered, and it is not meant to be used for real or kept: it
  can fake whatever it is not about.
- **credit:** full credit for the difference that matters: an MVP is for real use and stays, a
  prototype is to show or learn from and is thrown away or faked. Half credit for "an MVP is
  bigger" or "a prototype is rougher" with nothing about what each is for. Do not accept "a
  prototype is unfinished and an MVP is finished": an MVP is deliberately incomplete too.

### q-mvp-is-whatever-fits

- **type:** free
- **goal:** w-mvp
- **move:** CATCH
- **answer:** what is in the MVP is settled by what makes a version worth using, not by when the
  clock runs out. Stopping wherever the time ends can leave an app that does no part of its job
  all the way through, which is not a version anyone could use, and deciding it in advance is what
  lets you say what gets left out and what does not.
- **credit:** full credit for saying the MVP is decided by the smallest thing worth actually using
  for what the app is for, not by the time available, or for saying that stopping at an arbitrary
  point leaves something nobody could use. Half credit for "they should decide what's in it first"
  with no reason. Do not accept a different quibble as the error: that they should work faster,
  that the lab is too short, that the agent will run out of budget, or that they should commit
  their work.

### q-define-yagni

- **type:** free
- **goal:** w-yagni
- **move:** DEFINE
- **answer:** leave out anything the app does not need yet. Build what is needed for what it is
  for today, and do not add a feature because it might be wanted later: the guess about later is
  usually wrong, and every extra feature costs work now and has to be carried, understood and kept
  working afterwards whether anyone uses it or not.
- **credit:** full credit for the instruction: leave out what is not needed yet. A reason, that
  the guess about what will be wanted is usually wrong or that the extra costs more than the
  writing of it, is a good addition and not required. Do not accept the five words spelled out,
  which names it again. Do not accept "keep it simple", which is the other thing. Half credit for
  "leave things out" with nothing about their not being needed yet. No credit for "never add
  features", "write as little code as possible", or "do the easy parts first".

### q-yagni-cheaper-now

- **type:** free
- **goal:** w-yagni
- **move:** CATCH
- **answer:** "it would cost more to add later" is exactly the reasoning YAGNI is aimed at.
  Nobody needs the scoreboard now, and that it will be wanted later is a guess. The cost is not
  only the extra lines: a feature nobody asked for still has to be agreed, kept working and
  understood by whoever comes next, and it can break the parts that do matter. Here the brief says
  the app need not remember anything; if that is right, the feature serves nothing the app is for.
- **credit:** full credit for naming it as building a feature nobody needs yet on a guess about
  later, which is what YAGNI says to leave out. Full credit also for an answer resting on the cost
  being more than the few lines, or on the brief saying the app need not remember anything. Full
  credit also for arguing that saying yes was right but the reason was wrong: the app is not
  really useful without the scoreboard, so it is needed now, not on a guess about later. Half
  credit for "it wasn't asked for" with nothing about the cheaper-now reasoning being the mistake.
  Do not accept a different quibble as the error: that the agent should not make suggestions, that
  there was no time in the lab, that it would cost too many tokens, or that a scoreboard is a bad
  feature in itself.

### q-define-spike

- **type:** free
- **goal:** w-spike
- **move:** DEFINE
- **answer:** a short, deliberately rough piece of work done only to find something out that
  nobody yet knows: whether this can be done at all, whether this library works, how slow it is.
  What you keep at the end is the answer, not the code, which is thrown away, and the real work is
  then designed knowing it.
- **credit:** full credit for a quick try whose point is to answer a question, with the code not
  kept. Half credit for "a quick experiment" with nothing about the answer being the output or the
  code being thrown away. Do not accept "the first version of the app", "a small feature built
  early", or "a prototype", which is a different thing. No credit for a spike in usage or traffic,
  or for a sudden burst of work.

### q-spike-vs-prototype

- **type:** free
- **goal:** w-spike
- **move:** DISTINGUISH
- **answer:** both are work you do not keep, but they answer to different people. A spike is done
  to settle a question the builder has, such as whether something is possible or how hard it would
  be, and what comes out of it is the answer. A prototype is built to show what the app would be
  like, usually to a person, so they can react to it, and what comes out is something to look at
  or try.
- **credit:** full credit for the difference in what each produces and who it is for: a spike
  answers a question about whether or how something can be built, a prototype shows what the app
  would be like so someone can respond. Half credit for one side stated correctly and the other
  missing, such as a spike answering a question with nothing about what a prototype is for. Half
  credit for "a spike is shorter" or "a spike is rougher" alone, since both are throwaway. Do not accept "a spike is code you keep and a
  prototype is not", or that a prototype is simply a bigger spike.

### q-spike-twenty-minutes

- **type:** free
- **goal:** w-spike
- **move:** INTERPRET
- **answer:** there is something the design depends on that it cannot answer by thinking, so it
  will write a quick, rough piece of code purely to find out, and what it brings back is the
  answer rather than any code that stays in the app. The plan waits on that answer, because what
  goes in the plan depends on which way the answer falls.
- **credit:** full credit needs both halves: there is an open question it has to try something to
  answer, and the output is the answer, not code that is kept. Half credit for either half alone.
  No credit for reading it as the agent starting to build the file-reading feature, as the agent
  asking permission to spend twenty minutes of budget, or as a sign the agent cannot do the job.

### q-define-architecture

- **type:** free
- **goal:** w-architecture
- **move:** DEFINE
- **answer:** how the app is divided into its main parts and how those parts work together: what
  pieces there are, which one is responsible for what, and how they talk to each other. It is the
  shape of the app, not what it is made of.
- **credit:** full credit for the main parts of the app and how they fit together, or which part
  is responsible for what. Half credit for "how the app is built inside" with nothing about parts
  or how they relate. Do not accept a list of technologies (React, a database, a server), which is
  what the app is made of rather than how it is arranged. No credit for "the design document",
  "the folder layout", or "the diagram".

### q-architecture-vs-stack

- **type:** free
- **goal:** w-architecture
- **move:** DISTINGUISH
- **answer:** the architecture is the shape: which parts there are, what each one is responsible
  for, and how they talk to each other. The tech stack is what those parts are made of: the
  particular languages, frameworks, libraries and services chosen. The same architecture can be
  built on different stacks, and the same stack can be put together into quite different
  architectures.
- **credit:** full credit for the parts-and-how-they-fit against the technologies-used split. Full
  credit also for an answer that makes the point by varying one with the other held fixed. Half
  credit for an answer that gets one side right and leaves the other vague. Do not accept
  "architecture is the big picture and the stack is the detail" on its own, or that the
  architecture is the diagram and the stack is the list.

### q-architecture-shared-list

- **type:** mcq
- **goal:** w-architecture
- **move:** INTERPRET
- **answer:** 1
- **credit:** the agent is saying the app would get a new part and a new conversation between
  parts, which is a change to how the app is put together rather than to a value inside it. 2
  confuses the arrangement of the parts with what they are written in. 3 is a different
  arrangement that the agent did not describe. 4 is exactly what "not a setting" rules out.

### q-define-tech-stack

- **type:** free
- **goal:** w-tech-stack
- **move:** DEFINE
- **answer:** the set of technologies an app is actually built out of, taken together: the
  languages, frameworks, libraries, databases and services its parts are made of. Two apps that
  behave the same and look the same can be made of quite different things.
- **credit:** full credit for the technologies, tools, languages or frameworks the app is built
  with, as a set. Do not accept "the stack", which names it again. Do not accept how the parts of
  the app fit together or which part does what, which is the architecture. No credit for "the
  files in the project", "the computer it runs on", or "the versions of things installed".

### q-stack-says-who-does-what

- **type:** free
- **goal:** w-tech-stack
- **move:** CATCH
- **answer:** the stack says what the app is made of, not how it is arranged. Knowing that React,
  Vite and SQLite are in it tells you nothing about which part holds the list, which part decides
  what happens when someone clicks, or how those parts talk to each other. Two apps built on
  exactly that stack can be put together quite differently, and it is the architecture, not the
  stack, that answers what they asked.
- **credit:** full credit for saying a list of technologies says what the app is made of rather
  than how it is organized or which part is responsible for what, and that this is the
  architecture. Half credit for "that doesn't tell you that" with nothing about the difference
  between what it is made of and how it is arranged. Do not accept a different quibble as the
  error: that the list is incomplete, that they should ask the agent for a diagram, that they do
  not need to care about the stack, or that Vite is not really part of the stack.

### q-same-stack-two-approaches

- **type:** free
- **goal:** w-tech-stack
- **move:** INTERPRET
- **answer:** both approaches are built out of the same technologies, so nothing in this choice is
  a choice about languages, frameworks or databases. What separates them is where the list lives,
  which decides whether anyone but the person who made it can see it. A reason like "I prefer that
  technology" has nothing to choose between here; the reason has to come from who needs to see the
  list.
- **credit:** full credit needs both: the technologies are the same on either side, so the choice
  is not a technology choice, and the real difference is where the data lives, which is about what
  the app does for people. Half credit for either half alone. No credit for reading it as the
  second approach being the more advanced or more professional one, as the stack not mattering in
  general, or as the agent recommending one of them.

### q-criteria-for-practice-signup

- **type:** free
- **goal:** c-write-success-criteria
- **answer:** what it is for: so that the officer can see in one place who is coming to Thursday
  practice, instead of counting replies scattered across chat threads and getting it wrong. Two
  criteria a stranger could settle, for example: someone who opens the page can say whether they
  are coming to this Thursday's practice, and the page then shows their name under the right one
  of the two answers; and the officer can see, on one screen, everyone who has answered and which
  way, without going to the group chat at all.
- **credit:** full credit needs both halves. First, a purpose sentence that says what the app is
  for rather than what it has in it: "a page with yes and no buttons and a list" is a feature
  list, not a purpose. Second, two criteria a person with no knowledge of the club could settle by
  using the finished app, each about something the app shows or lets someone do. Half credit if
  one half is right and the other is not: a good purpose sentence with criteria that are feature
  names ("it has a yes button") or that nobody could settle ("the officer finds it easy"), or two
  good criteria under a purpose that only lists features. No credit for an answer that restates
  the officer's request and adds nothing, or that gives criteria about how the app is built.

### q-rota-meets-and-misses

- **type:** free
- **goal:** c-write-success-criteria
- **answer:** a builder could ship a rota that puts the same housemate's name on nearly every
  chore, or one whose turns never move on, and all three criteria are still met: every chore is
  listed, each shows a name, and anyone can tick one off. Nothing in the three says the work is
  spread out or lets anyone see how it has been spread. A criterion that would catch it: over any
  four weeks of the rota, each housemate's name appears on roughly the same number of chores. Or:
  any housemate can see, for the last month, how many chores each person was given and how many
  they ticked off.
- **credit:** full credit needs both: an app that plausibly meets all three criteria and still
  fails the stated purpose, and one further criterion that a person using the finished app could
  settle and that would rule that app out. Half credit for one of the two. Half credit also for an
  app no honest builder would ship, such as one that deliberately hides names or crashes on use,
  since the point is what a hurried builder could do in good faith. No credit for an answer that
  only says the three criteria are vague, or whose new criterion nobody could settle ("the rota
  should feel fair to everyone").

### q-choose-signup-approach

- **type:** free
- **goal:** c-choose-approach
- **answer:** the shared list, approach B. It gives up the simplicity of approach A: there is a
  server to set up and somebody has to keep it running, and it will not work without internet. The
  reason is in this situation: six officers, each on a different phone, all have to see the same
  sign-ups, and a list that lives in one person's browser cannot be seen from the other five. The
  founding year and the club colors have no bearing on this choice.
- **credit:** full credit needs all three: the pick, what it gives up, and a reason drawn from a
  fact in this situation that bears on the choice. The six officers on separate phones needing the
  same list favors B; the app outliving this committee, with no server to hand over, favors A. For
  B, what it gives up is the server to set up, keep running and pass on, or working without
  internet; for A, it is the officers seeing the same list. The reason is what is being judged
  rather than the pick: give full credit for picking approach A if it comes with what it gives up
  and a reason from this situation that genuinely bears on it. Half credit for a pick with a good reason but nothing given
  up, or for a pick with what it gives up and a reason that would hold for any app, such as "it
  scales better", "it's simpler", or "the agent recommended it". No credit for a reason resting on
  the founding year or the colors, or for "whichever one the agent recommends".

