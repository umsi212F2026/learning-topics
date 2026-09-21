# The words of react apps

**Intended goals:** `w-component`, `w-state`, `w-render`, `w-event-handler`, `w-dev-server`,
`w-dependency`, `w-build`, `w-hot-reload`, `w-browser-console`, `w-hard-reload`, `w-routing` and
`w-headless-browser`, with four questions on `c-describe-app-bug` and `c-run-browser-check` at the
end.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes an AI coding agent, imagine it is working on a React app on your own laptop: the
Vite starter you already have running, or one your agent built for you. Several questions are
about a small Tasks app your agent built. It runs at http://localhost:5173, it lists your tasks,
each task has a Done box, typing in the box at the top and clicking Add puts a new task at the
bottom, and clicking a task's text opens that task's own page.

### q-define-component

Your agent says it is going to pull the task list out into its own React component. Say what a component
is, in your own words.

### q-component-vs-page

What is the difference between a React component and a page?

### q-two-screens-two-components

A classmate says: "My Tasks app has two screens, the list and a single task's page, so the app has
exactly two React components." What is wrong with what they said?

### q-define-state

Your agent says the number next to Count is kept in state. Say what React state is, in your own words.

### q-state-vs-database

What is the difference between what an app is holding in state and what it has saved in a
database?

### q-list-only-in-state

Your agent says: "The tasks you add are only in the component's state. Nothing is written to a file
or a database." Which of these is true?

1. The tasks you add are safe, because state is where an app keeps things permanently.
2. The tasks you add are on the dev server, so they last for as long as it keeps running.
3. The tasks you add are being held by the app while it runs, and a page reload starts it over without them.
4. The tasks you add have already been thrown away.

### q-define-render

Your agent says the task list renders again whenever you tick a box. Say what React rendering is, in your
own words.

### q-render-vs-reload

What is the difference between a component rendering and the page reloading?

### q-click-reloads-page

A classmate says: "Every time I click Count the number on screen changes, so the page must be
reloading on each click." What is wrong with what they said?

### q-define-event-handler

Your agent says the Add button has no event handler on it. Say what an event handler is, in your
own words.

### q-handler-vs-event

What is the difference between a click event and that click's event handler?

### q-click-not-happening

A classmate says: "I click the new button and nothing happens at all, so the click event isn't
reaching the app." What is wrong with what they said?

### q-define-dev-server

You run `npm run dev` and leave that terminal window open while you work. Say what the dev server
is, in your own words.

### q-closed-terminal-still-up

A classmate says: "I closed the terminal window that `npm run dev` was running in, and my app is
still there in the browser tab, so the dev server was only needed to start it." What is wrong with
what they said?

### q-dev-server-other-port

Your agent says: "Something is already using port 5173, so I started your dev server on 5174
instead. Open http://localhost:5174." What is it telling you?

### q-define-dependency

Your agent says it has added a dependency to your project. Say what a dependency is, in your own
words.

### q-dependency-vs-installed-program

What is the difference between a dependency of your project and a program installed on your
computer, such as Chrome or Zettlr?

### q-agent-added-dependency

Your agent says: "To format the dates I've added date-fns to the project's dependencies and run
`npm install`, so it's there now." What is it telling you?

### q-define-build

You run `npm run build` and it writes a folder called `dist`. Say what a build is, in your own
words.

### q-build-vs-dev-server

What is the difference between the build and the dev server?

### q-built-once-updates

A classmate says: "I ran `npm run build` this morning, so `dist` has the whole app in it. Anything
the agent changes this afternoon will be in there too." What is wrong with what they said?

### q-define-hot-reload

Your agent says: "Save it and hot reload will take care of the rest." Say what hot reload is, in
your own words.

### q-hot-reload-vs-refresh

What is the difference between hot reload and refreshing the page yourself?

### q-saved-should-appear

Your agent says: "I've changed the heading and saved. You should see it in your tab in a second or
two, without touching anything." What is it telling you, and what would it mean if your tab still
showed the old heading a minute later?

### q-define-browser-console

Your agent asks you to check the browser console. Say what the browser console is, in your own
words.

### q-console-vs-terminal

What is the difference between the browser console and the terminal window where `npm run dev` is
running?

### q-pasted-terminal-for-console

A classmate says: "The agent asked what the console said when the page went white, so I copied what
the terminal running `npm run dev` had printed." What is wrong with what they said?

### q-define-hard-reload

Your agent asks you to do a hard reload. Say what a hard reload is, in your own words.

### q-hard-reload-vs-reload

What is the difference between a hard reload and an ordinary reload?

### q-hard-reload-looked-same

A classmate says: "I did a hard reload on the starter app and the page looked exactly the same as
after an ordinary reload, so hard reload doesn't do anything in my browser." What is wrong with
what they said?

### q-define-routing

Your agent says the Tasks app has no routing yet. Say what routing is, in your own words.

### q-address-changed-new-page

A classmate says: "When I click a task, the address bar changes to /tasks/1, so the browser has
fetched a new page from the server." What is wrong with what they said?

### q-routing-same-page-every-address

Your agent says: "The dev server hands back the same page for every address. The app looks at the
address and decides which screen to show." Which of these is true?

1. The dev server keeps a separate page saved for each address.
2. Which screen you see is worked out by the running app from the address, so an address only shows the right screen if the app knows what to do with it.
3. Every address shows the same screen, so the address bar means nothing in this app.
4. Any address you type will show the right screen, because the server always answers.

### q-define-headless-browser

Your agent says it will check the page in a headless browser. Say what a headless browser is, in
your own words.

### q-headless-vs-your-browser

What is the difference between the headless browser your agent uses and the browser you have open
on your laptop?

### q-no-headless-browser-here

Your agent says: "I don't have a headless browser in this session, so I can't look at the page
myself. Could you open http://localhost:5173, click Add, and tell me what you see?" Which of these
does that tell you?

1. The agent cannot open your app for itself here, so what it knows about the problem is whatever you report back.
2. The app is broken in a way that only a person could see.
3. Your dev server is not running, which is why the agent cannot reach the page.
4. The agent can see your browser tab already and wants you to confirm what is in it.

### q-links-expire-request

You're about to send your agent a message about a problem with your Tasks app: "Task pages are
blank when someone opens a link I sent them. The links expire after a while." Describe two problems with this message that might lead the agent to not fix it correctly.

### q-fixed-when-line

The last line of a request you send your agent reads: "It's fixed when a task I add is still in the
list after a reload." What does that line do that the rest of the request does not?

### q-first-line-of-error

Your agent asks you to click Clear done and paste what the console shows. The console shows a red
error with five more lines under it. You paste the first line and add "plus a few more lines of
stack trace". Why might the agent have to come back and ask you again?

### q-which-tab-snippet

Your agent asks: "In the console, run `document.querySelectorAll('button').length` and paste the
number." You have two tabs open in the same window: your app at http://localhost:5173, and a
documentation page you were reading, which is the tab in front. What should you do?

1. Run it in the tab that is in front, since it is the same console in every tab.
2. Run it in both tabs and paste both numbers, so the agent can pick the one it meant.
3. Run it in the tab that is in front and tell the agent which page that was, so it can allow for it.
4. Click into the app's tab, open the console there, run it, and paste what that tab printed.
