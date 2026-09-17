# Sort eight bug requests

**Used by:** `a-sort-bug-requests`, which serves `c-describe-app-bug`. A study activity: nothing
here can meet the goal.

## The app

Your agent built a small Tasks app. It runs on your laptop at http://localhost:5173.

- The list page starts with three sample tasks: Buy milk, Walk dog, Call Sam.
- Each task has a Done box you can tick.
- Typing in the box at the top and clicking Add puts a new task at the bottom of the list.
- Clicking a task's text opens that task's own page. Its address ends in `/tasks/` and the task's
  number, so Buy milk's page is http://localhost:5173/tasks/1.
- A Clear done button removes every ticked task.
- The app is supposed to keep your tasks when you reload the page or come back later.

Below are eight requests that eight different people sent their agent about this app. Each one is
about a real problem. None of the writers is you.

## For each request, answer two questions

1. Could someone who never saw the problem make it happen again from this request alone, and tell
   when it had been fixed? Yes or no. If no, say the one thing that stops them.
2. If the request guesses at the cause, is the guess kept apart from what the writer saw, and
   labeled as a guess? (A request with no guess at all is fine.)

When you have done all eight, say in one or two sentences the rule you used to sort them. Then
pick two of the requests that failed and rewrite them so they pass. Invent nothing the writer
could not have seen.

---

### r1

> You said you changed the heading from "Tasks" to "My Tasks" and saved. The page still says
> "Tasks", even after I reloaded. It's fixed when the heading says "My Tasks".

### r2

> The app doesn't keep a task I add. Steps, at http://localhost:5173: type "Buy bread" in the box
> and click Add. "Buy bread" appears at the bottom of the list. Now reload the page. The list shows
> only the three sample tasks, and "Buy bread" is gone. I expected it to still be there, because
> the app is supposed to keep my tasks. It's fixed when a task I add is still in the list after a
> reload. My guess, which I haven't checked: the new task is only remembered until the page
> reloads.

### r3

> Task pages are blank. At http://localhost:5173 I clicked "Buy milk", and the page that came up
> had the heading "Task" and no task text under it. It should show "Buy milk". It's fixed when
> clicking "Buy milk" shows its text.

### r4

> Ticking a task ticks the wrong one. At http://localhost:5173, with the three sample tasks, click
> the Done box next to "Buy milk". The box next to "Walk dog" gets ticked instead, and "Buy milk"
> stays unticked. It happens every time, and ticking "Walk dog" ticks "Call Sam". It's fixed when
> clicking a task's box ticks that task's own box. I'd guess the boxes are off by one, but that's
> only a guess.

### r5

> At http://localhost:5173 I typed "Buy bread" and clicked Add, and it showed up at the bottom.
> Because the app only keeps tasks in state, reloading the page wiped it, and only the three sample
> tasks came back. Please make tasks survive a reload. It's fixed when "Buy bread" is still there
> after I reload.

### r6

> The whole page goes white after Clear done. At http://localhost:5173, tick the Done box on "Buy
> milk", then click Clear done. The page goes completely white: no heading, no list, no message.
> The browser console shows this in red, copied as it appeared:
>
>     Uncaught TypeError: Cannot read properties of undefined (reading 'filter')
>         at clearDone (App.jsx:31:22)
>
> Reloading brings the app back. I expected "Buy milk" to disappear and the other two tasks to
> stay. It's fixed when those two steps leave "Walk dog" and "Call Sam" on screen and nothing red
> in the console.

### r7

> A task's page only works if I get there by clicking. At http://localhost:5173, click "Buy milk".
> The address changes to http://localhost:5173/tasks/1 and the page shows "Buy milk". Now copy
> that address, open a new tab, paste it and press Enter. The page shows the heading "Task" and
> nothing under it. Reloading while on the task page does the same. I expected to see "Buy milk"
> either way. It's fixed when pasting http://localhost:5173/tasks/1 into a new tab shows "Buy
> milk".

### r8

> The app crashes to a white screen when I click one of the buttons. The console had a red error
> saying something about "filter" being undefined. It's fixed when it doesn't go white.

---

## Key, for the tutor

Show the learner the app description and the requests, not this section. Take all eight answers
and the stated rule before saying anything about any of them.

| request | question 1 | question 2 | what decides it |
| ------- | ---------- | ---------- | --------------- |
| r1 | no | no guess | No address. The agent opens its own copy of the app, sees "My Tasks", and has nothing to go on. The address in the tab is exactly what would show that the tab is on a different copy of the app, or on a dev server that has stopped. Saying a reload was tried is good and not enough. |
| r2 | yes | yes | Starts from a fresh page, gives each step, says what happened and what should have, says how to tell it's fixed, and fences off the guess. |
| r3 | no | no guess | The steps don't produce the problem. Anyone who clicks "Buy milk" from the list sees it working. The writer must have reloaded or pasted the address at some point without noticing, and left that out. The "fixed when" line is already true, so the agent could declare it fixed without changing anything. The near miss is r7. |
| r4 | yes | yes | A problem you can see on one screen, fully described, with the guess labeled. It shows that a guess is allowed, not that one is required. |
| r5 | yes | no | Everything a stranger needs is there, but "because the app only keeps tasks in state" is a cause, stated as though it had been seen. Nobody can see that from the browser. The near miss is r2, which differs from this almost only there. |
| r6 | yes | no guess | The screen explains nothing, so the console text is what makes this useful, and it is copied rather than paraphrased. The two steps from a fresh page make it happen, and "fixed when" can be checked. |
| r7 | yes | no guess | The one route that fails (a pasted address, or a reload on the task page) is spelled out, and so is the route that works. |
| r8 | no | no guess | Which button, and starting from what? Clear done only fails when a task is ticked. The console error is paraphrased, which loses the part saying where it came from, and "doesn't go white" can't be checked without the missing steps. Unlike the other three that fail, this one is plainly bad; it is here to be set beside r6, the same bug described well. |

The rule the learner should arrive at, in some words of their own: a request passes when it names
where to start, gives the steps from there, says what happened and what should have happened, says
how you would know it's fixed, and keeps any idea about the cause apart from all that, marked as a
guess. A good rewrite of r1 or r3 has to add something the writer could actually have seen: the
address in the tab for r1, and the reload or pasted address for r3.
