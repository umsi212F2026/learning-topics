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

### q-links-expire-request

You're about to send your agent a message about a problem with your Tasks app: "Task pages are
blank when someone opens a link I sent them. The links expire after a while." Describe two problems with this message that might lead the agent to not fix the problem.

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
