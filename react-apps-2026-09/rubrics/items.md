# Rubrics: The words of react apps

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-define-component

- **type:** free
- **goal:** w-component
- **move:** DEFINE
- **answer:** a component is one of the pieces a React screen is assembled from: a named piece of
  the app that produces a part of what you see, such as the task list, one task's row, or the Add
  box. A screen is built out of several of them, and the same one can be used in more than one
  place.
- **credit:** full credit for saying it is a piece of the screen, a part of the app that produces
  part of what you see, and that screens are assembled from them. Full credit for "a reusable piece
  of the interface". Half credit for "a file" or "a function" alone, which says how a component is
  written rather than what it produces. Do not accept "a page" or "a screen", which is the whole
  thing a component is a piece of, and do not accept "a feature of the app".

### q-component-vs-page

- **type:** free
- **goal:** w-component
- **move:** DISTINGUISH
- **answer:** a page is the whole of what is on screen at one address; a component is one of the
  pieces that whole is assembled from. One page is built out of several components (a heading, the
  Add box, one row per task), and one component can turn up on more than one page.
- **credit:** full credit for the containment: a page is the whole screen and components are the
  pieces it is assembled from, so a page holds many components. Full credit for the reuse version:
  the same component can appear on several pages. Half credit for "a component is smaller", or for
  "a page has its own address and a component doesn't", with nothing about one being built out of
  the other. Do not accept "a component is the code and a page is what the user sees", and do not
  accept an answer in which each page is one component.

### q-two-screens-two-components

- **type:** free
- **goal:** w-component
- **move:** CATCH
- **answer:** the number of screens says nothing about the number of components. Each screen is
  itself assembled from several components, and one component can be used on both screens, so two
  screens is a claim about what the app shows rather than about how it is built.
- **credit:** full credit for saying one screen is built from several components, so two screens
  does not mean two components. Full credit for the reuse half alone: the same component can appear
  on both screens. Do not accept a different quibble as the error: that the app should have more
  screens, that they would have to open the files to count, or that the agent decides how many
  components there are.

### q-define-state

- **type:** free
- **goal:** w-state
- **move:** DEFINE
- **answer:** state is what the app is holding at this moment while it runs: the count so far, the
  text typed in the box, which tasks are ticked. What is on screen is worked out from it, and it
  changes as you use the app.
- **credit:** full credit for saying it is what the app is currently holding or remembering while
  it runs, with what is shown following from it. Full credit for "the data the app has right now,
  which changes as you use it". Half credit for "the app's data" with nothing about it being
  current or held while running. Do not accept "where the app saves things" or "the database",
  which is storage rather than state, and do not accept "the condition the app is in" with no
  example or no mention of what it holds.

### q-state-vs-database

- **type:** free
- **goal:** w-state
- **move:** DISTINGUISH
- **answer:** state is what the running app is holding at this moment, and it goes when the page is
  reloaded or closed unless something wrote it down. Data in a database has been written outside
  the running app, so it is still there next time, from another tab or another machine. An app
  typically loads state from the database when it starts and writes changes back.
- **credit:** full credit for the difference that matters: state lasts only as long as the page is
  running, so a reload starts it over, while saved data outlives the page and is there next time.
  Half credit for "one is temporary and one is permanent" with nothing tying the temporary one to
  the running page or the reload. Do not accept "state is in the browser and a database is on a
  server" on its own, and do not accept a difference of size or speed.

### q-list-only-in-state

- **type:** mcq
- **goal:** w-state
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 treats state as storage, which is exactly the confusion the word is against. 2 puts
  the tasks on the dev server; they are in the page, in your browser. 4 says they are already gone,
  but they are on screen and held by the app until the page is reloaded.

### q-define-render

- **type:** free
- **goal:** w-render
- **move:** DEFINE
- **answer:** rendering is a component working out what its part of the page should look like now
  and putting that on the screen. It happens again whenever what it shows changes, such as the
  count going up after a click, so the screen keeps matching what the app is holding.
- **credit:** full credit for saying a component produces what appears on the screen, its own part
  of the page, and that it happens again when what it shows changes. Half credit for "it shows
  something on the screen" with nothing about the component producing its own part, or nothing
  about it happening again. Do not accept "the page loads" or "the browser displays the page",
  which is the page arriving rather than a component producing its part.

