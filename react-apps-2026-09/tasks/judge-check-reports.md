# Judge ten replies to an agent's browser check

**Used by:** `a-judge-check-reports`, which serves `c-run-browser-check`. A study activity: nothing
here can meet the goal.

## The situation

Your agent is helping with a small Tasks app that runs on your laptop at http://localhost:5173. The
app lists tasks, each with a Done box, and has a Clear done button that removes ticked tasks. The
agent asked for two checks in the browser. Under each request are replies that different students
sent back. Where a reply included a screenshot, the brackets describe what the screenshot showed.

## For each reply, answer

Could the agent act on this reply without asking again? Yes or no. If no, write the question the
agent would have to send back.

When you have done all ten, say what the replies that worked have in common.

---

## Request A

> Could you open the browser console on the Tasks app, tick "Buy milk", click Clear done, and paste
> me everything that appears in the console? Then run this in the same console and paste what it
> prints: `localStorage.getItem('tasks')`

### a1

> Here's everything the console showed after Clear done, copied straight from it:
>
>     App.jsx:31 Uncaught TypeError: Cannot read properties of undefined (reading 'filter')
>         at clearDone (App.jsx:31:22)
>         at executeDispatch (react-dom_client.js?v=8c2e41d0:12412:11)
>     > localStorage.getItem('tasks')
>     < null
>
> Nothing else appeared.

### a2

> There was a red error, something about not being able to read "filter". The localStorage one
> said null.

### a3

> `Uncaught TypeError: Cannot read properties of undefined (reading 'filter')` and then `null`.

### a4

> [A screenshot of the console panel. The right-hand edge is cropped, so the file names and line
> numbers at the end of each line are cut off.]

### a5

> I couldn't find a Clear done button anywhere on the page I had open, so I skipped that step. The
> localStorage line printed `null`.

### a6

> When I pasted your line, the console said `Uncaught SyntaxError: Invalid or unexpected token`, so
> I retyped the quotes myself and then it printed null. After Clear done I got the error about
> "filter" again, same as before.

### a7

> Copied from the console:
>
>     App.jsx:31 Uncaught TypeError: Cannot read properties of undefined (reading 'filter')
>         at clearDone (App.jsx:31:22)
>         at executeDispatch (react-dom_client.js?v=8c2e41d0:12412:11)
>     > localStorage.getItem('tasks')
>     < null
>
> There was also a long yellow warning above the red error. I left it out because it wasn't an
> error.

## Request B

> Something looks off in narrow windows. Could you drag the browser window on the Tasks app as
> narrow as it will go, and show me what the list looks like?

### b1

> It looks squished, and the Done boxes end up in a weird spot.

### b2

> [A screenshot of the whole browser window at its narrowest. The address bar reads
> localhost:5173, and the whole list is visible: each Done box sits on its own line below its
> task instead of beside it.]

### b3

> [A screenshot cropped to just the "Buy milk" row and its box.]

---

## Key, for the tutor

Show the learner the situation, the requests and the replies, not this section. Take all ten
answers before commenting on any.

| reply | act on it? | why |
| ----- | ---------- | --- |
| a1 | yes | Both outputs copied as text, complete, including the lines under the error that say where it came from, and a statement that nothing else appeared. |
| a2 | no | A paraphrase. The agent needs the exact message and the lines under it: "Can you copy the error exactly as it appears, including the lines below it?" |
| a3 | no | Only the first line of the error. The lines under it, which say which file and line it came from, were cut. Complete means all of it. |
| a4 | no | This was text, so it could have been copied, and the crop removed the part that says where the error came from. A screenshot is for what can't be copied. |
| a5 | no | The missing button is the clue. The Tasks app has a Clear done button, so both steps almost certainly ran on some other page, and the `null` says nothing about the Tasks app. This matters beyond the report: a snippet an agent hands you runs in your own app's tab only, never in whatever page happens to be in front, which could be a site where you are logged in. The agent's question: "Which page was open in that tab? Could you open http://localhost:5173 and do both steps there?" |
| a6 | no | Two problems. First, the snippet was retyped instead of its failure being reported as it appeared: the agent no longer knows exactly what ran, and changing what the agent handed you isn't the learner's job here. Reporting the syntax error was the right part; quotes that turn curly when copied out of a chat are a common cause of that error, and worth mentioning to the learner, but the fix is the agent's to make. Second, "same as before" refers to something the agent never saw, so it still has to ask for the Clear done error text. |
| a7 | no | Edited. The learner decided the warning didn't matter, and the agent can't know whether it did. Warnings above an error are often the explanation. Unedited means leaving that judgment to the agent. |
| b1 | no | A description of something visual. This is what screenshots are for. |
| b2 | yes | The whole window, the address showing it's the app, and the thing asked about visible in full. |
| b3 | no | Cropped too tightly: the agent can't see the list as a whole, or which page this is. |

What the two that worked share: the output is all there, it is the output itself rather than a
description of it, it is text wherever text could be copied, and it came from the app's own tab.
