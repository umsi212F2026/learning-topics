# Judge ten plans for checking that an app really saves

**Used by:** `a-judge-persistence-plans`, which serves `c-check-persistence`. A study activity:
nothing here can meet the goal.

## The app and the message

Streaks is a small habit tracker running on your laptop at http://localhost:5173. You add habits
(such as "Stretch" or "Read 20 pages"), and each day you tick the ones you did. It shows how many
days in a row you've kept each one up.

Your agent has just sent you this:

> I've added a server and a SQLite database to Streaks. Your habits and your daily ticks are now
> saved, so they'll still be there when you come back.

## Four ways the agent could be wrong

An app can look as if it saves when it doesn't. Suppose the agent was wrong in one of these four
ways:

- **P, the page.** Streaks keeps your habits only in the open page. They're there until the page is
  reloaded or opened again.
- **B, the browser.** Streaks keeps them in that browser's own storage. They survive a reload and a
  server restart, but a different browser, or a private window, has never seen them.
- **S, the server.** Streaks sends them to the server, which keeps them in its memory rather than in
  the database. Any browser sees them, until the server restarts.
- **T, the tables.** Streaks keeps them in the database, but whenever the agent changes the tables
  (say, to add a reminder time to each habit), the table is thrown away and made again, empty.
  Everything survives until the tables change.

Ten students each wrote what they would do to find out whether Streaks really saves.

## For each plan, answer

Which of P, B, S and T would this plan catch? A plan catches one if, followed exactly as written,
it would show you that your habits were gone.

When you've done all ten, say what the plans that catch all four have in common. Then write your
own plan, as short as you can make it while still catching all four.

---

### p1

> I'd reload the page and check my habits are still there.

### p2

> I'd ask Codex whether my habits are really being saved in the database.

### p3

> I'd add a habit, close the tab, then open Streaks in a new tab and look for it.

### p4

> I'd add a habit, then open the same address in Firefox instead of Chrome and look for it there.

### p5

> I'd add a habit, ask Codex to restart the server, and then reload the page to see if the habit is
> still there.

### p6

> I'd add a habit and tick it, then open a private window and look for both. Then I'd ask Codex to
> restart the server and look again in a new private window.

### p7

> I'd ask Codex to add a reminder time to each habit. Then I'd add a new habit, reload, and check
> it's there with its reminder time.

### p8

> I'd add a habit, ask Codex to add a reminder time to each habit, then reload the page and look
> for the habit I added.

### p9

> I'd add two habits and tick one. Then: reload the page and look; open the same address in a
> different browser and look; ask Codex to restart the server and reload that other browser; and
> the next time Codex changes the tables, reload that other browser again and look for those same
> two habits and the tick.

### p10

> I'd save a habit and look for it in a private window. Then I'd have Codex restart the server and
> look in a new private window. After Codex next changes the tables, I'd open another private
> window and look for that same habit.

---

## Key, for the tutor

Show the learner everything above this section, not this section. Take all ten answers before
commenting on any.

| plan | P | B | S | T | what decides it |
| ---- | - | - | - | - | --------------- |
| p1 | yes | no | no | no | A reload catches only the page. The same browser still has its own storage, the server wasn't restarted, and the tables didn't change. |
| p2 | no | no | no | no | Asks the agent, which the goal rules out: an agent that kept the habits in the page believes it saved them. Nothing is checked from the running app. |
| p3 | yes | no | no | no | A new tab in the same browser is a reload with extra steps. Worth pointing out, because it feels like more. |
| p4 | yes | yes | no | no | A different browser has neither the page's memory nor the first browser's storage. The server's memory is still there, and the tables haven't changed. |
| p5 | yes | no | yes | no | Restarting the server is the right move for S, but looking again in the same browser lets B through: that browser shows its own stored copy whatever the server lost. Discuss this one whatever the learner answered. |
| p6 | yes | yes | yes | no | Complete except for the tables. A private window catches P and B, and the restart catches S. |
| p7 | yes | no | no | no | The habit was added after the tables changed, so T's loss (what was already there) can't show. The reload catches P. Codex may have restarted the server to change the tables, but that happened before the habit existed, so S isn't caught either. Compare with p8. |
| p8 | yes | no | no | yes | Saves before the change and looks after it, so T is caught, and the reload catches P. Looking in the same browser lets B through. S is caught only if Codex happened to restart the server to make the change; the plan doesn't make sure of it, so count it as not caught. The only difference from p7 is the order. |
| p9 | yes | yes | yes | yes | Each step catches one: the reload P, the other browser B, the restart S (looked at from the other browser, so B's stored copy can't hide it), and the same habits after the next table change T. |
| p10 | yes | yes | yes | yes | The shortest complete plan. Every look is from a fresh private window, which catches P and B at every step, so the restart catches S and the table change catches T. |

What the complete plans share: every look is from a page that has never seen the habits (a reload
at the least, and another browser or a private window); the server is restarted before one of the
looks; something is saved before the tables change and that same thing is looked for afterwards;
and nothing rests on the agent's word. The learner's own plan should do all of that. Order matters
only for T: save first, change after.