### q-render-vs-reload

- **type:** free
- **goal:** w-render
- **move:** DISTINGUISH
- **answer:** a render happens inside the app that is already running: one component works out and
  puts up its own part of the screen, and everything the app is holding stays. A reload throws the
  whole page away, fetches the app again and starts it from the beginning, so what the app was
  holding is gone.
- **credit:** full credit for both sides: a render updates part of the screen with the app still
  running, while a reload starts the whole page over and loses what the app was holding. Half
  credit for one side stated clearly and the other left vague. Do not accept "a render is faster",
  "a render is automatic and a reload is something you do" on its own, or an answer that treats a
  render as a small reload.

### q-click-reloads-page

- **type:** free
- **goal:** w-render
- **move:** CATCH
- **answer:** clicking Count does not reload the page. The app stays running and the component
  renders again, so only its part of the screen is updated. A reload would fetch the page afresh
  and start the app over, and the count would go back to 0 rather than up by one.
- **credit:** full credit for saying the app keeps running and renders part of the screen again,
  rather than the page being fetched again. Full credit for the evidence version on its own: a
  reload would put the count back to 0. Do not accept a different quibble as the error: that the
  browser showed no spinner, that React is fast, or that the count is saved somewhere.

### q-define-event-handler

- **type:** free
- **goal:** w-event-handler
- **move:** DEFINE
- **answer:** an event handler is the piece of the app connected to a particular thing happening on
  the page, such as a click on Add or a key pressed in the box, and it is what runs when that
  happens. It is where "what should the app do about this click" lives.
- **credit:** full credit for saying it is what the app runs in response to a click, a keystroke or
  similar, attached to a particular thing on the page. No credit for naming it again: "a handler"
  and "an event listener" are other names for the same thing rather than a definition. Do not
  accept "the button" or "the click itself", which are the thing clicked and the thing that
  happens, and do not accept "the code behind the app".

### q-handler-vs-event

- **type:** free
- **goal:** w-event-handler
- **move:** DISTINGUISH
- **answer:** the event is the thing that happened: you clicked, and the browser reports a click on
  that button. The handler is the app's response, the piece connected to that event which runs when
  it arrives. The event is reported whether or not anything is connected to it; the handler is what
  makes something come of it.
- **credit:** full credit for placing them on opposite sides: the event is what happened, reported
  by the browser, and the handler is what the app runs because of it. Full credit for "the event
  happens either way; the handler is what is listening for it". Half credit for an answer that
  describes the handler correctly and says nothing about what the event is. Do not accept "two
  names for the same thing", and do not accept an answer in which the handler is the button.

### q-click-not-happening

- **type:** free
- **goal:** w-event-handler
- **move:** CATCH
- **answer:** the click event happens either way: the browser reports a click on that button
  whether or not the app does anything with it. What is missing is a handler connected to that
  event, so nothing runs when it arrives. Nothing appearing on screen says nothing about whether
  the click reached the page.
- **credit:** full credit for separating the two: the click event happens regardless, and what is
  absent is the handler, with nothing connected to run. Do not accept a different quibble as the
  error: that they should have told the agent sooner, that they should check the console first, or
  that the button's label is wrong.

### q-define-dev-server

- **type:** free
- **goal:** w-dev-server
- **move:** DEFINE
- **answer:** the dev server is the program `npm run dev` starts and leaves running in that
  terminal. It serves your project to the browser at a local address such as
  http://localhost:5173 while you work on it, and it watches your files so that saved changes reach
  the open page. Stop it and that address stops answering.
- **credit:** full credit for saying it is what serves your project to your browser at a local
  address while you are working, and keeps running until it is stopped. Full credit for "the thing
  running in the terminal that makes localhost:5173 work". No credit for "the development server",
  which names it again. Do not accept "the terminal", "npm", or "where the app is hosted online".

### q-closed-terminal-still-up

- **type:** free
- **goal:** w-dev-server
- **move:** CATCH
- **answer:** the tab is showing a page the browser already has; nothing is serving it at this
  moment. With the dev server stopped, a reload has nothing to answer it and the page fails to
  load, and saved changes stop reaching the tab. The dev server is needed for as long as you are
  using the app, not just to start it.
