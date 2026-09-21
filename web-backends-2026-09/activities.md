# Activities: web backends

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-check-persistence` | find out whether an app really keeps what its agent says it saves | Given an app whose agent says it now saves something, says what they would do to find out whether it is really kept. It passes when what they describe would catch an app that kept it only in the open page, one that kept it only in that browser, one that kept it only until the server restarted, and one that lost what was already saved when its tables changed. They may ask the agent to restart the server or to change the tables. Asking the agent whether it is saved does not meet it. |
| `c-review-schema` | tell whether the tables an agent proposes can hold what the app has to remember | Given a short description of an app and the tables its agent proposes, each listed with its columns, names anything the app will need to remember that isn't saved in any of the tables, or says that nothing is missing. It passes when they find what is missing without naming anything that isn't, and when nothing is, say so and point to where each thing the app needs to remember is kept. Whether the tables are organized well is not part of it, only whether they can hold what the app needs. |
| `c-trace-action` | follow one action in the app from the click to where it is kept, and back to the screen | Given something a user does in an app with a server and a database, such as adding an item to a list, and a list of the app's parts that doesn't say how they connect, says in order which part of the app handles it and what passes between the parts, from the click until the result is on screen. It passes when every part the action goes through is named, in order, on the way there and back, no part is named that it doesn't go through, and nothing is given to a part that could not do it. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. Activities whose `serves` is `all` sit on the `o-orientation` row only.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-codecademy-backend` | `a-dry-run-backend-asks` | |
| `c-check-persistence` | `a-hunt-planted-forgetting`, `a-judge-persistence-plans`, `a-read-prisma-migrations` | `a-plan-persistence-check`, `a-check-own-app-saves` | |
| `c-review-schema` | `a-sort-missing-claims`, `a-narrated-table-review`, `a-list-own-app-memory` | `a-review-proposed-tables`, `a-review-own-agent-tables` | |
| `c-trace-action` | `a-watch-list-app-requests`, `a-judge-action-traces`, `a-read-mdn-dynamic-request` | `a-trace-described-action`, `a-trace-own-app-action` | |

---

## Activities

### `a-read-codecademy-backend`

- **serves:** `all`
- **supports:** orient
- **artifact:** Codecademy, "What is Back-End Architecture?",
  https://www.codecademy.com/article/what-is-back-end-architecture (the older address
  https://www.codecademy.com/article/back-end-architecture redirects there). Free, no account;
  credited to the Codecademy Team, undated. Read the opening, from "Software engineers seem to
  always be discussing" to "put the pieces all together!" (about 160 words), then these sections in
  order: What are the clients? (about 60 words), What is a back-end? (70), What is a server? (50),
  What kinds of responses can a server send? (75), What is a database, and why do we need to use
  them? (95), What is a Web API, really? (120), Other principles of the request-response cycle (55),
  and Mapping out a request (490). About 1,170 words: 9 or 10 minutes of reading inside a 40 to 50
  minute session, of which the five stops take about 15 minutes and the seven words about 15 more.
  Skipped: the course cards after the opening; What are the core functions of the
  app? (routes, handler functions and middleware, which is how the server's code is organized and
  past this topic's depth); Conclusion; Frequently asked questions. The page has no code blocks and
  no diagrams, and the assigned sections contain no code and no commands: the only text in code
  type is a shop's product address and its path (`http://www.SuperCoolShop.com/products/66432`,
  `/products/66432`) in Mapping out a request. Words in place: back-end and front-end, server,
  request, response, request-response cycle, HTTP, status code (404 and 200), JSON, database,
  database query, Web API, endpoints, routes. What is a server? says "you will often use your very
  own computer as a server when developing apps", which is localhost without the word. Not named:
  localhost, server log, SQL, table, schema, migration, fixture. Two loose sentences are worth a
  word if the learner stops on them: databases "save data in a persistent way in memory" (a
  database keeps it on disk; memory is what is lost when things are switched off), and "Reading and
  writing from static memory is fairly slow". Mapping out a request follows a shopper clicking a
  product on a large shop's site, not an app on a laptop.
