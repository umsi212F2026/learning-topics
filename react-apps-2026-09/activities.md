# Activities — react apps

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
| `c-describe-app-bug` | tell the agent what is going wrong in a running app | Given a problem in a running app, writes the request they would send the agent. It passes when someone who never saw the problem could make it happen again from that request alone, and could tell when it had been fixed. Any guess at the cause is labeled as a guess, separate from what they saw. |
| `c-run-browser-check` | carry out a check in the browser that the agent asks for, and bring back what it showed | Given the agent's request to inspect the running app or run a snippet in the browser's developer tools, runs it only in their own app and reports back what it produced: copied text where it can be copied, a screenshot where it can't, complete and unedited, errors included. It passes when the agent could act on the result without asking again. |

## Coverage

<!--
  Derivation convention, recorded so it does not get re-flagged: an activity carrying `checks`
  is a check, so it appears only in the `checks` cell and never in `study`. Activities whose
  `serves` is `all` sit on the `o-orientation` row, which is the row that carries them; they are
  not repeated on every other goal's row.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-tour-starter-app-words`, `a-read-why-frameworks-exist` | `a-dry-run-both-asks` | |
| `c-describe-app-bug` | `a-read-tatham-bug-reports`, `a-sort-bug-requests`, `a-narrated-planted-bug` | `a-describe-planted-bug`, `a-describe-own-app-bug` | |
| `c-run-browser-check` | `a-read-devtools-on-starter`, `a-judge-check-reports` | `a-run-tutor-agent-check`, `a-report-own-agent-check` | |

---

## Activities

### `a-tour-starter-app-words`

- **serves:** `all`
- **supports:** orient
- **artifact:** no external source. The learner's own Vite + React starter project, the one every
  student got running on their laptop before this topic, used through a scratch copy so that the
  original stays unmodified. In the current create-vite React template (vitejs/vite,
  `packages/create-vite/template-react`, as it stood on 2026-09-17) the page shows a "Get started"
  heading, a line reading "Edit src/App.jsx and save to test HMR", and a "Count is 0" button; the
  project's own code is a single component, `App`; and `package.json` has `dev`, `build`, `lint`
  and `preview` scripts, with `react` and `react-dom` as its dependencies. A project made from an
  older template shows different headings and "count is 0" in lower case, but the same button and
  the same HMR line. 40 to 50 minutes.
- **learner does:** keeps a two-column list with one row per word in this topic (component, state,
  render, event handler, dev server, dependency, build, hot reload, browser console, hard reload,
  routing, headless browser). Whenever one of them turns up, fills in its row: what on their screen
  it was. Says each row out loud before the tutor comments; "no idea yet" is an acceptable first
  entry. Does every browser step with their own hands, on the copy, and types only the terminal
  commands the tutor gives them, exactly as given:
  1. In a terminal window in the copy's folder, runs `npm run dev`, reads the address it prints,
     and opens that address in the browser. Keeps the terminal window visible.
  2. Clicks Count several times.
  3. Reloads the page and watches the count. Then does a hard reload (in Chrome, Edge or Firefox,
     Cmd+Shift+R on a Mac or Ctrl+Shift+R on Windows) and watches again.
  4. Clicks Count up to 5, then asks the tutor to change the words "Get started" to anything they
     choose and save, and watches the page without touching it. Says whether the count survived.
  5. Opens the browser's developer tools on the app's tab, finds the Console, and says what is in
     it (it may be empty). Compares it with what the terminal window shows.
  6. Adds `/about` to the end of the address, presses Enter, and says what changed on screen and
     what didn't.
  7. Stops the dev server with Ctrl+C in its terminal, reloads the tab, and says what happened.
     Starts it again.
  8. Runs `npm run build`, then `npm run preview` in the same folder, opens the address the preview
     prints, asks the tutor for another wording change, and says whether the preview page changed
     by itself. Then looks at the dev server's tab again.
  9. Opens the copy's folder in their file browser, finds `node_modules`, and asks the tutor how
     many packages are in it and where they came from.
  10. Watches the tutor either open the copy with a headless browser and show what it saw, or say
      what one would do.
  Rows for routing and headless browser will point at something that did not happen, or that the
  tutor did rather than the learner; that is expected. No code is read at any step.