- **credit:** full credit for saying the page on screen is what the browser already loaded, and
  that reloading now would fail because nothing is serving the app. Full credit for the hot reload
  half on its own: with the server stopped, saved changes no longer reach the page. Do not accept a
  different quibble as the error: that they should have stopped it with Ctrl+C, that the app is now
  in production, or that the browser has saved the whole app for good.

### q-dev-server-other-port

- **type:** free
- **goal:** w-dev-server
- **move:** INTERPRET
- **answer:** another dev server was already running on 5173, from an earlier run or another copy
  of the project, so this one took the next free port. The address for the project the agent just
  started is 5174, and whatever is at 5173 is a different server, so anything you check in a tab
  still pointing at 5173 tells you nothing about this app.
- **credit:** full credit for both: this project is now at 5174, and 5173 is something else already
  running, so looking there would be looking at the wrong app. Half credit for the change of
  address alone. No credit for reading it as the app being broken, as the agent having failed to
  start anything, or as the two addresses being two views of the same app.

### q-define-dependency

- **type:** free
- **goal:** w-dependency
- **move:** DEFINE
- **answer:** a dependency is somebody else's code that your project relies on and lists, so that
  `npm install` can fetch it into that project's `node_modules` folder. React itself is one, and
  the project will not run without the ones it lists.
- **credit:** full credit for saying it is outside code the project relies on and lists, fetched
  into the project by npm install. No credit for "a package", which is another name for it. Half
  credit for "something the project needs" with nothing about it being other people's code brought
  into the project. Do not accept "a program you install on your computer", and do not accept a
  file of your own that the project uses.

### q-dependency-vs-installed-program

- **type:** free
- **goal:** w-dependency
- **move:** DISTINGUISH
- **answer:** a program like Chrome is installed once on the machine, belongs to the machine, and
  you open it yourself. A dependency belongs to one project: `npm install` fetches it into that
  project's `node_modules`, another project of yours needs its own copy, and anyone else who gets
  your project runs `npm install` to fetch the same ones for themselves. You never open a
  dependency; the project uses it.
- **credit:** full credit for the per-project point: a dependency is fetched into one project's own
  folder and other projects need their own, while an installed program sits on the machine and is
  available to everything. Half credit for "one is for the project and one is for your computer"
  with nothing following from it. Do not accept a difference of size, "one is code and one is an
  application", or "one is free".

### q-agent-added-dependency

- **type:** free
- **goal:** w-dependency
- **move:** INTERPRET
- **answer:** the project now relies on somebody else's code, date-fns, for formatting dates: it
  has been added to the list of things the project depends on, and `npm install` has fetched it
  into this project's `node_modules` so the app can use it. Nothing was installed on your computer
  as a program, and only this project has it.
- **credit:** full credit for both: the project now depends on an outside package, and it has been
  fetched into this project so the code can use it. Half credit for "it added a library" with
  nothing about it belonging to this project. No credit for reading it as a program installed on
  your laptop, as something for you to open, or as code the agent wrote itself.

### q-define-build

- **type:** free
- **goal:** w-build
- **move:** DEFINE
- **answer:** the build is the version of the project made ready to leave your laptop: `npm run
  build` takes the project's files and writes out a folder, `dist`, of files that a plain web
  server can hand to visitors, which is what you would put online. As a verb, building is running
  that command to produce it.
- **credit:** full credit for saying it is the packaged, ready-to-ship version of the project that
  npm run build produces, the thing you would put online. Full credit for the verb sense: the
  process that turns the project into that. No credit for "a production build", which names it
  again. Do not accept "running the app", "the dev server", or "checking the code for errors".

### q-build-vs-dev-server

- **type:** free
- **goal:** w-build
- **move:** DISTINGUISH
- **answer:** the dev server runs while you work: it serves the project straight from your files,
  and saved changes reach the page as you go. The build is a one-off product: the command takes the
  files as they are at that moment and writes a fixed folder of them, which does not change again
  until you build again, and which is what gets served to real visitors, with no npm or dev server
  needed where it lands.
- **credit:** full credit for the difference that matters: the dev server is live and follows your
  edits, while the build is a fixed snapshot produced on demand and meant to be served somewhere
  else. Half credit for "one is for development and one is for production" with nothing about the
  snapshot or the edits. Do not accept "the build is faster" alone, and do not accept an answer
  that treats npm run build as another way of starting the app while you work.