- **learner does:** reads with their own app open in a browser window beside the page (the app
  with state from the last lab, or hello-react if that one isn't running). Stops at five points
  and, before reading on, says what in their own app corresponds now and what will correspond after
  the lab adds a server and a database; "nothing yet" is an honest answer:
  1. What is a back-end?: which of its three parts their app has today.
  2. What is a server?: the sentence about your own computer as a server, and the address their
     app is at.
  3. What is a database, and why do we need to use them?: what their app forgets today when the
     page is reloaded.
  4. What is a Web API, really?: two requests their app will need to send once it has a server, in
     plain words ("give me my habits", "save this one").
  5. Mapping out a request, after step 9: looks away from the page and retells the steps for one
     action in their own app as it will work after the lab (adding a habit, say), then compares
     with the article.
  Then takes the seven words the article doesn't name, one at a time: the tutor names the word and
  a place to look, and the learner says what they think it names before hearing anything about it.
  "No idea" is a fine first answer. Ends each word by saying it back in their own sentence.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the five stops and when asked. At each
  stop, takes the learner's answer first and replies with a near-miss question rather than a
  verdict ("you said your dev server is your app's server; once there's a database, which of the
  two will talk to it?"). At stop 5, checks that the retelling has a way back as well as a way
  there: the database answering the server, the server answering the page, the page changing
  what's on screen. For the seven missing words, goes in this order, giving for each the word and a
  place to look, never a definition: localhost (the address in their app's tab); server log (the
  terminal where their dev server runs, and after the lab a second one where the server runs, as
  against the browser console from the last topic); SQL (the "SQL" in SQLite, the database their
  agent is likely to use); table (asks what one table in their app would hold, and what one row of
  it would be); schema (what their agent will show them in the lab, before it builds the database,
  for them to approve); migration (a scenario: after a week of saved habits, they ask their agent
  to add a reminder time to each one); fixture (a scenario: their agent writes a test that starts
  from the same three sample items every time). Replies to a guess with a near-miss question and to
  "no idea" with a short pointer, then asks for the word back in the learner's own sentence rather
  than accepting agreement. If the sitting runs long, takes the seven words at the start of the
  next one instead, before `a-dry-run-backend-asks`. Makes no change to the learner's app.
- **done when:** each of the five stops has an answer tied to the learner's own app, the retelling
  at stop 5 runs from the click to the database and back to the screen, and each of the seven words
  has the learner's first answer and their own closing sentence. No `checks`: the readiness
  indication `o-orientation` is ruled on is taken in `a-dry-run-backend-asks`, which follows.
- **offer as:** this topic's orientation reading: about 1,200 words of plain prose, free, 40 to 50
  minutes with the stops and the words (the words can move to the next sitting). It ends by
  following one click through every part and back, and names endpoint, API and status code where
  they occur. No diagrams, and nothing about what is inside a database (tables, SQL, schema), which
  the tutor raises through the words that follow the reading. Followed by
  `a-dry-run-backend-asks`.

### `a-read-mdn-server-side`

- **artifact:** MDN Web Docs, "Introduction to the server side",
  https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/First_steps/Introduction,
  read as an orientation, with its Dynamic sites diagram redrawn for the learner's own app.
- **status:** dropped: the instructor chose `a-read-codecademy-backend` as this topic's
  orientation reading, 2026-09-21

### `a-read-fullstack-for-builders`

- **artifact:** MindStudio blog, "What Is a Full-Stack App? Frontend, Backend, and Database
  Explained", https://www.mindstudio.ai/blog/what-is-a-full-stack-app, read as an orientation.
- **status:** dropped: the instructor chose `a-read-codecademy-backend` as this topic's
  orientation reading, 2026-09-21

### `a-dry-run-backend-asks`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. The learner's answers at the stops of
  `a-read-codecademy-backend`, and their retelling from its last stop, still in front of them. 10 to
  15 minutes. Nothing needs to be running.
- **learner does:** three short rehearsals, none of them judged, each answered in a sentence or
  two. First, the tutor describes an action in a made-up app with a server and a database, and the
  learner says roughly which parts it goes through, there and back. Second, the tutor, speaking as
  a coding agent, says that something in a made-up app is now saved, and the learner says one or
  two things they would do to find out whether it really is. Third, the tutor shows a short
  description of a made-up app and two tables with their columns, and the learner says one thing
  the app would need to remember that has nowhere to go, or says nothing is missing. Then answers
  the question the tutor puts: with your reading and notes beside you, could you now attempt these
  three things for real: following one action in an app from the click to where it is kept and
  back to the screen; finding out whether an app really keeps what its agent says it saves; and
  telling whether the tables an agent proposes can hold what the app has to remember?
- **tutor role:** explainer
- **tutor does:** sets the three rehearsals from the generator below and grades none of them. If
  an answer shows a misunderstanding (the page talking to the database directly, asking the agent
  whether it saved, calling a count that can be worked out "missing"), explains it once and moves
  on. Then puts the readiness question as written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's own indication, not on the rehearsals and not on
  whether the tutor thinks they are ready. A plain yes to all three parts is `criterion: met`. A
  hedge on any part, with no plain no, is `criterion: unclear`: explain the hedged part once more
  and put the question again; a second hedge stays `unclear`, and the tutor offers a study activity
  on that capability. A plain no to any part is `criterion: not met`: record it, ask what is
  missing, and offer to go back over the reading's stops that bear on the capability named, or a
  study activity on it; don't put the question again in the same sitting. This goal isn't required, so a no never blocks
  anything else the learner wants to try.
- **kind:** generator
- **generator:** vary the made-up app and the three items; hold the rest fixed. The app is small,
  on the learner's laptop, with a page, a server and a SQL database and no logins (a habit tracker,
  a recipe box, a shared grocery list, a workout log, a movie watchlist); each rehearsal may use a
  different one. Rehearsal one is a `save-new` action from `a-trace-described-action`'s generator,
  with the app described in two or three sentences rather than the full description. Rehearsal two
  is an Easy agent message (`items`, `plain`) from `a-plan-persistence-check`'s generator.
  Rehearsal three is an Easy instance from `a-review-proposed-tables`'s generator: two tables, one
  missing fact about a thing. Fixed: three rehearsals in that order, none graded, then the
  readiness question word for word. Difficulty doesn't vary: this settles an indication, not a
  capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about any of the three capabilities: every rehearsal is helped, ungraded, imagined
  rather than seen, and of the easiest kind, and a one-sentence answer never has to be complete. It
  shows nothing about the thirteen words, which have their own supply.
- **offer as:** the short step that closes orientation, after `a-read-codecademy-backend`. Not an
  alternative to it: the reading gives you the shape, and this is where you say whether you have
  it. 10 to 15 minutes, nothing to run.

### `a-watch-list-app-requests`

- **serves:** `c-trace-action`
- **supports:** orient, deepen
- **artifact:** no external source. A small list app that the tutor builds in a scratch folder on
  the learner's laptop, with a page, a server and a SQL database, each server in a terminal the
  learner can see. 35 to 45 minutes; the tutor builds and starts the app before the session, which
  takes it 5 to 10 minutes. Built to this specification, which `a-hunt-planted-forgetting` reuses:
  - The page: a copy of the learner's hello-react project (with its `node_modules`), or a fresh
    Vite + React project if that copy won't run, changed to show a heading, a text box with an Add
    button, the list of items each with a Done box and a Delete button, a line under the list
    reading "N of M done" that the page works out itself, and two controls that act only on screen
    and are never sent to the server: a "Hide done" switch and a "Sort A to Z" button. Served by
    the Vite dev server as usual (http://localhost:5173, or the next free port).
  - The server: a small Node server on its own port (3001, or the next free one) that answers four
    requests: give me all the items; add this item (replies 201 with the saved item); mark this item
    done or not done; delete this item (replies 204). An Add with empty text gets a 400 and the
    message "An item needs some text", which the page shows in red; the page itself does not check
    for empty text. When a request fails because the server can't be reached, the page leaves its
    list exactly as it was and shows "Couldn't reach the server" in red; it never shows a new item
    before the server has answered. The server prints one line per request in its terminal: the
    method, the path, the status code and, in plain words, what it asked the database (for example
    `POST /api/items 201 saved item 4`). The dev server prints nothing per file it sends.
  - The database: a SQLite file `list.db` in the scratch folder, with one table, `items`, whose
    columns are `id`, `text`, `done` and `created_at`. Uses Node's built-in SQLite module if this
    Node version has it without a flag, and otherwise installs `better-sqlite3` into the scratch
    folder.
  - The page sends its requests straight to the server's address (the server allows requests from
    the page's address), not through the dev server, so once the page has loaded the dev server
    takes no part in any action.
  - The scratch folder is outside every repository the learner commits to.
- **learner does:** arranges three things where they can see them together: the app's tab with the
  developer tools' Network panel open, the server's terminal, and the dev server's terminal. For
  action 1 the panel shows every request (its All filter); from action 2 on, it is filtered to
  fetch/XHR requests. Before each of eight actions, says a prediction: will a request go to the
  server, and asking for what? will the server's terminal print a line? will the database change?
  what comes back, and what changes on screen? For action 1, also predicts which server sends the
  page's own files. Then does the action and says what the panel and the two terminals show. The
  actions, in order:
  1. Reload the page.
  2. Type in the box without clicking Add.
  3. Click Add.
  4. Tick Done on one item.
  5. Flip "Hide done", then click "Sort A to Z".
  6. Clear the box and click Add.
  7. Ask the tutor to stop the server, then click Add. (The tutor starts it again, and the learner
     reloads.)
  8. Delete an item.
  At the end, with everything still open, writes the whole path of "click Add" from the click to the
  screen in their own words: each part in order, and what passes between each pair. Opens no
  project file at any point.
- **tutor role:** explainer
- **tutor does:** builds and starts the app before the session and, if it has a headless browser,
  runs each of the eight actions once to confirm they behave as specified. Shows the learner no
  code. Shows how to open the Network panel and switch its filter between All and fetch/XHR
  requests (the filter's name differs slightly between browsers), and which terminal is which, and
  says before action 1 that the dev server's terminal stays silent while it sends files, so its part
  in a reload shows only in the panel. After action 1, points to the many rows from localhost:5173
  (the page's files, sent by the dev server) and the one row from the server's address (the list),
  then switches the filter for the rest. At each action, takes the
  prediction first; after the result, replies with a near-miss question rather than an explanation
  ("the 'N of M done' line changed when you ticked Done; did that number come back from the
  server?"). Ties each action to words as it goes: request and endpoint to the path in each Network
  row and each server line; status code to the 200, 201, 204 and 400; server log to the server's
  terminal, as against the browser console; localhost to the two addresses and their two ports;
  database to `list.db`, and to the items still being there after the restart. At action 7, points
  out that the page went on showing the old list while nothing could be saved: what the page shows
  and what is kept are two different copies. Stops both servers at the end, tells the learner where
  the scratch folder is, and keeps it if `a-hunt-planted-forgetting` is next.
- **done when:** the learner's written path for "click Add" names the page, the server, the
  database, the server again and the page again, in that order, with what passes at each hop (the
  item's text in a request to save it; the server asking the database to store it; the database's
  answer with the new item's number; a response with a success code and the saved item; the page
  adding the item and redrawing); the learner can say which server sent the page's files on the
  reload; and they can say which of the eight actions never reached the server. No `checks`: the
  actions were chosen and ordered for them, and the Network panel and
  the terminals showed each answer.
- **offer as:** see it happen on a real, tiny app on your own laptop before you're asked to
  describe it. The only candidate where every request shows up as it happens, with its status code
  and a line in the server's log. The longest (35 to 45 minutes), and it needs a live session in
  which the tutor can build and run a small app. `a-judge-action-traces` needs nothing running.

### `a-judge-action-traces`

- **serves:** `c-trace-action`
- **supports:** deepen
- **artifact:** `tasks/judge-action-traces.md`, written for this topic: a description of Shelf, a
  small reading-list app on a laptop with a page, a server and a SQL database; three actions in it
  (add a book, flip a "Hide finished" switch, reload the page); eleven traces that students wrote
  for them; and a key for the tutor. Three traces pass. The eight that fail each fail one way: no
  way back from the database, the page handing the book straight to the database, the database
  answering the page, the dev server put on a path it isn't on, "the API" treated as a stop of its
  own, a switch that never leaves the page sent to the server, a reload traced without the dev
  server, and a reload with the right steps in the wrong order. 20 to 25 minutes. No app or browser
  needed.
- **learner does:** reads the app description, then for each of the eleven traces answers: does it
  pass? If not, which one thing is wrong: a part missing, a part named that the action doesn't go
  through, the parts out of order, or something handed to a part that can't do it. Then states the
  rule they judged by, in one or two sentences. Then rewrites two of the failing traces so they
  pass.
- **tutor role:** critic
- **tutor does:** shows the learner everything above the key and nothing in it. Takes all eleven
  answers and the rule before commenting on any. On each answer that disagrees with the key, asks
  what that part would actually do with what it was handed, rather than giving the verdict. Puts
  four pairs side by side if either of a pair was misjudged: `a1` and `a2` (the way back), `a1` and
  `a5` (the dev server on an Add), `c1` and `c2` (the dev server on a reload), `c1` and `c3` (the
  order on a reload). Makes sure `a6` gets
  discussed whatever the learner answered, because it separates the API, which is the set of
  requests a server answers, from a part a request passes through. Reads each rewrite literally and
  says where it still skips or adds a part.
- **done when:** the learner's stated rule covers naming every part in order both ways, naming no
  part the action doesn't reach, and giving each part only what it can do; and both rewrites would
  pass. No `checks`: judging traces other people wrote is not writing one.
- **offer as:** no app and no reading, 20 to 25 minutes. Every trace is about the same small app, so
  the only thing that varies is the mistake, and the three that pass show the right shape for
  three different actions. The fastest route, and the only one that sets the common wrong answers
  side by side. Pick `a-watch-list-app-requests` to see the requests happen instead.

### `a-read-mdn-dynamic-request`

- **serves:** `c-trace-action`
- **supports:** deepen
- **artifact:** MDN Web Docs, "Client-server overview",
  https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview
  (free, no account; its footer says last modified Sep 10, 2026). Four sections only: Dynamic sites
  (about 150 words), Anatomy of a dynamic request (about 490 words, with a diagram numbered 1 to
  7), Doing other work (about 80 words) and Returning something other than HTML (about 95 words).
  About 820 words: 7 minutes of reading inside a 30-minute session. None of the four has a code
  block or a command; the text in code type is the request method names `GET` and `POST` and three
  example addresses (`/best`, `/best?team=my_team_name&show=11`, `/best/my_team_name/11/`). The rest
  of the page is skipped, and does have code: raw request and response messages under GET
  request/response example and POST request/response example, and Python under Web frameworks
  simplify server-side web programming. The worked example is a sports-team site where a coach asks
  for the best lineup: the browser sends a request, the web server passes it to the web
  application, which gets data from the database, fills in an HTML template and sends back a
  finished page with status code 200 (or 404 if the team doesn't exist). Returning something other
  than HTML says a server can instead send back data such as JSON to a page that updates itself,
  which is how the learner's React app will work. Words in place: request, response, status code,
  database, HTTP, URL, server-side, and "logging" once (Doing other work).
- **verified:** 2026-09-21
- **learner does:** reads the four sections. For each numbered step of Anatomy of a dynamic
  request, says which part does it, what it receives, what it hands on, and what would break if the
  step were skipped, before moving to the next. After Returning something other than HTML, rewrites
  the coach's request for a React version of the same site, where the page asks the server for the
  lineup and draws it itself: which steps stay, which drop out, which move to the browser, and what
  now comes back. Then writes the full path of one new action in that React version, the coach
  adding a player to the team, from the click to the screen.
- **tutor role:** socratic questioner
- **tutor does:** stays out of the reading until the learner starts on the steps. At each step,
  asks what would break without it rather than confirming ("if the web server didn't pass it on,
  what would the browser get back?"). Points out that the diagram's Web Server and Web Application
  are, in the app the learner's agent builds, usually one program: the server. Leaves step 7 (the
  static files) aside unless the learner asks, since it belongs to loading the page rather than to
  the coach's request. On the React rewrite, asks about each dropped or moved step: the template
  goes, the drawing moves to the page, and data with a status code comes back instead of a
  finished page. On the final path, checks for the way back, for the database never talking to the
  page, and for the page being the part that changes the screen.
- **done when:** every numbered step has the learner's account of what it does and why it's
  needed; the React rewrite drops the template and moves the drawing to the page; and the path for
  adding a player names the page, the server, the database, the server and the page in order, with
  what passes at each hop. No `checks`: the example was worked for them, and the final path is for
  a site whose parts the reading laid out.
- **offer as:** a worked example to take apart, in prose with a numbered diagram, 30 minutes and
  nothing to run. The reading's trace is for the older kind of site where the server builds each
  page, so the work is converting it to your kind of app, which is where understanding shows.

### `a-trace-described-action`

- **serves:** `c-trace-action`
- **supports:** attempt
- **checks:** `c-trace-action`
- **artifact:** no external source. A made-up app and one action in it, written by the tutor per
  the generator below. 10 minutes.
- **verified:** 2026-09-21
- **learner does:** reads the app's description, its list of parts and the action, then writes
  alone, as a numbered list, every part the action goes through from the click until the result is
  on screen, in order, and for each step what passes to the next part. If the action never leaves
  the page, says so and says what the page does. Hands the list to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing the learner anything: the parts in order, what passes at each hop, and the parts the
  action does not go through. Shows only the description, the parts list and the action. Waits,
  helping only if
  asked and writing down any help word for word. Sends the adjudicator the description, the
  action, the key, the learner's list verbatim and every piece of help. After the ruling, tells the
  learner which hop, if any, was missing, extra, out of order, or handed to a part that couldn't do
  it. Labels the attempt `a-trace-described-action/<kind>`.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed for every instance: the description is four to seven sentences in a user's
  words saying what people do and see, what the app keeps ("close everything, come back tomorrow,
  and your ... are still there"), and anything on screen that it doesn't keep. A list of the app's
  parts follows, always in this form and changed only in names and numbers. It says what each part
  is and what it holds or serves, and never which part talks to which during an action:
  - the page, which runs in your browser;
  - the dev server at localhost:5173, which sends your browser the page's files while you're
    developing;
  - the server at localhost:3001;
  - a SQL database, kept in a file on your laptop.
  Behind the list, every instance is built the usual way, and the key follows it: the page sends
  its requests straight to the server, only the server reaches the database, the dev server does
  nothing but send the page's files, and there are no logins, outside services, second servers or
  caches. None of that is told to the learner. The key states what passes at each hop in plain
  words (the new item's text in a request to save it; the server asking the database to store it;
  the database's answer with the new row; a response with a success code and the saved item; the
  page updating what it shows). Exact addresses, formats and code numbers are never required. Where
  the parts list leaves a choice open, the key accepts either way: after a save or a change, the
  page may show the result from the server's response or by asking the server for the list again,
  as long as every part is named in order there and back.
  What varies: the app (a different one each attempt: habit tracker, recipe box, workout log,
  plant-watering list, movie watchlist, club sign-up sheet, expense splitter, or another), the
  action, and its kind:
  - `save-new` (Easy): the action adds one new kept thing. Path: page, server, database, server,
    page.
  - `change-kept` (Medium): the action changes or deletes one existing kept thing (ticks it,
    renames it, rates it, removes it). Same path, and what passes has to say which one: the page
    tells the server which item and what changed.
  - `page-only` (Easy, never counts): the action touches only something the description says isn't
    kept, or something already on screen: sorting or filtering what's shown, opening details already
    on screen, switching a view the description says resets on reload. The expected answer is that
    it never leaves the page. It is one step long, with no way there and back, so it is kept for the
    worked example, for a retry with help after a miss, and for a practice question after a counting
    attempt, and never counts on its own. If the learner sends it to the server, the tutor asks what
    the server would give the page that the page doesn't already have.
  - `reload` (Hard): reloading the page, or opening the app in a new tab. Path: the browser asks
    the dev server for the page's files and the dev server sends them; the page starts empty and
    asks the server for the kept things; the server asks the database; the database answers the
    server; the server answers the page with the list; the page draws it. The page runs in the
    browser, so "the page asks the dev server for its files" is accepted for the first step, as is
    "the browser asks"; the browser is not a separate part.
  - `refused` (Hard): an action on a kept thing that no longer exists, because the user deleted it
    a moment ago in another tab of the same app on the same laptop; the description says what the
    user then sees ("That item no longer exists"). Path: the page asks the server to change it; the
    server asks the database; the database finds nothing to change and says so; the server answers
    the page that it failed (not found, 404) with the message; the page shows the message and drops
    the item from its list.
  Difficulty: Easy is `save-new` or `page-only`; Medium is `change-kept`; Hard is `reload` or
  `refused`. An attempt meant to count runs at Medium or Hard; Easy is for the worked example, for
  a retry with help after a miss, and for practice. Across attempts and review visits, serve a
  Medium or Hard kind the learner hasn't had, until `change-kept`, `reload` and `refused` have each
  come up once, reading the labels `served.mjs` returns.
- **worked example:** work one Easy instance aloud: name each part as the action reaches it, say
  what it is handed and what it hands on, and at each hop say why this part and not another ("the
  page can't keep anything past a reload, so it has to tell the server; the server's memory goes
  when it restarts, so it asks the database to store it"). At the first level of help on a real
  attempt, ask only "which part hears about the click first, and what does it do with it?"
- **doesn't show:** the app is described, not running, and its parts are listed for the learner,
  so a pass doesn't show they could find out what an app's parts are. Every instance is built the
  usual way (the page asks the server, only the server reaches the database, the dev server only
  sends the page's files), so a pass doesn't show the learner could trace an app built otherwise,
  such as one whose page talks to a hosted database directly or whose dev server passes requests on.
  No instance has a cache, an outside service or a login. An action that never leaves the page
  doesn't count, so the clause about naming no part the action doesn't go through is examined
  through the dev server, which a save or a change doesn't go through, and not through an action
  that stays in the page. What passes is judged in plain words, so a pass says nothing about reading
  real requests or responses. And the learner knows a check is on, so the trace may be more careful
  than one given in the middle of real work.
- **offer as:** the check that's available now, before your own app has a server: a made-up app,
  one action, 10 minutes, nothing to run. The tutor picks the kind of action, so the hard ones (a
  reload, an action the server turns down) actually come up. `a-trace-own-app-action` is the same
  capability on your own app once the lab has added a server.

### `a-trace-own-app-action`

- **serves:** `c-trace-action`
- **supports:** attempt
- **checks:** `c-trace-action`
- **artifact:** no external source. The learner's own app once their agent has added a server and
  a database (in the lab after this topic, or in Problem Set 2), running on their laptop. 15 to 20
  minutes.
- **verified:** 2026-09-21
- **learner does:** gets from the tutor a list of their app's parts, which says what each part is
  but not which talks to which, and one action in their app that the tutor picks. With the
  developer tools closed and the server's terminal out of
  sight, writes alone the path of that action from the click to the screen: each part in order,
  and what passes between them. Hands it to the tutor. Only then does the action in the browser,
  with the Network panel open and the server's terminal visible, and says where their path and
  what they see differ.
- **tutor role:** none
- **tutor does:** before the attempt, reads the app's code (the learner never sees it) and, if it
  has a headless browser, runs the action while watching the server's output, to write the key
  into the record: the parts the action goes through in order, the requests the page sends and to
  which endpoints, what the server asks the database, what comes back with which status code, and
  what the page does with it. Writes the parts list from what it found: every part the app has (the
  page, the dev server, the server, the database, and any other), each with its address or what it
  holds, and never which part talks to which during an action. Picks an action whose path follows
  from what the learner can know about their own app: a save, a change or deletion of a kept thing,
  a reload, or an action on a kept thing already deleted in another tab. Avoids actions where
  whether the page asks the server at all is a choice the agent made and never told the learner (a
  filter or a sort the app might do on the server). If a login, an outside service or a cache lies
  on the path, picks another action or tells the adjudicator. Tells the adjudicator which of two
  choices the learner can't see this app makes, and that either account of them passes: whether
  the dev server passes the page's requests on to the server (Vite's proxy, a common setup), so that
  naming it on a save's path or leaving it out are both accepted; and whether the page shows the
  result of a save or change from the server's response or by asking for the whole list again, so
  that a path with every part in order but no second request for the list is not a miss. On a
  reload the dev server's sending of the page's files is always required. Waits during the attempt,
  writing down any help word for word. Sends the adjudicator the parts list, the action, the key,
  the two choices, the learner's path as written before the Network panel was opened, and every
  piece of help; the learner's comparison afterwards is not part of the ruling. Labels the attempt
  `a-trace-own-app-action/<kind>`, using the kinds in `a-trace-described-action`'s generator.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is the learner's own app, so instances differ as the app does. The
  tutor varies the action and its kind across visits, aiming to cover `change-kept`, `reload` and,
  where the app has one, `refused`. A `page-only` action may be asked as practice after a counting
  attempt, but never counts, for the reason given in `a-trace-described-action`'s generator. A
  `save-new` action does count here: in a real app the learner applies the path without a
  description written around it, and the key comes from the app's own code. Hold fixed: the parts
  list is given before the action; the path is written before any developer tools or server output
  are looked at; the key comes from the code and the server's output, never from the learner's
  account.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "which part hears about the click first?", and the attempt is recorded `unaided: no`.
- **doesn't show:** the key rests on the tutor's reading of code the learner never sees, so a
  mistaken reading passes or fails the learner wrongly. The parts list tells the learner which
  parts exist, so a pass doesn't show they could have found that out themselves. Two things the
  learner can't see (whether the dev server passes requests on, and whether the page asks for the
  list again after a change) are never ruled on, so a pass shows nothing about either. Because of
  that, and because an action that stays in the page never counts, the clause about naming no part
  the action doesn't go through is examined here only weakly, through a stop the learner invents
  (such as "the API" as a stop of its own). `a-trace-described-action` examines it through the dev
  server. Which kinds of action come up
  depends on what the app has, and a small app may offer no `refused` case at all.
- **offer as:** the real thing: an action in the app your agent actually built, and afterwards you
  watch its requests and its server log to see how close you were. Only possible once the lab has
  added a server and a database, which makes it the natural candidate for review visits.
  `a-trace-described-action` is the one to take now.

### `a-hunt-planted-forgetting`

- **serves:** `c-check-persistence`
- **supports:** deepen
- **artifact:** no external source. The scratch list app from `a-watch-list-app-requests`, built to
  that entry's specification (or reused if it's still there), run by the tutor in five versions
  labeled A to E in an order the tutor draws at random. The page looks the same in all five; each
  keeps the items somewhere different:
  - `page`: only in the page's memory. The server runs, but the page never sends it the items. Gone
    after a reload.
  - `browser`: only in that browser's own storage (localStorage). Survives a reload and a server
    restart; absent in another browser or a private window.
  - `server-memory`: sent to the server, which keeps them in its memory and not in the database.
    Survives a reload and shows in another browser; gone after the server restarts.
  - `rebuilt-table`: in the database, but the server throws the table away and makes a new, empty
    one whenever the table's columns change. Survives everything until the "agent" changes the
    tables.
  - `kept`: in the database, and a change to the columns keeps the rows.
  35 to 45 minutes, plus the tutor's setup.
- **verified:** 2026-09-21
- **learner does:** for each version, when the tutor, speaking as the agent, says "Your items are
  now saved", adds three items of their own, then tries whatever they think will show whether the
  items are really kept, one step at a time, saying beforehand what they expect to see if they are.
  They may use the browser however they like and ask the agent to do anything except two things:
  tell them where or whether the items are saved, and show them code or what's inside the
  database. Everything has to be found from the running app, and which steps to try is theirs to
  decide. After each version, says whether it really keeps the items and which step showed it. At the end, says where each of A to E was keeping the items, then writes the shortest list of
  steps that would have caught every version that forgets, in the order they would do them.
- **tutor role:** socratic questioner
- **tutor does:** builds the five versions before the session so that switching is quick, and
  makes each one start empty: every version has its own scratch folder, its own database file, and
  its own page and server ports, so neither the database nor the browser's storage (which belongs
  to one address) carries items from one version into the next. Never says which is which until
  the learner has decided. Plays the agent literally: restarts the server when asked, and
  nothing more; when asked to change the tables, adds a column and restarts the server, which in
  `rebuilt-table` loses the rows and in `kept` doesn't. Answers any "is it saved?" with the same
  line every time: "Your items are now saved." Gives no list of steps to try. When the learner is
  stuck, asks a near-miss question rather than naming a step ("you reloaded and they were still
  there; would they be there in a browser that has never opened this app?"); those questions, not a
  list, are how a move the learner hasn't thought of comes in. After each version, says in one or two sentences where
  it kept the items. At the end, checks the learner's shortest list against the four versions that
  forget and asks about any it would miss, and points out that `rebuilt-table` survived every step
  except the change of tables, so a list without that step would have passed it. Stops everything
  at the end.
- **done when:** the learner has placed all five versions, and their shortest list would catch
  `page`, `browser`, `server-memory` and `rebuilt-table`. No `checks`: the tutor chose the versions
  and asked questions throughout, and the list was written after the learner had watched each kind
  of forgetting happen.
- **offer as:** hands-on: you try to catch out five versions of the same small app, four of which
  only look as if they save. The only candidate where you see each kind of forgetting happen for
  yourself. The longest (35 to 45 minutes plus setup), and it needs a live session in which the
  tutor can build and run the app. `a-judge-persistence-plans` needs nothing running.

### `a-judge-persistence-plans`

- **serves:** `c-check-persistence`
- **supports:** deepen
- **artifact:** `tasks/judge-persistence-plans.md`, written for this topic: an agent's message
  saying a small habit-tracking app now saves habits and daily ticks; the four ways an app can look
  as if it saves when it doesn't; ten plans that students wrote for finding out; and a key. Two
  plans catch all four. The others fall short in different ways (three of them catch only the page,
  each for a different reason), including one that only asks the agent, one that uses a new tab
  (which is only a reload), one that changes the tables before saving anything, and one that
  restarts the server but looks again in the same browser. 15 to 20 minutes. No app or browser
  needed.
- **learner does:** for each of the ten plans, marks which of the four forgetful apps it would
  catch. Then says what the plans that catch all four have in common. Then writes their own plan for
  the same message, as short as they can make it while still catching all four.
- **tutor role:** critic
- **tutor does:** shows everything above the key and nothing in it. Takes all ten answers before
  commenting on any. On each answer that disagrees with the key, asks the learner to walk through
  what that plan would show on that app, step by step, rather than stating the answer. Makes sure
  `p7` and `p8` are compared whatever the learner answered, since they differ only in whether
  something was saved before the tables changed. Makes sure `p5` is discussed: restarting the server
  is right, but looking again in the same browser lets an app that keeps things in the browser
  through. Reads the learner's own plan literally against each of the four.
- **done when:** the learner's account of what the complete plans share covers looking from a page
  that has never seen the data, looking after a server restart, and looking after a change to the
  tables for something saved before it, with nothing resting on the agent's word; and their own
  plan catches all four. No `checks`: the four ways were set out for them and two complete plans
  were in front of them.
- **offer as:** no app, 15 to 20 minutes, and about what makes a check thorough rather than how to
  carry out each step. Ten plans for the same app and the same message, so the only thing that
  changes is the steps, and what those steps would let through; three plans that each catch only
  the page show three different ways to fall short. Pick `a-hunt-planted-forgetting` to watch the
  forgetting happen instead.

### `a-read-prisma-migrations`

- **serves:** `c-check-persistence`
- **supports:** deepen
- **artifact:** Prisma's Data Guide, "What are database migrations?",
  https://www.prisma.io/dataguide/types/relational/what-are-database-migrations (free, no account;
  Prisma makes database tools, and the page carries an advert for its hosted database in the middle
  and a pitch at the end). Read: Introduction (about 115 words); What are database migrations?
  (about 195 words, skipping the Prisma Postgres advert inside it); from What are some
  disadvantages of migration tools?, the first two paragraphs, ending "preserved or transformed
  correctly" (about 95 words); from What to keep in mind with state based migrations, the first
  paragraph, ending "intervene to prevent data loss" (about 90 words); and from During development,
  the paragraph beginning "In general, it's best practice to be conservative" (about 75 words).
  About 570 words: 5 minutes of reading inside a 20-minute session. The page has no code and no
  commands anywhere. It is written for developers, in general terms; its one concrete case is a tool
  that renames a table by deleting it and making a new one. Words in place: database, schema,
  migration (also "schema migrations" and "database schema migrations"), table, column, and data
  loss.
- **verified:** 2026-09-21
- **learner does:** reads the five pieces, then writes three things in their own words: how an app
  can lose what it had already saved when its tables change, even though nothing is wrong with the
  database itself; one example in an app like theirs (their agent adds a due date to each to-do
  after a week of use); and the step they would add to a check of whether an app really keeps
  things, saying what they would save, when the tables would change (they ask, or they wait for the
  agent's next change), and when and where they would look.
- **tutor role:** socratic questioner
- **tutor does:** stays out of the reading. On the example, asks what exactly would be gone and
  what would still be there (the table and its new column would be; the week's to-dos might not).
  On the step, asks near-miss questions: "you'd add a to-do after the change and check it's there;
  does that show the old ones survived?"; "you'd look with the page still open from before; could
  that page be showing its own copy?" Ties it to the words: a migration is a change to the schema
  once data is already in it, not a move to a different database.
- **done when:** the step the learner wrote saves something before the tables change, and looks for
  that same thing, from a freshly loaded page, after they change. No `checks`: this covers one of
  the four cases the criterion names.
- **offer as:** narrow, and only for the case the other routes make hardest to believe: that an app
  can lose what it had saved when its agent changes its tables. About 570 words of developer prose,
  20 minutes, nothing to run. Take it if that case is the one that isn't landing.

### `a-plan-persistence-check`

- **serves:** `c-check-persistence`
- **supports:** attempt
- **checks:** `c-check-persistence`
- **artifact:** no external source. A made-up app and an agent's message about it, written by the
  tutor per the generator below. 10 minutes.
- **verified:** 2026-09-21
- **learner does:** reads the app's description and the agent's message, then writes alone, as a
  list, what they would do to find out whether the thing the agent says is saved really is kept.
  The plan may include asking the agent to restart the server, or to change the tables; it may not
  rest on the agent's word for what any step shows. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and, before showing anything, writes into
  the record the four apps the plan has to catch (one that keeps the thing only in the open page,
  one only in that browser, one only until the server restarts, and one that loses what was already
  saved when its tables change) and the trap in the message, if any. Shows the description and the
  message. Waits, writing down any help word for word. Sends the adjudicator the description, the
  message, the trap, the plan verbatim and the help. After the ruling, tells the learner which of the
  four the plan would miss, if any, and why. Labels the attempt
  `a-plan-persistence-check/<saved>-<trap>`.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed: a small app on the learner's laptop with a page, a server and a SQL
  database, described in three to five sentences in a user's words, with no logins and nothing
  deployed. The description says the thing should be kept for good, the way a real app keeps your
  data. The agent's message is two to five sentences in a coding agent's voice, says what it built,
  and says the thing is now saved. The learner never sees the app; the plan is judged on whether,
  followed as written, it would catch each of the four.
  What varies: the app (a different one each attempt); what is claimed saved: `items` (things the
  user adds), `changes` (ticks, edits or ratings on existing things), `setting` (a choice the
  description says should stay, such as the order a list is sorted in, or a chosen color theme),
  or `draft` (something half-written that the description says is kept); and the trap in the
  message:
  - `plain`: none.
  - `named-db`: the message names the database and its file ("saved in a SQLite database at
    data/app.db"), inviting the learner to stop there.
  - `self-tested`: the agent says it already checked one case ("I reloaded and it's still there",
    or "I restarted the server and it came back"). A plan that skips that case because the agent
    checked it misses it.
  - `sample-data`: the agent says it added three sample items that are put in whenever the server
    starts, so the app is never empty. A plan that looks only for whether there are items after a
    restart can't tell kept items from fresh samples; it has to look for something the learner
    added.
  - `next-change`: the agent says what it will change next ("next I'll add a category to each
    habit"), which makes the table case concrete, and tempts a plan that checks only things added
    after the change.
  Difficulty: Easy is `items` with `plain`. Medium is `changes` or `setting` with `plain`, or
  `items` with `named-db` or `next-change`. Hard is `self-tested` or `sample-data` with anything
  saved, or `draft` with any trap. An attempt meant to count runs at Medium or Hard; Easy is for the
  worked example and for a retry with help after a miss. Across attempts and review visits, cover
  `self-tested`, `sample-data`, and a `setting` or `draft` instance at least once each, reading the
  labels `served.mjs` returns.
- **worked example:** work one Easy instance aloud by asking, one at a time, where else the app
  could be keeping the thing besides the database (in the open page, in this browser, in the
  server's memory, in a table that gets rebuilt), and for each, what you would do to catch it and
  in what order. At the first level of help on a real attempt, ask only "if the app weren't really
  saving it, where else could it be keeping it?"
- **doesn't show:** it is a plan, not a check carried out, so whether the learner can do each step
  (open a private window, get the agent to restart the server, pick out their own items among
  sample ones) is not examined. Only the four ways the criterion names are examined, so other ways
  to lose data (a database file the agent deletes and remakes by hand, data that doesn't survive
  deployment) are not. The message is handed to the learner, so a pass shows nothing about noticing
  an agent's claim in the middle of work, and the learner knows a check is on, so the plan may be
  more thorough than what they would do unprompted.
- **offer as:** the check that's available now, before your own app has a database: a made-up app
  and an agent's message, 10 minutes, nothing to run. The tutor picks the trap, so the harder
  messages (an agent that says it already tested, sample items that hide a loss) actually come up.
  `a-check-own-app-saves` is the same capability on a real message from your own agent.

### `a-check-own-app-saves`

- **serves:** `c-check-persistence`
- **supports:** attempt
- **checks:** `c-check-persistence`
- **artifact:** no external source. The learner's own app and a real message from their own agent,
  in the lab after this topic or in Problem Set 2, saying that something is now saved. 10 minutes
  to write the plan, plus however long carrying it out takes.
- **verified:** 2026-09-21
- **learner does:** when their agent says something in their app is now saved, and before asking
  the agent anything more about it, writes alone, in a note, what they will do to find out whether
  it is really kept. Then carries out the plan, asking the agent to restart the server or to change
  the tables if the plan says so, and writes next to each step what they saw. Brings the tutor the agent's message, the
  note as first written, and what they saw. No tutor is there while this happens.
- **tutor role:** none
- **tutor does:** when first offering this activity, tells the learner to write the note before
  doing anything else, and to write at its top anything they looked at for help while writing it.
  Afterwards, confirms with the learner that the note came before the steps, and sends the
  adjudicator the agent's message, the note as first written, any help noted, and, marked as what
  happened afterwards, what the learner saw. If the app did forget something, tells the learner
  which step caught it and offers to help them describe it to their agent. Labels the attempt
  `a-check-own-app-saves/<what was claimed saved>`.
- **done when:** criterion met with no help. The plan is judged as first written, not on what the
  app turned out to do.
- **kind:** generator
- **generator:** the material is whatever the learner's own agent says it saves, so no two
  instances match and nobody sets the difficulty. Hold fixed: the note is written before any step is
  carried out and before the learner asks the agent anything more about how the saving works; the
  agent's message is kept word for word. No instance if the learner had already asked the agent how
  it saves before writing the note, since the answer shapes the plan, or if the note was written
  after any step was carried out. A note that says only "ask the agent" is an instance, and a miss.
  A plain message about added items counts here, although `a-plan-persistence-check` keeps its Easy
  instances out of counting: the plan has to catch all four whatever the message says, and the
  difficulty here is the real situation (the learner's own app, in the middle of work, with nobody
  prompting a check), not the wording of the message.
- **worked example:** no tutor is present, so nobody offers one. If the learner stalls, they may
  open `tasks/judge-persistence-plans.md` themselves and look at `p9` or `p10`; they write at the
  top of the note that they did, and the attempt is recorded `unaided: no`.
- **doesn't show:** that the note came before the steps rests on the learner's say-so. A plan that
  waits for the agent's next change to the tables, rather than asking for one, may be judged
  before that step has been carried out, so what the learner saw may stop short of it; the plan is
  still judged as written. Whether the app really had
  a fault is luck, and the plan is judged the same either way. And the messages that come up are
  whatever the agent happens to say, so traps like sample items or an agent that says it already
  tested may never appear.
- **offer as:** the real thing: your own agent tells you something is saved, and you find out
  before you believe it. Only possible once your agent is adding a database, which makes it the
  natural candidate for the lab and for review visits. `a-plan-persistence-check` is the one to take
  now.

### `a-sort-missing-claims`

- **serves:** `c-review-schema`
- **supports:** deepen
- **artifact:** `tasks/sort-missing-claims.md`, written for this topic: a description of Potluck,
  an app for planning shared dinners; the three tables its agent proposed, each with its columns;
  ten claims classmates made about what is missing; and a key. Two claims are right. Eight are
  wrong, each for its own reason: a count and a warning the app can work out, something held under
  a different name, names held where they're used, what's typed in a search box, a column that's
  already there, something the app was never asked to keep, and an average that can be worked out,
  but only from something that really is missing and that no claim names. 20 to 25 minutes. No app
  needed.
- **verified:** 2026-09-21
- **learner does:** reads the description and the tables. For each claim, says whether it's right
  (the app needs to remember this and no table holds it) or wrong, and if wrong, why. Then says
  whether anything the app has to remember is missing that none of the claims names. Then states the
  rule they sorted by, in one or two sentences.
- **tutor role:** critic
- **tutor does:** shows everything above the key and nothing in it. Takes all ten answers, the
  answer about anything unnamed, and the rule before commenting on any. On each answer that
  disagrees with the key, asks the learner where exactly that thing would be written down next
  week, or how the app would work it out, rather than giving the verdict. Makes sure `k8` is
  discussed whatever the learner answered: the average can be worked out, but only from the stars
  people gave, and nothing holds those. If the learner doesn't find the ratings unaided, asks
  "where would Potluck keep the three stars Sam gave the lasagne?" Makes sure `k6` is discussed as a
  question of how the tables are organized, not of whether they hold what's needed.
- **done when:** the learner's rule covers listing what the app must still know later; counting
  something as missing only if no column holds it, under any name; leaving out what can be worked
  out from what is kept, what nobody expects back, and what the app was never asked to keep; and not
  judging how the tables are arranged. And they found the ratings. No `checks`: sorting other
  people's claims is not finding what's missing yourself, and two of the three missing things were
  named for them.
- **offer as:** examples before procedure, and the quickest route: 20 to 25 minutes, one app,
  nothing to run. Most of the claims are wrong in the ways careful reviewers usually go wrong
  (calling a count missing, not seeing that something is saved under another name), which is the
  half of the goal about not naming what isn't missing. Pick `a-narrated-table-review` to watch the
  procedure first.

### `a-narrated-table-review`

- **serves:** `c-review-schema`
- **supports:** orient, deepen
- **artifact:** no external source. A made-up app and an agent's proposed tables, built by the
  tutor per `a-review-proposed-tables`'s generator at Medium, with one missing thing of kind `link`
  and at least a `computed` and a `renamed` distractor. 15 minutes.
- **verified:** 2026-09-21
- **learner does:** watches the tutor review the proposal out loud, and interrupts whenever they
  disagree or can't follow. Before the tutor reaches its verdict, writes down their own guess at
  what's missing. At the end, states the tutor's procedure in their own words, then carries out its
  last step themselves on one item the tutor names.
- **tutor role:** explainer
- **tutor does:** builds the instance and its key first. Works in three passes, out loud. First,
  reads the description one sentence at a time and writes the list of everything the app must still
  know next week, saying for each sentence why it adds something or doesn't (a count can be worked
  out; the text in a search box isn't expected back). Second, takes each thing on the list and
  points to the column that holds it, accepting a different name when it means the same thing.
  Third, checks what's left over: is it really something to keep, or can it be worked out from what
  is kept? Makes two false starts on purpose, visibly: in the first pass calls the count "missing",
  then withdraws it in the third; in the second pass matches everything and nearly declares nothing
  missing, then asks the one question that exposes this instance's missing link in its own terms
  (in an app with several lists, "if two lists each had an item called milk, could the app tell
  which list each was on?"; in an app with comments on dinners, "could it tell which dinner's page
  a comment goes on?") and finds it. Gives the answer in the form the checks want: the list, each
  thing with its column or "missing", then a one-line verdict. Compares it with the learner's
  written guess. For the
  last step, names one item (a computed value or a truly missing fact) and asks the learner which
  it is and why.
- **done when:** the learner can state the three passes in their own words and gets the leftover
  check right on the item named: truly missing, or something that can be worked out, and why. No
  `checks`: the tutor did the review.
- **offer as:** watch it done on a fresh example, with the false starts left in: the only route
  that shows the procedure and why each pass is there. 15 minutes, nothing to run, needs a live
  session. `a-sort-missing-claims` gives you the mistakes to sort instead.

### `a-list-own-app-memory`

- **serves:** `c-review-schema`
- **supports:** deepen
- **artifact:** no external source. The learner's own app with state from the lab before this topic
  (the one the next lab adds a server and a database to), running in their browser; or, if it isn't
  finished, the learner's own account of what it is meant to do. 20 minutes.
- **verified:** 2026-09-21
- **learner does:** uses their app, screen by screen (or talks it through, if it isn't finished),
  and writes a list of everything it would need to still know next week, after the laptop has been
  switched off, once it has a database. One line each: what it is, and which screen shows it. Then
  marks each line: kept (it has to be saved), worked out (the app can compute it from kept things),
  or fine to lose. Then groups the kept lines into kinds of things, in plain words, as a first guess
  at what the tables will be. Keeps the list for the lab, to check their agent's proposal against.
- **tutor role:** socratic questioner
- **tutor does:** proposes nothing. Asks near-miss questions instead: "you marked your streak as
  kept; if the app knows which days you checked in, could it work the streak out?"; "does it need
  to remember the order you dragged things into?"; "you have two lists; does each item need to know
  which list it's on?" Never opens the app's code. Keeps logins and sharing out of it: those belong
  to Problem Set 3.
- **done when:** every screen of the app is covered, every line is marked, and the learner can say
  why for each mark. No `checks`: there is no proposal yet to check.
- **offer as:** on your own app, and the most useful one before the lab: you arrive with the list
  you'll check your agent's tables against. 20 minutes. Needs your app with state, or a clear idea
  of it.

### `a-review-proposed-tables`

- **serves:** `c-review-schema`
- **supports:** attempt
- **checks:** `c-review-schema`
- **artifact:** no external source. A made-up app and the tables its agent proposes, written by the
  tutor per the generator below. 10 minutes.
- **verified:** 2026-09-21
- **learner does:** reads the description and the proposed tables, then writes alone a list of
  everything the description asks the app to keep, each with the table and column that holds it,
  or "missing"; then a one-line verdict: what is missing, or that nothing is. Hands both to the
  tutor.
- **tutor role:** none
- **tutor does:** builds the instance and writes the key into the record before showing anything:
  every thing the app must remember and the column that holds it, or "missing"; and every
  distractor, with why it isn't missing. Shows the description and the tables. Waits, writing down
  any help word for word. Sends the adjudicator the description, the tables, the key, the list and
  verdict verbatim, and the help. After the ruling, tells the learner what they missed, named
  wrongly, or pointed to the wrong place. Labels the attempt
  `a-review-proposed-tables/<kinds missing, or none>`.
- **done when:** criterion met with no help, on a Medium or Hard instance. A "nothing is missing"
  verdict meets it only when the list is there and points each thing the app must keep to the
  column that really holds it; the verdict on its own does not.
- **kind:** generator
- **generator:** fixed: the description is five to eight sentences in a user's words saying what
  people do and see, and ends with a sentence that settles what must last ("When anyone opens the
  app next week, every ... is still there"). No logins or accounts; people type their names where
  needed. The tables are listed the way an agent lists them in plain words: each table's name, then
  its columns by name, with an `id` column, a `created_at` where natural, and a `<thing>_id` column
  where one table points at another; no data types and no SQL. Two to four tables. How well the
  tables are organized is never the answer.
  What varies: the app (a different one each attempt: book club, recipe box, habit tracker, class
  project board, movie-night voting, workout log, lost-and-found board, or another); how many things
  are missing (none, one or two); the kind of each missing thing:
  - `fact`: one fact about a thing has no column (a due date, a vegetarian tick, a price).
  - `link`: nothing records which thing another belongs to (which list an item is on, which dinner
    a comment is on).
  - `many`: a kind of thing the app keeps several of for each item has nowhere to go (ratings from
    several people, several photos, the history of changes when the description says it's shown).
  - `state`: something that changes and has to be remembered has no column (done, archived, the
    order a user dragged the items into).
  and the distractors, at least two per instance, from:
  - `computed`: a count, a total, an average or a streak that the kept columns determine.
  - `transient`: what's typed in a search box, which tab is open, a filter that resets.
  - `renamed`: held under a different name (`finished` for done, `who` for the person).
  - `elsewhere`: held in a different table from the obvious one.
  - `unasked`: plausible, but the description never asks the app to keep it. It sits next to
    something the description does ask for and stops short of it (a date asked for without a time,
    a name without a photo), so that someone reading quickly expects it.
  A `computed` distractor must really be computable from the proposed columns (a streak needs the
  dates of check-ins, not just a count), and a `many` omission must not fit in the given columns
  without changing what they mean.
  Difficulty: Easy is two tables, one missing `fact`, with `renamed` and `transient` distractors.
  Medium is three tables with one missing `link`, `many` or `state`, or with nothing missing, and a
  `computed` among the distractors. Hard is three or four tables with two missing things of
  different kinds, or nothing missing with four distractors including `computed` and `elsewhere`.
  An attempt meant to count runs at Medium or Hard; Easy is for the worked example and for a retry
  with help after a miss. One of the learner's first three counting attempts has nothing missing.
  Across attempts and review visits, cover `link`, `many`, `state` and a nothing-missing instance at
  least once each, reading the labels `served.mjs` returns.
- **worked example:** work one Easy instance aloud in three passes: list what the app must still
  know next week, sentence by sentence; point each to its column, accepting other names; check that
  what's left over can't be worked out. At the first level of help on a real attempt, ask only "what
  would the app need to show you next week, and where would each of those be written down?"
- **doesn't show:** the description states outright what must last, so a pass doesn't show the
  learner could settle that for an app whose purpose is vaguer, as a real one often is. The
  proposals are in plain words, so a pass says nothing about an agent's proposal given as code.
  Each missing thing is either clearly held or clearly not, so borderline cases (a column that could
  hold it at a stretch) are never examined. The list is judged at the level of the description's
  sentences, so a pass shows the learner can match what an app must keep to where it is kept, not
  that they would think of something the description never mentions. And the learner knows a check
  is on and that none, one or two things may be missing.
- **offer as:** available now, before your agent proposes anything: a made-up app and its tables,
  10 minutes, nothing to run. The tutor picks what's missing, so the hard kinds (a missing link
  between tables, several people's ratings with nowhere to go) and the case where nothing is missing
  actually come up. `a-review-own-agent-tables` is the same capability on your own agent's proposal.

### `a-review-own-agent-tables`

- **serves:** `c-review-schema`
- **supports:** attempt
- **checks:** `c-review-schema`
- **artifact:** no external source. The tables the learner's own agent proposes for their own app,
  in the lab after this topic or in Problem Set 2, before it builds the database; and whatever
  settles what the app has to remember: the learner's description of the app as given to the agent
  or, where there wasn't one (as in the lab, where the agent adds a database to an app the learner
  already has, working from the app itself), the running app. 10 to 15 minutes, plus the tutor's
  time afterwards.
- **learner does:** when their agent proposes the tables it will build, and before approving them or
  asking it anything about them, writes alone, in a note, a list of everything the app will need to
  remember, each with the table and column that holds it, or "missing"; then a one-line verdict:
  what is missing, or that nothing is. If the agent gave its proposal as code, first asks it to list
  the tables and their columns in plain words, which doesn't count as help. Then brings the tutor the
  proposal word for word, the note as first written, and either the description they gave the agent
  or, if there wasn't one, the app itself, running. No tutor is there while this happens.
- **tutor role:** none
- **tutor does:** reads what settles the app's needs, and the proposal, first, and writes the key
  into the record (everything the app must remember, where each is held, and what is missing)
  before reading the learner's note, so the note can't shape the key. From a description, the key
  follows its sentences. From a running app, the tutor reads its code (the learner doesn't see it)
  and, if it has a headless browser, goes through its screens, as `a-trace-own-app-action` does;
  the key lists what the app shows or lets people change that it would still need next week. Where neither settles whether
  something must be kept, the key says so and the adjudicator is told; a learner is not failed for
  listing, or not listing, something left open. Sends the adjudicator what settled the app's needs
  (the description, or the tutor's account of the app's screens), the proposal, the key, the note
  as first written and any help the learner noted. After the ruling, tells the learner what, if
  anything, to raise with their agent before it builds. Labels the attempt
  `a-review-own-agent-tables/<app>`.
- **done when:** criterion met with no help, on the note as first written. A "nothing is missing"
  verdict meets it only when the list is there and points each thing the app must keep to the
  column that really holds it; the verdict on its own does not.
- **kind:** generator
- **generator:** the material is whatever the learner's agent proposes for whatever the learner is
  building, so nobody sets the difficulty. Hold fixed: the note is written before the learner
  replies to the proposal; the proposal, and the description if there was one, are kept word for
  word; the key is written before the note is read. No instance if the proposal came after the
  learner had already told the agent what was missing, or if neither a description nor the running
  app settles what the app has to remember. A proposal with nothing missing is a fair instance,
  since the list still has to point everything to where it is kept.
- **worked example:** no tutor is present, so nobody offers one. If the learner stalls, they may
  reread `tasks/sort-missing-claims.md` above its key; they write at the top of the note that they
  did, and the attempt is recorded `unaided: no`.
- **doesn't show:** the key rests on the tutor's reading of a description the learner wrote, or of
  an app whose code the learner never saw, and either may leave open what the app must keep. Real
  proposals often miss nothing and have no planted distractors, so a pass often rests on the list
  alone, with no omission to find and nothing tempting to name wrongly. Which kinds of omission come
  up is chance, and a learner may pass here without ever meeting a missing link or a missing kind of
  thing.
- **offer as:** the real thing, at the moment this topic's depth is about: your agent proposes
  tables and you check them before approving. Only possible once your agent is adding a database,
  in the lab or in Problem Set 2. `a-review-proposed-tables` is the one to take now.

### `a-w-backend`

- **origin:** generated
- **serves:** `w-backend`
- **checks:** `w-backend`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-request`

- **origin:** generated
- **serves:** `w-request`
- **checks:** `w-request`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-endpoint`

- **origin:** generated
- **serves:** `w-endpoint`
- **checks:** `w-endpoint`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-api`

- **origin:** generated
- **serves:** `w-api`
- **checks:** `w-api`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-status-code`

- **origin:** generated
- **serves:** `w-status-code`
- **checks:** `w-status-code`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-localhost`

- **origin:** generated
- **serves:** `w-localhost`
- **checks:** `w-localhost`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-server-log`

- **origin:** generated
- **serves:** `w-server-log`
- **checks:** `w-server-log`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-database`

- **origin:** generated
- **serves:** `w-database`
- **checks:** `w-database`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-sql`

- **origin:** generated
- **serves:** `w-sql`
- **checks:** `w-sql`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-table`

- **origin:** generated
- **serves:** `w-table`
- **checks:** `w-table`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-schema`

- **origin:** generated
- **serves:** `w-schema`
- **checks:** `w-schema`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-migration`

- **origin:** generated
- **serves:** `w-migration`
- **checks:** `w-migration`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-fixture`

- **origin:** generated
- **serves:** `w-fixture`
- **checks:** `w-fixture`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