- **tutor role:** explainer
- **tutor does:** beforehand, asks where the starter project is, and copies the whole folder
  (including `node_modules`) to a scratch directory outside any repository the learner commits to.
  The original is never edited. If the original is still running on 5173, Vite gives the copy the
  next free port and prints it. During the tour, asks for the learner's row before commenting and
  replies with a near-miss question rather than a verdict ("you wrote that the reload re-rendered
  it; did clicking Count re-render it too?"). Ties each step to its words: steps 1 and 7 to dev
  server, and to the terminal and the page being two different places; steps 2 and 3 to event
  handler, state and render, and to the count being gone after a reload because nothing kept it;
  the hard reload to a reload that doesn't trust what the browser kept from last time, which looks
  the same here because nothing was stale; step 4 to hot reload and the HMR line on the page
  (whether the count survived is for the learner to observe, not for the tutor to promise); step 5
  to browser console as against the terminal; step 6 to routing: the starter has none, and Vite's
  dev server sends the same page for any path by default, so every address shows the same screen,
  where an app with routing would show a different one; step 8 to build: the preview serves the
  built `dist` folder, usually at port 4173, and doesn't change by itself; step 9 to dependency:
  `npm install` fetched these, starting from `react` and `react-dom` and the tools. Handles
  component without a step: the starter's own code is one component, `App`, so asks the learner
  which parts of the page they would expect to become separate components in an app with several
  screens. At step 10, if it has a headless browser, opens the copy's address and shows the
  learner the screenshot it took; if not, says what it would do, and why that means an agent can
  sometimes check its own work without asking. Makes the wording changes without showing the file
  or the change, and says only what changed on screen. At the end, has the learner stop the
  servers they started.
- **done when:** every one of the twelve rows points at something the learner saw or did (for
  routing and headless browser, at what did not happen or what the tutor did), and the learner can
  say what each row points at with the list in front of them. This entry carries no `checks`: the
  readiness indication `o-orientation` is ruled on is taken in `a-dry-run-both-asks`, which
  follows.
- **offer as:** hands-on, on the app you already have. Every word lands on something you did
  yourself, in your own browser and terminal, and there is nothing to read. The longer of the two
  orientation routes, 40 to 50 minutes, and the only one that covers all twelve words;
  `a-read-why-frameworks-exist` is a short page of prose that names four and leaves eight for the
  tutor to raise. Needs a live session. Either one is followed by `a-dry-run-both-asks`.

### `a-read-why-frameworks-exist`

- **serves:** `all`
- **supports:** orient
- **artifact:** MDN Web Docs, "Introduction to client-side frameworks",
  https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Frameworks_libraries/Introduction
  (free, no account). Two parts of it only: "Why do frameworks exist?" (about 320 words, one short
  code block) and "Other things frameworks give us" with its subsections Tooling,
  Compartmentalization and Routing (about 550 words, no code). About 900 words, 6 to 8 minutes of
  reading inside a 25 to 30 minute session. The first part introduces state ("In software
  development, this underlying data is known as state") and the problem of updating the screen to
  match it, which is what render names. Compartmentalization introduces components. Routing
  explains the URL in the address bar, single page apps, and client-side routing. Tooling is about
  testing and linting, and names none of this topic's tooling words. The page's running example is
  a to-do list; it mentions React but never Vite. The parts skipped ("The verbosity of DOM changes"
  and "Another way to build UIs") are mostly code, and the rest of the page is about choosing a
  framework.
- **learner does:** reads the two parts with their own starter app running in a browser window
  beside the page. Skips the code blocks, and says so if one seems to carry something the prose
  doesn't. Stops at each of these as the page reaches it: state; updating the UI to match the
  state; components; the URL in the address bar; single page app; client-side routing. At each,
  says what on the running starter app it corresponds to, or says they can't find anything, before
  reading on. After the read, asks about the eight words the two parts never mention: event
  handler, dev server, dependency, build, hot reload, browser console, hard reload, headless
  browser. For each, hears it explained against the starter app and says it back in one sentence of
  their own.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the six stopping points and when asked.
  At each stopping point, takes the learner's answer first and replies with a near-miss question
  rather than a verdict. Useful anchors on the starter: the count is state, and clicking Count
  updates the screen to match it; the starter has no routing, so typing a different path after its
  address shows the same page. Explains the eight missing words in the order someone using an app
  meets them: dev server and dependency (what `npm run dev` leaves running, what `npm install`
  fetched), event handler (what the Count click is connected to), hot reload (the "save to test
  HMR" line on the starter page), hard reload (a reload that doesn't trust what the browser kept),
  browser console (where the page reports what went wrong, out of sight, as against the terminal),
  build (what the project becomes to leave the laptop), headless browser (a browser the agent
  drives itself, to look at the app without asking). Where a word takes one action to show, has the
  learner do it on the starter now: click Count, open the console. Makes no change to the starter
  project, and doesn't explain the code blocks.
- **done when:** each of the six stopping points has an answer tied to the starter app, or an
  honest "can't find it" that the tutor then resolved, and each of the eight missing words has a
  one-sentence restatement from the learner. This entry carries no `checks`: the readiness
  indication is taken in `a-dry-run-both-asks`, which follows.
- **offer as:** the prose route: a short, free page that explains why a React app is built out of
  components and state, and what routing is for, before you touch anything. Shorter than
  `a-tour-starter-app-words` (25 to 30 minutes against 40 to 50) and needs no copy of your project,
  but the page names only four of the twelve words, and the other eight come from the tutor rather
  than from anything you did. Take it if you'd rather read the why first. Either this or the tour
  is followed by `a-dry-run-both-asks`.

### `a-dry-run-both-asks`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. The learner's running starter app (the original, or the copy
  from `a-tour-starter-app-words` if it is still running), with whatever they oriented with still in
  front of them: their twelve-row list from the tour, or the MDN page and their answers from the
  read. 10 minutes.
- **learner does:** two rehearsals, neither of them judged. First, the tutor describes a made-up
  problem with the starter app in one sentence, and the learner says roughly what they would write
  to their agent about it, and which of the topic's words it touches. Second, the tutor sends a
  request worded the way a coding agent asks for a browser check, and the learner does it for real,
  on the starter app's tab, and says what they would send back. Then answers the question the tutor
  puts: with your list (or the page) beside you, could you now attempt telling your agent what is
  going wrong in an app it built, and carrying out a check in the browser that it asks you for?
- **tutor role:** explainer
- **tutor does:** sets both rehearsals from the generator below. Grades neither answer. If an
  answer shows a misunderstanding (a made-up cause stated as though it had been seen, a check run
  in a tab that isn't the app), explains it once and moves on. Then puts the readiness question as
  written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's own indication, not on how good either rehearsal
  was and not on whether the tutor thinks they are ready. A yes to one half of the question and a
  hedge on the other is `criterion: unclear`: explain the hedged half again and put the question
  again.
- **kind:** generator
- **generator:** vary the made-up problem and the request; hold everything else fixed. The problem
  is one sentence about the starter app, in a user's words, drawn from any category in
  `a-describe-planted-bug`'s generator ("suppose that after you click Count three times and reload,
  the page goes white instead of showing the count"). The request is one Easy request from
  `a-run-tutor-agent-check`'s generator, aimed at the starter app ("Could you open the console on
  the app and tell me whether anything in it is red?"). Fixed: two rehearsals in that order, neither
  graded, then the readiness question word for word. Difficulty doesn't vary: this settles an
  indication, not a capability.
- **worked example:** if the learner freezes on the first rehearsal, the tutor answers a different
  made-up problem out loud first, in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about whether the learner can do either capability: both rehearsals are helped and
  ungraded, the problem is imagined rather than seen in a running app, and the request is the
  easiest kind. It also shows nothing about any of the twelve words, which have their own supply.
- **offer as:** the short step that closes orientation, after either `a-tour-starter-app-words` or
  `a-read-why-frameworks-exist`. Not an alternative to them: they give you the shape, and this is
  where you say whether you have it. Ten minutes, on the app you already have.

### `a-read-tatham-bug-reports`

- **serves:** `c-describe-app-bug`
- **supports:** orient, deepen
- **artifact:** Simon Tatham, "How to Report Bugs Effectively",
  https://www.chiark.greenend.org.uk/~sgtatham/bugs.html (free, no account, one page, about 3,500
  words; 20 minutes to read, 35 to 40 for the activity). Written for anyone who uses software, with
  no programming assumed; its examples are older desktop programs, not web apps. Sections:
  Introduction; "It doesn't work."; "Show me."; "Show me how to show myself."; "Works for me. So
  what goes wrong?"; "So then I tried . . ."; "I think the tachyon modulation must be wrongly
  polarised."; "That's funny, it did it a moment ago."; "So I loaded the disk on to my Windows . .
  ."; Summary. Each part of this goal's criterion has a passage: making it fail for themselves ("you
  want the programmer to run their own copy of the program, do the same things to it, and make it
  fail in the same way"), saying what you saw and what you expected (the Summary: "State what you
  saw, and also state what you expected to see"), and symptoms before diagnosis ("The diagnosis is
  an optional extra, and not an alternative to giving the symptoms").
- **learner does:** reads it in order. At the end of each section whose heading quotes a bad report
  ("It doesn't work.", "So then I tried . . .", "I think the tachyon modulation must be wrongly
  polarised.", "That's funny, it did it a moment ago."), writes one sentence someone might send an
  agent in that style about a web app on their laptop, and one sentence saying what the section
  says they should have written instead. After the Summary, the tutor describes a problem in a
  user's words; the learner asks the tutor whatever they need to know about what happened, then
  writes the full request they would send an agent, and marks each of its sentences as seen,
  expected, or guess.
- **tutor role:** socratic questioner
- **tutor does:** stays out of the reading until a sentence is written. Takes each pair of
  sentences and asks a question that separates the rule from the example ("your version names the
  page; would the agent know what to click first?"). When asked, translates the essay's desktop
  examples into the browser: an error message with numbers in it is the red text in the browser
  console, and "run their own copy" is the agent opening the same address. For the closing request,
  picks a problem from any Medium or Hard category in `a-describe-planted-bug`'s generator, fixes
  the exact steps in its own notes first, gives only a one-sentence complaint, and answers the
  learner's questions the way a user who saw it would: truthfully, only what was asked, and without
  volunteering the steps. Then reads the finished request back literally, as someone who never saw
  the problem, pointing at each place it would have had to guess.
- **done when:** the learner has written the closing request and can say, with the essay beside
  them, which of its sentences a stranger would follow, which say what should have happened, and
  which are guesses. No `checks`: the problem was described to them in conversation rather than
  seen in a running app, and the tutor answered questions about it.
- **offer as:** the reasons first, in prose, from a well-known essay that assumes no programming.
  The longest read on this goal and the only candidate that explains why each part of a good
  request is there. Its examples are old desktop programs, so the translation to a web app happens
  in conversation with the tutor. Pick `a-sort-bug-requests` for examples before reasons, or
  `a-narrated-planted-bug` to see it done on a live app.

### `a-sort-bug-requests`

- **serves:** `c-describe-app-bug`
- **supports:** deepen
- **artifact:** `tasks/sort-bug-requests.md`, written for this topic: a short description of a small
  Tasks app running at localhost, eight requests that different people sent their agent about it,
  and a key for the tutor. Four requests pass and four are near misses. Between them they cover a
  task gone after a reload, a task page that works when clicked through to but not when its address
  is pasted, a saved change that doesn't appear, a white page whose only explanation is in the
  console, and a problem visible on one screen. 20 to 25 minutes. No app or browser needed.
- **learner does:** reads the app description, then answers the file's two questions for each of
  the eight requests: could someone who never saw the problem make it happen and tell when it's
  fixed from this alone (and if not, the one thing that stops them), and is any guess kept apart and
  labeled as a guess. Then states, in one or two sentences, the rule they sorted by. Then rewrites
  two of the requests they marked as failing so that they pass, adding only what the writer could
  have seen.
- **tutor role:** critic
- **tutor does:** shows the learner everything above the key and nothing in it. Takes all eight
  answers and the rule before commenting on any. On each answer that disagrees with the key, asks
  what the learner would do to follow that request exactly as written, rather than stating the
  answer. `r3` and `r7`, and `r2` and `r5`, are pairs built to be compared: if one of a pair was
  misjudged, puts the two side by side. Reads the two rewrites as a stranger would and says where
  each still leaves them guessing.
- **done when:** the learner's stated rule covers where to start, the steps, what happened, what
  should have happened, how to tell it's fixed, and a guess kept apart; and both rewrites would
  pass. No `checks`: judging and repairing someone else's request is not writing one about a
  problem you saw in a running app.
- **offer as:** examples before reasons, and the fastest of the three: 20 to 25 minutes, nothing to
  read beyond the file, no app to run. Every request is about the same small app, so the only thing
  that varies is the difference between a request that works and one that almost does. It covers
  the problems this topic's words explain (a reload, a pasted address, a change that doesn't show,
  a white page with the reason only in the console). Pick `a-read-tatham-bug-reports` if you'd
  rather have the reasons first.

### `a-narrated-planted-bug`

- **serves:** `c-describe-app-bug`
- **supports:** orient, deepen
- **artifact:** no external source. A scratch copy of the learner's own Vite + React starter project
  with one problem planted in it by the tutor, from the `reload-forgets` or `pasted-address`
  category of `a-describe-planted-bug`'s generator, running on the learner's laptop. 20 to 25
  minutes.
- **learner does:** drives the browser while the tutor writes. Before each action, says what they
  are about to do and what they expect to see; after it, says what they actually see. Interrupts
  whenever the tutor writes into the request something they didn't see. When the request is
  finished, marks each sentence as seen, expected or guess, and writes down a prediction: could
  someone who never saw the app make the problem happen from this request alone? Never opens a
  project file.
- **tutor role:** explainer
- **tutor does:** sets up the copy and the plant as `a-describe-planted-bug` describes, out of the
  learner's sight, and gives them that instance's description and complaint. Then composes the
  request out loud from what the learner reports, saying what it is weighing at each sentence, and
  makes two false starts on purpose, visibly, then corrects them. First it writes the cause as
  though it had been seen ("the app isn't saving the list") and rewrites it as a labeled guess. Then
  it writes the steps starting from wherever the learner happens to be, asks "what would a stranger
  have on screen at step one?", and rewrites them from a freshly opened page. Adds the "fixed when"
  line last and says why it comes last. After the learner's written prediction, says which sentence
  in the first drafts would have sent a stranger wrong. Labels the attempt
  `a-narrated-planted-bug/<category>`, and serves a different category in the learner's next
  attempt at `a-describe-planted-bug`. Stops the copy's dev server at the end.
- **done when:** the learner can name, in order and with the finished request on screen, the parts
  of the request: where to start, the steps, what happened, what should have happened, how to tell
  it's fixed, and the guess set apart. No `checks`: the tutor wrote the request.
- **offer as:** watch it done on a live, broken copy of your own starter app, with the false starts
  left in. The only candidate that shows the weighing a finished request hides, and the only study
  route where you use a running app before being checked on one. Needs a live session and a
  scratch copy of your starter project. Pick `a-sort-bug-requests` for a faster route with no app.

### `a-describe-planted-bug`

- **serves:** `c-describe-app-bug`
- **supports:** attempt
- **checks:** `c-describe-app-bug`
- **artifact:** no external source. A scratch copy of the learner's own Vite + React starter project
  with one problem planted in it, built per the generator below and running on the learner's
  laptop. 20 to 25 minutes.
- **learner does:** is given two things: a one or two sentence description of what the app is
  supposed to do, and a one-sentence complaint in a user's words that doesn't give the steps. Uses
  the app in the browser as much as they like (clicking, reloading, opening new tabs, pasting
  addresses, opening the browser console) until they can make the problem happen. Opens no project
  file. Then writes, alone, the request they would send an agent about it, and hands it to the
  tutor rather than sending it anywhere.
- **tutor role:** none
- **tutor does:** before the learner starts: asks where the starter project is, copies it (including
  `node_modules`) to a scratch directory outside any repository the learner commits to, plants one
  problem per the generator, and starts the copy's dev server on a free port. Plants it without
  narrating the change and without the change showing on the learner's screen; if the tutor's
  edits display on that screen, does it before the learner sits down, or asks them to look away. A
  learner who saw the change has been handed the cause: record that attempt `unaided: no`. If it
  has a headless browser, confirms the problem happens by following the ground-truth steps itself.
  Writes the ground truth into the record before the learner starts: the category, what was
  planted in plain words, the exact steps from a freshly opened page that make it happen, and what
  the app does once it's fixed. Gives the learner the description and the complaint, then waits,
  helping only if asked and writing down any help word for word. Sends the adjudicator the ground
  truth, the description and complaint as given, every piece of help, and the request verbatim.
  After the ruling, tells the learner what a stranger would have been stuck on, if anything. Stops
  the copy's dev server. Labels the attempt `a-describe-planted-bug/<category>`. If the learner
  can't make the problem happen within 10 minutes and the tutor had no headless browser to confirm
  the plant, suspects the instance before the learner: checks the plant, and if it was faulty,
  records nothing against the goal and serves a fresh instance.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: one problem per copy; it happens every time its steps
  are followed from a freshly opened page, never only sometimes; it can be made to happen and seen
  from the browser alone (the page, the address bar, reloading, a new tab, the console), with no
  project file opened; no new dependency is installed; the learner gets the description and the
  complaint and nothing else; the ground truth is in the record before the learner starts. The
  complaint never names the cause and never gives away a step (no "reload", "address", "link
  pasted" or "console").
  What varies: the category, where on the page it shows, and the wording of the description and
  complaint. Categories, each with one way to plant it:
  - `wrong-amount` (Easy): Count goes up by 2 per click. Complaint: "the counter seems off".
  - `does-nothing` (Easy): a new button, described as doing something visible, whose click is
    connected to nothing. Complaint: "the new button is broken".
  - `one-step-behind` (Medium): a line under Count reading "You have clicked N times" that always
    shows the number from the click before. Complaint: "the click message is wrong".
  - `reload-forgets` (Medium): a small list the user can add items to, kept only in the component's
    state, with the description saying the list is kept. Items are gone after a reload. Complaint:
    "the things I add keep disappearing".
  - `pasted-address` (Medium): a short list where clicking an item changes the address to
    `/items/<n>` with `history.pushState` and shows that item's page, and the item page takes its
    item from the click rather than from the address. Opening that address in a new tab, or
    reloading on it, shows the page without its item. Vite's dev server serves the app for any path,
    so the page itself loads; it's the item that is missing. Complaint: "links to items don't work
    when I send them to someone".
  - `change-not-showing` (Hard): once the learner has the page open, the tutor, speaking as their
    agent, announces that it changed a piece of visible text and saved, but the learner's tab
    doesn't get it. Plant it one of two ways: a second copy on another port, which the tutor edits
    while the learner's tab shows the first; or stop the copy's dev server just before announcing
    the change, so the old text stays until a reload fails. No complaint: the announcement is the
    setup.
  - `blank-screen` (Hard): a Reset button sets a value to something the page can't display, so an
    error is thrown while the page is being drawn and the page goes white, with the explanation only
    in the console. Confirm the page really goes blank. If Vite's red error overlay appears
    instead, the explanation is on screen and this is a different, easier instance: change the
    plant. Complaint: "sometimes the app just goes white".
  Difficulty: Easy is visible on the first screen after one action, with no reload, new tab or
  console involved. Medium needs two or more actions, a reload, or a second tab. Hard is
  `change-not-showing` or `blank-screen`, where the screen alone doesn't show what went wrong. An
  attempt meant to count runs at Medium or Hard; Easy is for the worked example and for a retry
  with help after a miss. Across attempts and review visits, serve a category the learner hasn't
  had, reading the labels `served.mjs` returns, until `reload-forgets`, `pasted-address`,
  `change-not-showing` and `blank-screen` have each come up once.
- **worked example:** work one Easy instance live: make the problem happen twice from a freshly
  opened page, saying what is on screen at each step, then write the request in front of the learner
  with its parts in order (the address, the steps, what happened, what should have happened, how to
  tell it's fixed, any guess set apart and labeled). At the first level of help on a real attempt,
  give only the question "what would someone need on screen before your first step?" and let the
  learner do the rest.
- **doesn't show:** the learner is told that a problem exists and what the app is for, so a pass
  doesn't show they would notice one, or know what should have happened, in an app nobody described
  to them. The copy is a tiny app they already know and every problem is repeatable by design, so
  describing something that happens only sometimes is never examined. The request is read by a
  judge against the ground truth rather than sent to an agent, so a pass doesn't show an agent would
  go on to fix the right thing. A pass in one category is thin evidence about the others: a
  `blank-screen` pass shows nothing about remembering to mention a pasted address. Easy instances
  are kept out of counting attempts because a problem visible on one screen after one click
  involves none of the reload, new-tab, saved-change or console cases this topic's words are about.
- **offer as:** a problem planted in a copy of the starter app you already have, where the tutor
  picks the kind of problem, so the ones this topic is about (gone after a reload, a pasted address
  that fails, a change that never shows up, a white page) actually come up. Available now, before
  your own app exists. Needs a live session and 20 to 25 minutes. `a-describe-own-app-bug` is the
  same capability on a real problem in your own app.

### `a-describe-own-app-bug`

- **serves:** `c-describe-app-bug`
- **supports:** attempt
- **checks:** `c-describe-app-bug`
- **artifact:** no external source. The learner's own app, the one their agent builds after this
  topic or any later one, running on their laptop, and a real problem in it that the learner
  noticed. 10 to 15 minutes, at whatever moment the app misbehaves.
- **learner does:** when the app does something it shouldn't, and before telling their agent
  anything about it, writes alone, in a separate note, the request they will send. Sends it to the
  agent word for word, then straight away sends the fixed follow-up message given in the generator
  below. Keeps the note unchanged, and keeps the agent's reply to the follow-up. Brings both to the
  tutor.
- **tutor role:** none
- **tutor does:** before the learner's first run, gives them the fixed follow-up message to keep
  somewhere they can copy it from. Afterwards, reads the note and the reply. Checks that the note
  was written before the agent had heard about the problem; if the agent raised it first, or the
  learner had already described it to the agent in conversation, there is no instance. Sends the
  adjudicator the request as sent, the follow-up, the agent's reply to it, and, kept separate and
  labeled as given afterwards, the learner's answer to "what did you see that made you write
  this?". After the ruling, tells the learner what the agent had to guess, if anything.
- **done when:** criterion met with no help. The request is judged as written and sent, not a later
  version, and the agent saying it fixed the problem is not itself evidence that the request met
  the criterion.
- **kind:** generator
- **generator:** the material is whatever goes wrong in the learner's own app, so no two instances
  match and the learner doesn't choose the problem. Hold fixed: the request is written alone, before
  the agent has been told anything about the problem, and sent word for word; straight after it,
  the learner sends this message unchanged: "Before you change anything: using only what I wrote,
  try to make this problem happen yourself, and tell me whether you could. List anything you had to
  guess, or look up, because my message didn't say it." The agent's reply to that message is part
  of the record. No instance if the agent found the problem first, if the problem had already been
  discussed with the agent, or if the learner can't say what the app should have done instead (then
  it is not yet a problem they can describe, and the tutor serves `a-describe-planted-bug`). Nobody
  sets the difficulty. A problem visible on one screen is a fair instance here, unlike the Easy
  planted ones, because here the learner also had to notice it and know what should have happened.
- **worked example:** if the learner stalls before writing, show them `r2` or `r7` from
  `tasks/sort-bug-requests.md` and let them adapt its shape to their own problem. That counts as
  help.
- **doesn't show:** the agent is the stranger here, and an agent can report that it made the problem
  happen when it actually found the cause by reading the code, so "yes, I could" is weaker evidence
  than it looks; the judge rules on the request, and the reply only informs that. The learner
  decides when a problem is worth a request, so the problems examined are the ones they noticed. And
  nothing controls the category, so a pass may come from a problem none of this topic's words bear
  on.
- **offer as:** the real thing: a problem you actually hit, in the app your agent actually built,
  sent to your actual agent, with one extra message asking whether what you wrote was enough. Only
  possible once your own app exists and misbehaves, which makes it the natural candidate for review
  visits later in the term. `a-describe-planted-bug` is the one to take now.

### `a-read-devtools-on-starter`

- **serves:** `c-run-browser-check`
- **supports:** orient, deepen
- **artifact:** MDN Web Docs, "What are browser developer tools?",
  https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools
  (free, no account, about 2,000 words; 30 to 35 minutes with the doing). Sections: How to open the
  devtools in your browser; The Inspector: DOM explorer and CSS editor; The JavaScript debugger;
  The JavaScript console. The opening section gives keyboard shortcuts and menu routes for Firefox,
  Chrome, Opera and Safari, and says Safari's tools have to be switched on first. The console
  section has the reader enter three snippets (an alert, a purple page background, an added image),
  then three deliberately broken versions of them, to see what the console reports. The page sends
  the reader to MDN's own example site to try them; this activity uses the learner's own starter app
  instead.
- **learner does:** has their starter app open at its localhost address and does each part of the
  page on that tab, never on the MDN page or MDN's example site:
  1. Opens the developer tools the way the page says for their browser, switching on Safari's
     developer features first if that is their browser.
  2. Right-clicks the Count button, chooses Inspect, and says what text the highlighted line holds.
     Skims the CSS editor and debugger sections only far enough to recognize those panels.
  3. In the console, enters the page's first two snippets (the alert, then the purple background)
     and watches what happens. If the browser refuses a paste and shows a warning instead, reads the
     warning out and does what it says.
  4. Runs one of the page's broken versions, then copies the whole error it produces, exactly as
     shown, into the chat with the tutor.
  5. Takes a screenshot of the purple page with the developer tools open, and puts it in the chat.
  6. Reloads the tab, and says what happened to the purple and why they think so.
- **tutor role:** explainer
- **tutor does:** before step 3, asks the learner which tab the snippet will run in, and why it
  matters that it is their own app. If a paste warning appears (Chrome, for one, blocks pasting into
  a new user's console until they type "allow pasting"), explains it as the browser guarding against
  exactly what this goal rules out: running something someone handed you in a page where you are
  logged in. After step 4, compares the pasted error with what a full copy contains, and says which
  line was dropped or retyped, if any. After step 6, ties the purple disappearing to the snippet
  having changed only this page load. Explains the DOM only as "the page as the browser holds it
  right now", doesn't teach the debugger, and doesn't explain the snippets' code beyond what each
  one does to the page.
- **done when:** with the page beside them, the learner has opened the console on their own app's
  tab, run snippets they were given, copied a complete error into the chat, and put a screenshot in
  the chat. No `checks`: the steps come from the page, and nobody asked for a report an agent could
  act on.
- **offer as:** read-and-do on your own app, in the order of a real reference page. It covers every
  major browser, including switching on Safari's tools, and you finish having copied your first
  error and taken your first screenshot for someone else. The slower of the two (30 to 35 minutes)
  and the only one with your hands on a browser. `a-judge-check-reports` needs no browser, and is
  about what makes a report good rather than how to get one.

### `a-judge-check-reports`

- **serves:** `c-run-browser-check`
- **supports:** deepen
- **artifact:** `tasks/judge-check-reports.md`, written for this topic: two requests a coding agent
  made for checks in the browser on a small Tasks app, ten replies students sent back, and a key for
  the tutor. Two replies would let the agent act; eight wouldn't, each for a different reason: a
  paraphrased error, an error cut to its first line, a cropped screenshot of text that could have
  been copied, a snippet run in the wrong tab, "same as before", a warning left out on purpose, a
  description where a screenshot was needed, and a screenshot cropped too tightly. 15 to 20
  minutes. No browser needed.
- **learner does:** for each of the ten replies, answers yes or no: could the agent act on this
  without asking again? For each no, writes the question the agent would have to send back. Then
  says what the two that worked have in common. Then picks one reply they marked no and rewrites it
  the way they would have sent it, describing any screenshot in brackets as the file does.
- **tutor role:** critic
- **tutor does:** shows everything above the key and nothing in it. Takes all ten answers before
  commenting on any. On each disagreement with the key, asks what the agent would do next with that
  reply rather than giving the verdict. Makes sure `a5` gets discussed whatever the learner answered,
  because there the trouble is not the report but where the snippet was run. Reads the rewrite as
  the agent would.
- **done when:** the learner's account of what the two have in common covers complete, unedited,
  copied text where it can be copied, a screenshot where it can't, and the app's own tab; and the
  rewrite would let the agent act. No `checks`: judging other people's reports is not carrying out
  a check.
- **offer as:** no browser and no app, 15 to 20 minutes, and about what makes a report something an
  agent can act on rather than about how to find the console. Ten replies to the same two requests,
  so the only thing that changes is how the report was made. The quickest way to see why "complete
  and unedited" is stricter than it sounds. Take `a-read-devtools-on-starter` first if you have never
  opened the developer tools.

### `a-run-tutor-agent-check`

- **serves:** `c-run-browser-check`
- **supports:** attempt
- **checks:** `c-run-browser-check`
- **artifact:** no external source. The learner's own Vite + React starter app running on their
  laptop, or a scratch copy of it with something planted per the generator; the learner's own
  browser; the tutor playing a coding agent. 15 minutes.
- **learner does:** gets one request, worded the way a coding agent asks for a check in the browser.
  Carries it out on their own app's tab only (the starter or its copy, both of which are theirs and
  on their laptop), and replies to the "agent" with what it produced: copied text wherever the output
  can be selected, a screenshot wherever it can't (pasted into the chat, or saved with its file path
  given), complete and unedited, errors and warnings included. If the snippet fails, reports the
  failure as it appeared rather than fixing the snippet. If the request would have them run
  something anywhere other than their own app, says so instead of running it. Works alone.
- **tutor role:** role-play partner
- **tutor does:** before the attempt, builds the instance per the generator and writes into the
  record the request and what a complete report must contain, established in advance: by running the
  same steps itself in a headless browser against the same address if it has one, and otherwise by
  choosing a check whose output is fixed by construction. Plays a literal coding agent: sends the
  request, then waits, helping only if asked and writing down any help word for word. When the reply
  comes, answers as that agent would, either acting on it in one line or sending the question it
  would have to ask, and records which. Sends the adjudicator the request, the expected content, the
  learner's reply verbatim with any screenshot, every piece of help, and the agent-voice response.
  Afterwards, tells the learner what was missing, if anything. Labels the attempt
  `a-run-tutor-agent-check/<cases>`, naming which of `screenshot`, `error` and `other-tab` the
  instance included (or `plain`). Stops any server it started. Never issues a request aimed at a site
  other than the learner's own app.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: one request, in an agent's voice, with any snippet in a
  code span the learner can copy exactly; the target is the learner's own app at a localhost address;
  the tutor knows what a complete report contains before sending the request; the learner never
  writes or changes code; nothing in the request touches anything outside the app.
  What varies:
  - the kind of check: run a snippet and report what it prints (`document.title`, `location.href`,
    `document.querySelectorAll('button').length`, or `localStorage.getItem(...)` for a key the copy
    sets on load); do an action, then report everything the console shows; inspect an element and
    report its text; show what something looks like (the page at the narrowest window width, a
    panel, an error overlay).
  - the output's shape: one line; an object or array; several console messages; an error with lines
    of detail under it.
  - whether it can be copied: text in the console or the inspector can be; how the page looks can't
    be; some checks need both.
  - errors: none; a snippet that throws; or an error the copy logs, with a fixed message, when a
    button is clicked. A real React rendering error prints extra lines that differ between versions,
    so use one only when a headless browser has confirmed the exact output first.
  - the tab: only the app open; or another ordinary site already open in a second tab from the
    learner's own browsing, with a request that says "in the console" without naming the tab.
  Difficulty: Easy is one snippet, a one-line text result, no error, only the app open. Medium is an
  object, array or several messages, or an action before reading the console, or a warning or error
  in the output, with another tab open. Hard needs both copied text and a screenshot, or includes an
  error with several lines of detail, and the request doesn't name the tab while another site is
  open. An attempt meant to count runs at Medium or Hard; Easy is for the worked example and for a
  retry with help after a miss. Across attempts and review visits, cover at least once each a report
  that needs a screenshot, one whose output includes an error, and one with another site open,
  reading the labels `served.mjs` returns.
- **worked example:** do one Easy instance together: the tutor says which tab to click into and why,
  has the learner open the console and run the snippet, then shows how to select all of the output
  and copy it, and how to screenshot just the browser window (Cmd+Shift+4 then Space on a Mac,
  Win+Shift+S on Windows). At the first level of help on a real attempt, give only the question
  "which tab is this going to run in?".
- **doesn't show:** the tutor's request is tidier than a real agent's, and the learner knows they are
  being checked, so a pass doesn't show they would be as careful in the middle of their own work.
  The other-tab case only ever puts an ordinary tab in the way; it never shows the learner declining
  a request that actually points at a site where they are logged in, and nothing here should
  construct one. The copy is a tiny app, so a long, noisy console is never met. And whether the
  agent could act on the report is ruled from the tutor playing a literal agent, not from a real one.
- **offer as:** the check on the app you already have, with the tutor as the agent. The tutor knows
  exactly what a complete report should hold, so what you missed comes back specific. Available now,
  before your own app exists; 15 minutes and a live session. `a-report-own-agent-check` is the same
  thing when your real agent asks during real work.

### `a-report-own-agent-check`

- **serves:** `c-run-browser-check`
- **supports:** attempt
- **checks:** `c-run-browser-check`
- **artifact:** no external source. The learner's own coding agent session while it works on their
  own app, at a moment when the agent asks them to look at something in the browser or run something
  in its developer tools. 5 to 10 minutes on top of the work.
- **learner does:** carries out the agent's request on their own app's tab only, and replies with
  what it produced: copied text where it can be copied, a screenshot where it can't, complete and
  unedited, errors included. Keeps the transcript from the agent's request through the agent's next
  message after the reply, screenshots included, and brings it to the tutor.
- **tutor role:** none
- **tutor does:** afterwards, reads the excerpt and checks that the request came from the agent
  rather than from the learner asking to be set a check. Sends the adjudicator the request, the reply
  with its screenshots, and the agent's next message, noting whether that message acted on the result
  or asked for it again, and whether a repeated ask was about the report or about something new.
  After the ruling, tells the learner what the agent would have needed, if anything.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the learner's own agent asks for, so no two instances
  match and nobody sets the difficulty. Hold fixed: the request comes from the agent without the
  learner having asked to be set one; the reply is the learner's own, unhelped; the excerpt runs from
  the request through the agent's next message and keeps every screenshot. No instance if the agent
  looked for itself with a headless browser instead of asking, or if the screenshots were lost. A
  check the learner ran somewhere other than their own app is an instance, and a miss.
- **worked example:** if the learner is unsure what to send, show `a1` and `b2` from
  `tasks/judge-check-reports.md` as the shape of a reply that worked. That counts as help.
- **doesn't show:** the agent's next message is a noisy signal, since an agent may press on with too
  little or ask again out of habit, so the ruling is on the report against the request, with the
  agent's response as evidence rather than verdict. Which checks come up is up to the agent, so a
  pass may never have involved a screenshot, an error or a second tab. And the learner decides which
  exchanges to bring, so the ones that went badly may never be seen.
- **offer as:** the real thing: your own agent asks during real work on your own app, and you are
  judged on whether it could carry on without asking you again. Only possible once your own app
  exists and your agent is asking for checks, which makes it the natural candidate for review visits.
  `a-run-tutor-agent-check` is the one to take now.

### `a-w-component`

- **origin:** generated
- **serves:** `w-component`
- **checks:** `w-component`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-state`

- **origin:** generated
- **serves:** `w-state`
- **checks:** `w-state`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-render`

- **origin:** generated
- **serves:** `w-render`
- **checks:** `w-render`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-event-handler`

- **origin:** generated
- **serves:** `w-event-handler`
- **checks:** `w-event-handler`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-dev-server`

- **origin:** generated
- **serves:** `w-dev-server`
- **checks:** `w-dev-server`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-dependency`

- **origin:** generated
- **serves:** `w-dependency`
- **checks:** `w-dependency`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-build`

- **origin:** generated
- **serves:** `w-build`
- **checks:** `w-build`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-hot-reload`

- **origin:** generated
- **serves:** `w-hot-reload`
- **checks:** `w-hot-reload`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-browser-console`

- **origin:** generated
- **serves:** `w-browser-console`
- **checks:** `w-browser-console`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-hard-reload`

- **origin:** generated
- **serves:** `w-hard-reload`
- **checks:** `w-hard-reload`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-routing`

- **origin:** generated
- **serves:** `w-routing`
- **checks:** `w-routing`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-headless-browser`

- **origin:** generated
- **serves:** `w-headless-browser`
- **checks:** `w-headless-browser`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