### q-built-once-updates

- **type:** free
- **goal:** w-build
- **move:** CATCH
- **answer:** the build is a snapshot of the files as they were when the command ran. This
  afternoon's changes are not in `dist`, and will not be until `npm run build` is run again. The
  thing that follows edits as they happen is the dev server, not the build.
- **credit:** full credit for saying dist holds what was there at build time and only another build
  puts later changes into it. Do not accept a different quibble as the error: that they should not
  have built in the morning, that dist should not be committed, or that the agent will rebuild
  without being asked.

### q-define-hot-reload

- **type:** free
- **goal:** w-hot-reload
- **move:** DEFINE
- **answer:** hot reload is the dev server noticing that a project file has been saved and pushing
  that change into the page you already have open, so what you see updates by itself, with nobody
  reloading anything.
- **credit:** full credit for saying a saved change reaches the already open page on its own, with
  nobody reloading. Mentioning the dev server pushing it in is a good addition and is not required.
  No credit for "HMR" or "hot module replacement", which are other names for it. Do not accept "the
  page reloads itself when you save" as the whole answer: the point of the word is that the running
  page is updated in place rather than being fetched and started over.

### q-hot-reload-vs-refresh

- **type:** free
- **goal:** w-hot-reload
- **move:** DISTINGUISH
- **answer:** when you refresh, the browser throws the page away, fetches the app again and starts
  it from the beginning, so whatever the app was holding goes with it. With hot reload the page
  keeps running and only the piece that changed is swapped in, and nobody asked for it: it happens
  because a file was saved.
- **credit:** full credit for both sides: a refresh starts the whole page over and loses what the
  app was holding, while hot reload updates the running page in place when a file is saved. Saying
  that something like a count may survive a hot reload and never survives a refresh is a good
  addition and is not required. Half credit for "one is automatic and one you do yourself" with
  nothing about what happens to the page. Do not accept an answer that makes hot reload a refresh
  the computer does for you.

### q-saved-should-appear

- **type:** free
- **goal:** w-hot-reload
- **move:** INTERPRET
- **answer:** the change is already in the file, and the agent is relying on hot reload to carry it
  into the page you have open, so your tab is where it expects the result to show. If the old
  heading is still there a minute later, what is in doubt is not the change: either nothing is
  connecting your page to a running dev server, or your tab is on a different address or a
  different copy of the project from the one the agent edited.
- **credit:** full credit for both halves: the saved change should reach the open tab by itself, and
  a tab that does not change points at the dev server or at which page the tab is on rather than at
  the change not having been made. Half credit for the first half alone. No credit for reading it
  as an instruction to reload the page, and no credit for concluding that the agent must not have
  saved the file, which is the one thing its message says it did.

### q-define-browser-console

- **type:** free
- **goal:** w-browser-console
- **move:** DEFINE
- **answer:** the browser console is a panel in the browser's developer tools, belonging to one
  tab, where the page reports what happened inside it: errors and warnings from the running app
  turn up there, and you can type a line for that page to run. Someone using the app never sees it
  unless they open the developer tools.
- **credit:** full credit for saying it is where the page's own errors and messages appear, inside
  the browser's developer tools, out of an ordinary user's sight. Full credit for adding that you
  can run a line there. No credit for "the JavaScript console" or "the DevTools console", which
  name it again. Do not accept "the terminal" or "where npm prints things", and do not accept
  "where the errors are" with nothing about it being in the browser.

### q-console-vs-terminal

- **type:** free
- **goal:** w-browser-console
- **move:** DISTINGUISH
- **answer:** the terminal is where the dev server is running, and it reports what that program is
  doing on your laptop: the address it is serving on, files it noticed, its own failures. The
  console belongs to one browser tab and reports what happened inside the page while it ran, which
  is where an error thrown while the app was drawing shows up. They are two different places, and a
  message in one need not appear in the other.
- **credit:** full credit for placing both: the terminal is the dev server's own output on your
  machine, and the console is one tab's report of what happened in the running page. Half credit
  for one placed correctly and the other left vague. Do not accept "one is in the browser and one
  is not" with nothing about what each reports, and do not accept an answer that makes them two
  views of the same messages.

