# Activities — react apps

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-09-17. Settle three things before offering anything, because they decide what can count:
whether the learner's Vite + React starter project is on their laptop and runs, whether this
session can run hidden subagents (or the learner can open a separate session for setup), and
whether you have a headless browser. Until the learner's own app exists, each capability's only
check runs on that starter. `a-describe-planted-bug` needs the hidden setup or every attempt is
`unaided: no`, and a headless browser is what tests its reproduction clause; without one,
`a-run-tutor-agent-check` is limited to checks whose output is fixed by construction.

**On `c-describe-app-bug`.** Both checks test the "could make it happen again" part directly only
when a headless browser follows the request. Without one, `a-describe-planted-bug` is ruled by a
judge who already holds the true steps and `a-describe-own-app-bug` leaves that part unexamined; in
either, you can give a fresh subagent only the request, have it write out what it would do from a
freshly opened page and every place it would have to guess, and send that to the adjudicator as
well. The guess clause is examined only when a guess or a theory is in play, so make the learner's
first counting planted instance one whose complaint carries a theory.

**On `c-run-browser-check`.** Either check can meet this goal without the learner ever choosing
the app's tab unprompted or turning down a request aimed outside their app: a Medium
`a-run-tutor-agent-check` instance names the app in the request, and a real agent seldom asks for
anything elsewhere. To have that part of the criterion examined before the goal is met, make the
learner's first counting `a-run-tutor-agent-check` attempt a Hard `unnamed-tab` or `elsewhere`
instance.

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
| `c-describe-app-bug` | `a-read-tatham-bug-reports`, `a-sort-bug-requests`, `a-narrated-planted-bug` | `a-describe-planted-bug`, `a-describe-own-app-bug` | see Check notes |
| `c-run-browser-check` | `a-read-devtools-on-starter`, `a-judge-check-reports` | `a-run-tutor-agent-check`, `a-report-own-agent-check` | see Check notes |

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
- **verified:** 2026-09-17
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
  4. Clicks Count up to 5, then asks the tutor to change the page's main heading to any words they
     choose and save, and watches the page without touching it. Says whether the count survived.
  5. Opens the browser's developer tools on the app's tab, finds the Console, and says what is in
     it (it may be empty). Compares it with what the terminal window shows.
  6. Adds `/about` to the end of the address, presses Enter, and says what changed on screen and
     what didn't.
  7. Stops the dev server with Ctrl+C in its terminal, reloads the tab, and says what happened.
     Starts it again.
  8. Leaves the dev server running in its terminal, opens a second terminal window in the same
     folder (the tutor says how, for their system), and there runs `npm run build`, then
     `npm run preview`. Opens the address the preview prints, asks the tutor for another wording
     change, and says whether the preview page changed by itself. Then looks at the dev server's
     tab again.
  9. Opens the copy's folder in their file browser, finds `node_modules`, and asks the tutor how
     many packages are in it and where they came from.
  10. Watches the tutor either open the copy with a headless browser and show what it saw, or say
      what one would do.
  Three rows will point at something other than a visible change the learner made happen: hard
  reload (it looks exactly like an ordinary reload here), routing (the address changes and the
  screen doesn't), and headless browser (the tutor does it, or only describes it). That is
  expected. No code is read at any step.
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
- **done when:** every one of the twelve rows points at something the learner saw or did (for hard
  reload and routing, at what did not change; for headless browser, at what the tutor did or
  described), and the learner can
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
  (free, no account). Three pieces of it only, none with any code: the section "Why do frameworks
  exist?" (about 210 words), and from the section "Other things frameworks give us" its opening
  paragraph (about 40 words) and its subsections Compartmentalization (about 120 words) and Routing
  (about 270 words). About 650 words, 5 minutes of reading inside a 25 to 30 minute session. The
  first section introduces state ("In software development, this underlying data is known as
  state"), uses render in passing ("render a list of tasks"), and states the problem of updating the
  UI to match the state. Compartmentalization introduces components. Routing explains the URL in
  the address bar, single page apps, and client-side routing. The page's running example is a to-do
  list; it mentions React but never Vite. Skipped: "The verbosity of DOM changes" (mostly code),
  "Another way to build UIs" (prose with a short Vue example, about how code gets written, which is
  past this topic's depth), the Tooling subsection (about testing and linting, none of this topic's
  tooling words), and everything after Routing, which is about choosing a framework.
- **verified:** 2026-09-17
- **learner does:** reads the three pieces with their own starter app running in a browser window
  beside the page. Stops at each of these as the page reaches it: state; updating the UI to match
  the state; components; the URL in the address bar; single page app; client-side routing. At each,
  says what on the running starter app it corresponds to, or says they can't find anything, before
  reading on. After the read, takes the eight words the reading never mentions (event handler, dev
  server, dependency, build, hot reload, browser console, hard reload, headless browser) one at a
  time: the tutor names the word and one place on the starter to look, and the learner says what
  they think the word names there before hearing anything about it. A guess, or "no idea", is a
  fine answer. Ends each word by saying it back in their own sentence, after the tutor's reply.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the six stopping points and when asked.
  At each stopping point, takes the learner's answer first and replies with a near-miss question
  rather than a verdict. Useful anchors on the starter: the count is state, and clicking Count
  updates the screen to match it; the starter has no routing, so typing a different path after its
  address shows the same page. For the eight words, goes in the order someone using an app meets
  them, and for each gives the word and a place to look, never a definition, then waits for the
  learner's answer: dev server (the terminal where `npm run dev` is running), dependency (the
  `node_modules` folder), event handler (the Count button), hot reload (the "save to test HMR" line
  on the page), hard reload (the reload button, and what the browser may have kept from last time),
  browser console (the Console panel, as against that terminal), build (the `npm run build`
  command), headless browser (the agent looking at this same page without a window). Replies to a
  guess with a near-miss question ("you said the event handler is the button; is it still there if
  the click does nothing?"), and to "no idea" with a short pointer, then asks for the word back in
  the learner's own sentence rather than accepting agreement. Where a word takes one action to
  show, has the learner do it on the starter now: click Count, open the console. Makes no change to
  the starter project.
- **done when:** each of the six stopping points has an answer tied to the starter app, or an
  honest "can't find it" that the tutor then resolved, and each of the eight missing words has the
  learner's first answer and their own closing sentence. This entry carries no `checks`: the
  readiness indication is taken in `a-dry-run-both-asks`, which follows.
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
  again. A plain no to both halves is `criterion: not met`: record it, ask what is missing, and offer
  whichever orientation route they didn't take, or a study activity on the half they named. Don't put
  the question again in the same sitting. This goal isn't required, so a no never blocks anything
  else they want to try.
- **kind:** generator
- **generator:** vary the made-up problem and the request; hold everything else fixed. The problem
  is one sentence in a user's words describing what one category from `a-describe-planted-bug`'s
  generator would look like on the starter app, for example `wrong-amount` ("suppose Count went up
  by 2 every time you clicked it") or `blank-screen` ("suppose the starter had a Reset button, and
  clicking it turned the whole page white"). The request is one Easy request from
  `a-run-tutor-agent-check`'s generator, aimed at the starter app: one snippet with a one-line text
  result and only the app open ("Could you open the console on the app, run `document.title`, and
  paste me what it prints?"). Fixed: two rehearsals in that order, neither graded, then the readiness
  question word for word. Difficulty doesn't vary: this settles an indication, not a capability.
- **worked example:** if the learner freezes on the first rehearsal, the tutor answers a different
  made-up problem out loud first, in two or three sentences, then hands the original back. If they
  freeze on the second, the tutor says which tab to click into and where the Console is, and lets
  them do the rest.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about whether the learner can do either capability: both rehearsals are helped and
  ungraded, the problem is imagined rather than seen in a running app, and the request is the
  easiest kind. It also shows nothing about any of the twelve words, which have their own supply.
- **offer as:** the short step that closes orientation, after either `a-tour-starter-app-words` or
  `a-read-why-frameworks-exist`. Not an alternative to them: they give you the shape, and this is
  where you say whether you have it. Ten minutes, on the app you already have.
- **check note:** `done when` covers only a yes with a hedge and a no to both halves. A plain no to
  either half is `criterion: not met`, handled like the no to both but offering study on the half
  they said no to; a hedge on both halves is `criterion: unclear`, handled like a single hedge.

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
- **verified:** 2026-09-17
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
  and a key for the tutor. Four requests pass. Of the four that fail, three are near misses (`r1`,
  `r3`, `r5`) and one is plainly bad (`r8`), there to be set beside `r6`, which describes the same
  bug well. Between them they cover a task gone after a reload, a task page that works when clicked
  through to but not when its address is pasted, a saved change that doesn't appear, a white page
  whose only explanation is in the console, and a problem visible on one screen. 20 to 25 minutes.
  No app or browser needed.
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
  answer. Three pairs are built to be compared: `r3` and `r7`, `r2` and `r5`, and `r6` and `r8`. If
  one of a pair was misjudged, puts the two side by side. `r6` and `r8` are there less for the
  verdict, which is easy, than for what exactly `r6` has that `r8` lacks. Reads the two rewrites as a stranger would and says where
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
- **tutor does:** sets up the copy and the plant the way `a-describe-planted-bug`'s `tutor does`
  describes, including keeping the plant and the true steps out of the learner's reach, and gives
  them that instance's description and complaint. A learner who sees the plant anyway spoils nothing
  here, since this activity checks nothing, but then that category is not used for their next
  attempt at `a-describe-planted-bug`. Then composes the
  request out loud from what the learner reports, saying what it is weighing at each sentence, and
  makes two false starts on purpose, visibly, then corrects them. First it writes the cause as
  though it had been seen ("the app isn't saving the list") and rewrites it as a labeled guess. Then
  it writes the steps starting from wherever the learner happens to be, asks "what would a stranger
  have on screen at step one?", and rewrites them from a freshly opened page. Adds the "fixed when"
  line last and says why it comes last. After the learner's written prediction, says which sentence
  in the first drafts would have sent a stranger wrong. Labels the attempt
  `a-narrated-planted-bug/<category>`. A watched category does not count as one the learner has
  had: `a-describe-planted-bug`'s rotation reads only its own labels, so the learner still attempts
  this category themselves later, just not as their very next attempt. Stops the copy's dev server
  at the end.
- **done when:** the learner can name, in order and with the finished request on screen, the parts
  of the request: where to start, the steps, what happened, what should have happened, how to tell
  it's fixed, and the guess set apart. No `checks`: the tutor wrote the request.
- **offer as:** watch it done on a live, broken copy of your own starter app, with the false starts
  left in. The only candidate that shows the weighing a finished request hides, and the only study
  route where you use a running app before being checked on one. Needs a live session and a
  scratch copy of your starter project. Pick `a-sort-bug-requests` for a faster route with no app.
- **check note:** The learner finds the steps and you narrate only the writing, and the entry says
  nothing about a learner who can't make the problem happen, which is likely with `pasted-address`.
  Nothing is checked here, so think out loud about what to try next from the complaint (what does
  someone who is sent a link do with it?), since that weighing is also hidden in a finished request;
  if it still stalls, read `ground-truth.md` yourself and steer from it without showing it.

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
- **tutor does:** first asks the learner where their starter project is, and tells them not to open
  anything in the scratch directory the copy will live in. Then keeps the plant and the true steps
  out of the learner's reach, including out of the session they can scroll back through. The way
  to do that: hand the setup to a subagent in a fresh context whose tool calls and output the
  learner is not shown. It copies the starter project (including `node_modules`) to a scratch
  directory outside any repository the learner commits to, plants one problem per the generator,
  starts the copy's dev server on a free port, confirms the problem happens if it has a headless
  browser, and writes two files beside the copy: `for-learner.md` (the address, the description,
  the complaint) and `ground-truth.md` (the category, what was planted in plain words, the exact
  steps from a freshly opened page that make it happen, what Back and a reload do where they matter,
  what the app does once it's fixed, and whether the problem was confirmed). The tutor reads only
  `for-learner.md` at this point. With no subagent available, the same setup is done in a separate
  session before this one opens. If neither is possible, or the learner saw the plant, the true
  steps or `ground-truth.md`, the attempt is recorded `unaided: no`.
  Gives the learner what is in `for-learner.md`, then waits, helping only if asked and writing down
  any help word for word. When the request is in, and before stopping anything, runs the stranger
  test if a headless browser is available: a second fresh subagent gets only the request text and
  this instruction: "You have not seen this problem. Don't read or open any files. Using a headless
  browser, follow these steps exactly as written. Report what you did and what you saw at each step,
  whether the problem happened, every place you had to guess, and whether the request tells you how
  to know it has been fixed." Only then reads `ground-truth.md`. Sends the adjudicator the ground
  truth, the description and complaint as given, every piece of help, the request verbatim, and the
  stranger's report, or a note that no stranger run was possible. After the ruling, tells the
  learner what a stranger was stuck on, if anything. Stops the copy's dev servers. Labels the
  attempt `a-describe-planted-bug/<category>`. If the learner can't make the problem happen within
  10 minutes, suspects the instance before the learner: has a subagent follow the ground-truth steps
  in a headless browser, or reads the plant, and if the plant was faulty, records nothing against the
  goal and serves a fresh instance.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: one problem per copy; it happens every time its steps
  are followed from a freshly opened page, never only sometimes; it can be made to happen and seen
  from the browser alone (the page, the address bar, reloading, a new tab, the console), with no
  project file opened; no new dependency is installed; the learner gets the description and the
  complaint and nothing else; `ground-truth.md` is written before the learner starts. The
  complaint never names the true cause and never gives away a step (no "reload", "address", "link
  pasted" or "console").
  What varies: the category, where on the page it shows, the wording of the description and
  complaint, and whether the complaint carries a theory. In about half of instances, the complaint
  adds the user's own theory of the cause, in the user's words and plausibly wrong ("I think my wifi
  keeps dropping", "I think the links expire after a while"). The theory must not give away a step
  either. A learner who passes it on as something seen has written an unlabeled guess; the ground
  truth notes that a theory was given. Categories, each with one way to plant it:
  - `wrong-amount` (Easy): Count goes up by 2 per click. Complaint: "the counter seems off".
  - `does-nothing` (Easy): a new button, described as doing something visible, whose click is
    connected to nothing. Complaint: "the new button is broken".
  - `one-step-behind` (Easy): a line under Count reading "You have clicked N times" that always
    shows the number from the click before. One click shows it, so it sits with the other Easy
    categories. Complaint: "the click message is wrong".
  - `reload-forgets` (Medium): a small list the user can add items to, kept only in the component's
    state, with the description saying the list is kept. Items are gone after a reload. Complaint:
    "the things I add keep disappearing".
  - `pasted-address` (Medium): a short list where clicking an item changes the address to
    `/items/<n>` with `history.pushState` and shows that item's page, and the item page takes its
    item from the click rather than from the address. Opening that address in a new tab, or
    reloading on it, shows the page without its item. Vite's dev server serves the app for any path,
    so the page itself loads; it's the item that is missing. Back must work: handle the browser's
    `popstate` event so that Back returns to the list with the list on screen, and the pasted
    address is the only problem in the copy. The ground truth says what Back does. Complaint:
    "links to items don't work when I send them to someone".
  - `change-not-showing` (Hard): once the learner has the page open, the tutor, speaking as their
    agent, announces that it changed a piece of visible text and saved, but the learner's tab
    doesn't get it. Plant it one of two ways: a second copy on another port, already edited during
    setup, while `for-learner.md` gives the learner the first copy's address; or have a hidden
    subagent stop the copy's dev server once the learner has the page open, just before the
    announcement, so the old text stays until a reload fails. No complaint: `for-learner.md`
    carries the announcement's wording instead, and the tutor delivers it in the agent's voice.
  - `blank-screen` (Hard): a Reset button sets a value to something the page can't display, so an
    error is thrown while the page is being drawn and the page goes white, with the explanation only
    in the console. Confirm the page really goes blank. If Vite's red error overlay appears
    instead, the explanation is on screen and this is a different, easier instance: change the
    plant. Complaint: "sometimes the app just goes white".
  Difficulty: Easy is visible on the first screen after one action, with no reload, new tab or
  console involved (`wrong-amount`, `does-nothing`, `one-step-behind`). Medium needs a reload or a
  second tab (`reload-forgets`, `pasted-address`). Hard is `change-not-showing` or `blank-screen`,
  where the screen alone doesn't show what went wrong. An attempt meant to count runs at Medium or
  Hard; Easy is for the worked example and for a retry with help after a miss. Across attempts and
  review visits, serve a Medium or Hard category the learner hasn't had, until `reload-forgets`,
  `pasted-address`, `change-not-showing` and `blank-screen` have each come up once. "Had" means a
  label beginning `a-describe-planted-bug/` among those `served.mjs` returns; a category the learner
  only watched in `a-narrated-planted-bug` doesn't count, but isn't served as their very next
  attempt either.
- **worked example:** work one Easy instance live: make the problem happen twice from a freshly
  opened page, saying what is on screen at each step, then write the request in front of the learner
  with its parts in order (the address, the steps, what happened, what should have happened, how to
  tell it's fixed, any guess set apart and labeled). At the first level of help on a real attempt,
  give only the question "what would someone need on screen before your first step?" and let the
  learner do the rest.
- **doesn't show:** the learner is told that a problem exists and what the app is for, so a pass
  doesn't show they would notice one, or know what should have happened, in an app nobody described
  to them. The copy is a tiny app they already know and every problem is repeatable by design, so
  describing something that happens only sometimes is never examined. Whether a stranger could make
  it happen is tested directly only when a headless browser is available for the stranger run.
  Without one, the judge reads the request with the true steps already in hand and can fill gaps a
  real stranger would stall on, so a pass then rests on the judge's reading rather than on
  anyone following the request. The request is never sent to an agent that fixes things, so a pass
  doesn't show an agent would go on to fix the right thing. The guess clause only comes into play
  when the learner writes a guess or the complaint carries a theory, which is about half of
  instances. A pass in one category is thin evidence about the others: a `blank-screen` pass shows
  nothing about remembering to mention a pasted address. Easy instances
  are kept out of counting attempts because a problem visible on one screen after one click
  involves none of the reload, new-tab, saved-change or console cases this topic's words are about.
- **offer as:** a problem planted in a copy of the starter app you already have, where the tutor
  picks the kind of problem, so the ones this topic is about (gone after a reload, a pasted address
  that fails, a change that never shows up, a white page) actually come up. Available now, before
  your own app exists. Needs a live session and 20 to 25 minutes. `a-describe-own-app-bug` is the
  same capability on a real problem in your own app.
- **check note:** Tell the setup subagent to reply with nothing but the path to `for-learner.md` and
  whether setup succeeded. Anything else it says about the plant lands in your context before the
  attempt and in the scrollback the learner can open, which is the leak this setup exists to
  prevent.

### `a-describe-own-app-bug`

- **serves:** `c-describe-app-bug`
- **supports:** attempt
- **checks:** `c-describe-app-bug`
- **artifact:** no external source. The learner's own app, the one their agent builds after this
  topic or any later one, running on their laptop, and a real problem in it that the learner
  noticed. 10 to 15 minutes, at whatever moment the app misbehaves.
- **learner does:** when the app does something it shouldn't, and before telling their working agent
  conversation anything about it, writes alone, in a separate note, the request they will send.
  Then, before sending it there, opens a new conversation with their agent, one that has not seen
  the app being built, and pastes in the request followed by the fixed stranger message given in the
  generator below. Keeps that whole new conversation. Only after that sends the request, word for
  word, to their working conversation to get the problem fixed. Brings the tutor three things: the
  note, unchanged; the whole stranger conversation; and the working conversation from their last few
  messages before the request through the request itself. No tutor is there while this happens.
- **tutor role:** none
- **tutor does:** when first offering this activity, gives the learner the fixed stranger message to
  keep somewhere they can copy it from, and says that anything they look at for help while writing
  gets noted at the top of the note. Afterwards, reads all three. Uses the working excerpt to check
  that the agent hadn't raised the problem and the learner hadn't described it before the request;
  if either, there is no instance. Checks that the stranger conversation got the request unchanged.
  Sends the adjudicator the request as written, the stranger message and the whole stranger reply,
  the working excerpt, any help noted at the top of the note, and, kept separate and labeled as given
  afterwards, the learner's answer to "what did you see that made you write this?". If the stranger
  couldn't use a headless browser, says so to the adjudicator: nobody followed the steps, and
  whether a stranger could make it happen is then unexamined. After the ruling, tells the learner
  what the stranger had to guess, if anything, and offers `a-describe-planted-bug` if reproduction
  went unexamined.
- **done when:** criterion met with no help. The request is judged as written, not a later version,
  and the working agent saying it fixed the problem is not itself evidence that the request met the
  criterion.
- **kind:** generator
- **generator:** the material is whatever goes wrong in the learner's own app, so no two instances
  match and the learner doesn't choose the problem. Hold fixed: the request is written alone, before
  the working conversation has been told anything about the problem; it goes first, unchanged, into
  a new conversation with this message straight after it, also unchanged: "You have not seen this
  problem, and I don't want you to fix it. Don't read or change any project files. Using a headless
  browser, follow the steps in my message exactly as written, against the address it gives. Tell me
  what you did and what you saw at each step, whether the problem happened, every place you had to
  guess because my message didn't say, and whether my message tells you how to know it has been
  fixed. If you can't use a headless browser, say so and stop." Then the same request goes to the
  working conversation. No instance if the agent found the problem first, if the problem had already
  been discussed with the agent, or if the learner can't say what the app should have done instead
  (then it is not yet a problem they can describe, and the tutor serves `a-describe-planted-bug`).
  Nobody sets the difficulty. A problem visible on one screen is a fair instance here, unlike the
  Easy planted ones, because here the learner also had to notice it and know what should have
  happened.
- **worked example:** no tutor is present during the attempt, so nobody offers one. If the learner
  stalls, they may open `tasks/sort-bug-requests.md` themselves and adapt the shape of `r2` or `r7`
  to their own problem. They write at the top of the note that they did, and the attempt is recorded
  `unaided: no`.
- **doesn't show:** the stranger is a fresh conversation with the same agent, told not to read the
  project files, but nothing enforces that; a report that it followed the steps is evidence rather
  than proof. There is no ground truth, so whether the problem the stranger saw is the one the
  learner saw rests on the learner's own after-the-fact account. When the agent has no headless
  browser, nobody follows the steps at all, and the "make it happen again" part of the criterion goes
  unexamined. The learner decides when a problem is worth a request, so the problems examined are
  the ones they noticed. And nothing controls the category, so a pass may come from a problem none
  of this topic's words bear on.
- **offer as:** the real thing: a problem you actually hit, in the app your agent actually built,
  with a fresh conversation of your agent trying your steps before your working one fixes anything.
  Adds a few minutes to real work. Only possible once your own app exists and misbehaves, which
  makes it the natural candidate for review visits later in the term, and it works best if your
  agent can use a headless browser. `a-describe-planted-bug` is the one to take now.

### `a-read-devtools-on-starter`

- **serves:** `c-run-browser-check`
- **supports:** orient, deepen
- **artifact:** MDN Web Docs, "What are browser developer tools?",
  https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools
  (free, no account, about 1,500 words of prose plus short code snippets; 30 to 35 minutes with the
  doing). Sections: How to open the
  devtools in your browser; The Inspector: DOM explorer and CSS editor; The JavaScript debugger;
  The JavaScript console. The opening section gives keyboard shortcuts and menu routes for Firefox,
  Chrome, Opera and Safari, and says Safari's tools have to be switched on first. The console
  section has the reader enter three snippets (an alert, a purple page background, an added image),
  then three deliberately broken versions of them, to see what the console reports. The page sends
  the reader to MDN's own example site to try them; this activity uses the learner's own starter app
  instead.
- **verified:** 2026-09-17
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
  been copied, a reply whose own content shows it was run on some page other than the app, a
  snippet retyped instead of its error being reported (with "same as before" in place of the
  second error), a warning left out on purpose, a description where a screenshot was needed, and a
  screenshot cropped too tightly. 15 to 20 minutes. No browser needed.
- **verified:** 2026-09-17
- **learner does:** for each of the ten replies, answers yes or no: could the agent act on this
  without asking again? For each no, writes the question the agent would have to send back. Then
  says what the two that worked have in common. Then picks one reply they marked no and rewrites it
  the way they would have sent it, describing any screenshot in brackets as the file does.
- **tutor role:** critic
- **tutor does:** shows everything above the key and nothing in it. Takes all ten answers before
  commenting on any. On each disagreement with the key, asks what the agent would do next with that
  reply rather than giving the verdict. Makes sure `a5` gets discussed whatever the learner answered,
  because there the trouble is not the report but where the snippet was run, and the only clue is a
  button that should have been there. Makes sure `a6` is read as two problems, not one: retyping the
  snippet is itself a change to what was asked, however sensible it looked. Reads the rewrite as the
  agent would.
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
  failure as it appeared rather than fixing the snippet. If any part of the request would have them
  run something anywhere other than their own app, says so instead of doing that part, and still
  does and reports the parts that are on their own app. Works alone.
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
  `a-run-tutor-agent-check/<cases>`, naming which of `screenshot`, `error`, `unnamed-tab` and
  `elsewhere` the instance included (or `plain`). Stops any server it started. Never aims any part
  of a request at a site other than the learner's own app, except the named public page in an
  `elsewhere` instance, where declining is the point.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: one request, in an agent's voice, with any snippet in a
  code span the learner can copy exactly; the target is the learner's own app at a localhost address;
  the tutor knows what a complete report contains before sending the request; the learner never
  writes or changes code; nothing in the request touches anything outside the app, except the
  second part of an `elsewhere` request, below. Whenever a second tab is part of the instance, the
  tutor names it: before the attempt, the learner opens https://developer.mozilla.org/ (a public
  page where nobody is logged in) in a second tab of the same browser window, and that window holds
  only the app and that page. In any instance with a second tab, snippets are ones whose output
  would be harmless on any page (a count of buttons, whether a heading exists), never a page title,
  an address or a stored value, and actions are clicks on the app's own buttons.
  What varies:
  - the kind of check: run a snippet and report what it prints
    (`document.querySelectorAll('button').length` in any instance; `document.title`,
    `location.href`, or `localStorage.getItem(...)` for a key the copy sets on load, only when no
    second tab is open); do an action, then
    report everything the console shows; inspect an element and report its text; show what something
    looks like (the page at the narrowest window width, or how a panel is laid out).
  - the output's shape: one line; an object or array; several console messages; an error with lines
    of detail under it.
  - whether it can be copied: text in the console or the inspector can be; how the page looks can't
    be; some checks need both.
  - errors: none; a snippet that throws; or an error the copy logs, with a fixed message, when a
    button is clicked. A real React rendering error prints extra lines that differ between versions,
    so use one only when a headless browser has confirmed the exact output first.
  - the tab, one of four: `app-only` (only the app open); `named-tab` (the MDN page open in a
    second tab and in front when the request arrives, and the request names the app); `unnamed-tab`
    (the same setup, and the request says "in the console" without naming a tab); `elsewhere` (the
    same setup, and the request has two parts: a check on the app, then "run the same line in the
    console on developer.mozilla.org too and paste that"). In `elsewhere`, a pass means doing and
    reporting the first part and saying, instead of doing the second, that it isn't their app.
  Difficulty, with its tab condition stated for each level: Easy is one snippet, a one-line text
  result, no error, and `app-only`. Medium is an object, array or several messages, or an action
  before reading the console, or a warning or error in the output, and `named-tab`. Hard is output
  that needs both copied text and a screenshot, or includes an error with several lines of detail,
  and `unnamed-tab` or `elsewhere`. An attempt meant to count runs at Medium or Hard; Easy is for the
  worked example and for a retry with help after a miss. Across attempts and review visits, cover
  at least once each a report that needs a screenshot, one whose output includes an error, an
  `unnamed-tab` instance and an `elsewhere` instance, reading the labels `served.mjs` returns.
- **worked example:** do one Easy instance together: the tutor says which tab to click into and why,
  has the learner open the console and run the snippet, then shows how to select all of the output
  and copy it, and how to screenshot just the browser window (Cmd+Shift+4 then Space on a Mac,
  Win+Shift+S on Windows). At the first level of help on a real attempt, give only the question
  "which tab is this going to run in?".
- **doesn't show:** the tutor's request is tidier than a real agent's, and the learner knows they are
  being checked, so a pass doesn't show they would be as careful in the middle of their own work.
  An `elsewhere` instance shows the learner declining a request aimed at a public page where nothing
  is at stake. It never shows them declining one aimed at a site where they are logged in, or holding
  out when an agent insists, and nothing here should construct either. The copy is a tiny app, so a
  long, noisy console is never met. And whether the agent could act on the report is ruled from the
  tutor playing a literal agent, not from a real one.
- **offer as:** the check on the app you already have, with the tutor as the agent. The tutor knows
  exactly what a complete report should hold, so what you missed comes back specific. Available now,
  before your own app exists; 15 minutes and a live session. `a-report-own-agent-check` is the same
  thing when your real agent asks during real work.
- **check note:** In any instance with the MDN tab open, choose a check whose correct report could
  not also have come from the MDN page: a button count qualifies (the starter has one button, the
  MDN page many), but whether a heading exists, or a snippet that throws the same error on any page,
  does not, and with those a reply run in the wrong tab reads as a pass. Have the learner open the
  MDN tab early in the session rather than just before the request, so the setup doesn't announce
  what is being tested. Before the request, tell the learner only that you are playing their agent
  and where a screenshot goes; the reporting rules in `learner does`, read out just beforehand,
  would make the attempt a checklist and give an `elsewhere` instance away.

### `a-report-own-agent-check`

- **serves:** `c-run-browser-check`
- **supports:** attempt
- **checks:** `c-run-browser-check`
- **artifact:** no external source. The learner's own coding agent session while it works on their
  own app, at a moment when the agent asks them to look at something in the browser or run something
  in its developer tools. 5 to 10 minutes on top of the work.
- **learner does:** carries out the agent's request on their own app's tab only, and replies with
  what it produced: copied text where it can be copied, a screenshot where it can't, complete and
  unedited, errors included. At the moment they copy the output, also takes an evidence screenshot
  of the whole browser window, with the address bar and the developer tools both visible (one per
  screenful if the output runs longer), and keeps it for the tutor without sending it to the agent.
  Keeps the transcript from the agent's request through the agent's next message after the reply,
  screenshots included, and brings it and the evidence screenshots to the tutor. No tutor is there
  while this happens.
- **tutor role:** none
- **tutor does:** when first offering this activity, tells the learner about the evidence screenshot
  and that anything they look at for help while replying gets noted when they bring the excerpt.
  Afterwards, reads the excerpt and checks that the request came from the agent rather than from the
  learner asking to be set a check. Compares the reply with the evidence screenshots: whether
  anything visible there is missing from or changed in the reply, and whether the address bar shows
  the learner's own app. Sends the adjudicator the request, the reply with its screenshots, the
  evidence screenshots, and the agent's next message, noting whether that message acted on the
  result or asked for it again, and whether a repeated ask was about the report or about something
  new. If there are no evidence screenshots, tells the adjudicator that "complete and unedited" and
  "only in their own app" have nothing to be checked against. After the ruling, tells the learner
  what the agent would have needed, if anything.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the learner's own agent asks for, so no two instances
  match and nobody sets the difficulty. Hold fixed: the request comes from the agent without the
  learner having asked to be set one; the reply is the learner's own; the excerpt runs from the
  request through the agent's next message and keeps every screenshot; the evidence screenshots of
  the whole window are taken when the output is copied and are not sent to the agent. No instance if
  the agent looked for itself with a headless browser instead of asking, or if the reply's
  screenshots were lost. A check the learner ran somewhere other than their own app is an instance,
  and a miss.
- **worked example:** no tutor is present during the attempt, so nobody offers one. If the learner
  is unsure what to send, they may open `tasks/judge-check-reports.md` themselves and look at `a1`
  and `b2`. They say so when they bring the excerpt, and the attempt is recorded `unaided: no`.
- **doesn't show:** the agent's next message is a noisy signal, since an agent may press on with too
  little or ask again out of habit, so the ruling is on the report against the request, with the
  agent's response as evidence rather than verdict. The evidence screenshots show only what was on
  screen: output that had scrolled away, or sat inside a collapsed entry, can't be compared, so
  "complete" is checked only as far as the screen went, and not at all if the learner forgot them.
  Which checks come up is up to the agent, so a pass may never have involved a screenshot, an error
  or a second tab, and declining a request aimed somewhere other than their own app is examined only
  if the agent happens to make one. And the learner decides which exchanges to bring, so the ones
  that went badly may never be seen.
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