### q-pasted-terminal-for-console

- **type:** free
- **goal:** w-browser-console
- **move:** CATCH
- **answer:** what they copied is the dev server's output, not the console. The console is in the
  browser's developer tools on the app's own tab, and an error thrown while the page was being
  drawn is reported there, which is why a page that goes white often has its only explanation in
  the console and nothing at all in the terminal.
- **credit:** full credit for saying these are two different places, and that the console is in the
  browser's developer tools on the app's tab, so the terminal's output is not what was asked for.
  Do not accept a different quibble as the error: that a screenshot would have been better, that
  they should have reloaded first, or that the agent's request was unclear.

### q-define-hard-reload

- **type:** free
- **goal:** w-hard-reload
- **move:** DEFINE
- **answer:** a hard reload is a reload in which the browser is told not to use the copies of the
  app's files it kept from last time, and to fetch them again. It is what you do when the page may
  be showing you an old version of the app rather than the one being served now.
- **credit:** full credit for saying it reloads without using what the browser kept from before,
  fetching the files again instead of reusing saved copies. No credit for "a hard refresh" or "a
  force reload", which name it again. Half credit for "a stronger reload" or "it clears the cache"
  with nothing about the page's files being fetched again. Do not accept "it restarts the app",
  which an ordinary reload does too.

### q-hard-reload-vs-reload

- **type:** free
- **goal:** w-hard-reload
- **move:** DISTINGUISH
- **answer:** both throw the page away and start it again. An ordinary reload may reuse files the
  browser saved from last time, so an old version of the app can come straight back up. A hard
  reload tells the browser not to trust those and to fetch the app's files again, so what you get
  is what is being served now.
- **credit:** full credit for the difference that matters: an ordinary reload may reuse the
  browser's saved copies, and a hard reload fetches the files again. Half credit for "a hard reload
  is more thorough" with nothing about the saved copies. Do not accept a difference of degree, the
  keyboard shortcut alone, or an answer in which a hard reload clears your data or logs you out.

### q-hard-reload-looked-same

- **type:** free
- **goal:** w-hard-reload
- **move:** CATCH
- **answer:** looking the same is what you would expect here. The difference is in where the page's
  files came from, not in what appears on screen: when nothing the browser kept was out of date,
  an ordinary reload and a hard reload give you the same page. The difference shows only when the
  browser is holding an old copy of the app.
- **credit:** full credit for saying the two look the same whenever the browser had nothing stale,
  because what differs is where the files come from rather than what is shown. Do not accept a
  different quibble as the error: that they pressed the wrong keys, that they should clear the
  cache from the browser's settings instead, or that the starter app is too small to have anything
  saved.

### q-define-routing

- **type:** free
- **goal:** w-routing
- **move:** DEFINE
- **answer:** routing is the link an app keeps between the address in the browser's bar and what is
  on screen: which screen you get is worked out from the address, and moving between screens
  changes the address to match, so an address names a particular screen and can be shared, bookmarked
  or reopened.
- **credit:** full credit for the link in either direction: the address decides which screen the
  app shows, or moving around the app updates the address to match. No credit for "client-side
  routing", which names it again. Half credit for "how you move between pages" with nothing about
  the address. Do not accept "loading a new page from the server", which is what routing in a React
  app replaces.

### q-address-changed-new-page

- **type:** free
- **goal:** w-routing
- **move:** CATCH
- **answer:** the browser did not fetch anything. With routing, the app that is already running
  changes what it shows and updates the address itself, so no new page comes from the server. That
  is why moving between screens is instant and the app keeps what it was holding.
- **credit:** full credit for saying the running app changed the screen and the address itself,
  without the browser fetching a new page from the server. Do not accept a different quibble as the
  error: that the address should have been something else, that the task page might be blank, or
  that they should reload to be sure.

### q-routing-same-page-every-address

- **type:** mcq
- **goal:** w-routing
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 describes a plain server with a file per address, which is what client-side routing
  replaces. 3 goes too far: the server does send the same page for every address, and the app then
  picks a screen from the address, which is the whole point. 4 confuses the server answering with
  the app recognising the address: the page loads either way, and an address the app knows nothing
  about shows you nothing useful.

### q-define-headless-browser

- **type:** free
- **goal:** w-headless-browser
- **move:** DEFINE
- **answer:** a headless browser is a real browser with no window, driven by a program rather than
  by a person. Your agent starts one, through a tool such as Playwright or Puppeteer, to open your
  app's address, click things, read what is on the page and take screenshots, so that it can see
  for itself what the app does.
- **credit:** full credit for saying it is a browser with no visible window that a program, the
  agent, drives, used to load a page and look at it. Half credit for "a browser the agent uses"
  with nothing about there being no window or about it being driven by a program. Do not accept "a
  way for the agent to see your browser tab", which is the confusion the word is against, and do
  not accept the dev server or a screen reader.

### q-headless-vs-your-browser

- **type:** free
- **goal:** w-headless-browser
- **move:** DISTINGUISH
- **answer:** the browser on your laptop is yours: it has a window you look at, your tabs, and
  whatever you are signed in to. The agent's headless browser is a separate browser it starts and
  drives itself, with no window and none of your tabs or sessions. It can open the same address you
  can, but it cannot see what is in your tab, which is why the agent still has to ask you what you
  are seeing.
- **credit:** full credit for both: the headless one is a separate browser the agent starts and
  drives with no window, and it does not have your tabs, your session or your view of the page.
  Half credit for "one has no window" alone. Do not accept "it is a fake browser" or "it cannot run
  the app properly", and do not accept an answer in which the agent's browser is a way of watching
  your screen.

### q-no-headless-browser-here

- **type:** mcq
- **goal:** w-headless-browser
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 makes it a problem only a human could see; the agent simply cannot open the page in
  this session. 3 blames the dev server, which the message says nothing about. 4 has the agent
  seeing your tab, which is the thing a headless browser is not.

### q-links-expire-request

- **type:** free
- **goal:** c-describe-app-bug
- **answer:** someone who never saw it would have to guess most of the steps: which address to
  start from, how to get a link to a task in the first place, what to do with it (open it in a new
  tab, or reload on it), and what "blank" means on screen, which is what would tell them it was
  fixed. The second sentence, about links expiring, is a guess and is not marked as one, so it
  reads as something you saw.
- **credit:** full credit needs both halves: one concrete thing a stranger would still have to
  guess (where to start, the steps, what appeared instead, or how to tell it is fixed) and the
  expiry sentence identified as an unlabeled guess. Half credit for either half alone. No credit
  for answers about tone, length or politeness, and no credit for treating the first sentence as
  the guess.

### q-fixed-when-line

- **type:** free
- **goal:** c-describe-app-bug
- **answer:** it says what the app should do when the problem is gone, in a form anyone can check,
  so whoever fixes it knows when they are finished and you can tell whether the fix worked. The
  rest of the request says what went wrong and how to make it happen again; without this line,
  "fixed" is left to the agent's judgment, and it may stop at something that only changes the
  symptom.
- **credit:** full credit for naming it as the checkable test for when the work is done, letting
  you or the agent tell whether the fix worked. Half credit for "it says what should happen
  instead" with nothing about telling whether it is fixed. No credit for "it summarises the
  request", "it is polite", or treating it as the labeled guess.

### q-first-line-of-error

- **type:** free
- **goal:** c-run-browser-check
- **answer:** the lines you left out are the ones that say where the error came from, and they are
  often the only part of the report that points at what to look at. The agent has the message but
  not the where, so it either asks you for the rest or guesses. A check is reported complete and
  unedited, pasted as it appeared, warnings included, rather than summarised.
- **credit:** full credit for saying the omitted lines carry what the agent needs, where the error
  happened, so it has to ask again. Half credit for "it wasn't complete" with no account of what
  was lost. No credit for saying a screenshot would have been better (the text could be copied), or
  for blaming the error itself rather than the report.

### q-which-tab-snippet

- **type:** mcq
- **goal:** c-run-browser-check
- **answer:** 4
- **credit:** the console belongs to one tab, so 1 is false and its number would come from the
  documentation page. 2 and 3 both report something that is not your app, which is the thing the
  request was about; where the request does not name a tab, the app is the tab it meant. Declining
  to run a snippet anywhere other than your own app is the same habit at work.
