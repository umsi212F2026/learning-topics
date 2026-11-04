Shape `burst`, case `spread-out`, natural kind `log`, Hard.

The natural place is the shared folder read against the log: the agent takes up letters a few at a
time, no faster than about ten a minute, each time choosing letter files in the folder that the log
does not name. The two facts behind it: where the items are held, "The form saves each of those
letters as a file in the newspaper's shared folder"; and what says which are done, "For each letter
it finishes, the agent adds a line naming that letter to a log." Every letter file not named in the
log is still waiting, so the workflow needs to keep nothing new.

The defining facts: the burst ("In the first quarter hour after each issue goes out, about three
hundred letters arrive") and the worker's limit ("The agent's provider takes only about ten
requests a minute"). At ten a minute the three hundred take about half an hour, inside "A thank-you
by the end of the school day is soon enough."

Other places:

- A list the workflow keeps, with a program adding each letter as the form saves it and handing
  them to the agent at ten a minute: workable, though more than the folder and the log already
  supply.
- A file the agent would newly save beside each finished letter, read against the folder:
  workable, though it only repeats what the log already says.
- The shared folder named alone, with nothing about how finished letters are told apart: not
  enough on its own, since every letter stays in the folder after it is done. Rule it workable
  only when the answer says how the waiting ones are found (not in the log, or a new file per
  finished letter).
- Nowhere: not workable. Three hundred letters in a quarter hour, at twenty a minute, would overrun
  a provider that takes ten.

The consequence without a queue, resting on the burst and the provider's limit: the agent would
send twice as many requests a minute as the provider takes, the refused ones would fail, and those
writers ("every writer should get one") would get no thank-you.

Irrelevant detail: "Our staff is eleven students and one faculty adviser."

Generic reasons that fail: "work might get lost", "a queue is safer", "it's good to keep a record".

True facts with no bearing on where the work waits, which also fail: the agent sorts each letter
by topic for the editors; hardly any letters come in the rest of the time (true, but it bears on
when the work arrives, not on where it waits).

Examples of each kind of tied reason, for the folder read against the log:

- What makes that place good here: "the form already saves every letter in the folder and the agent
  logs each one it finishes, so the letters not in the log are the ones still to do, and the agent
  can take them ten a minute."
- What would go wrong here without it: "three hundred letters in fifteen minutes would overrun a
  provider that takes ten a minute."
- What would make a specific other place worse: "a list of the workflow's own would only copy what
  the folder and the log already hold"; or "doing nothing would send twenty requests a minute to a
  provider that takes ten."

### q1

- **goal:** `c-when-to-queue`
- **cases:** spread-out
- **answer:** In the shared folder, read against the log: the agent takes up letter files the log
  doesn't name yet, no more than about ten a minute. The form saves every letter there and the
  agent logs each one it finishes, so the folder and the log together already say what is
  waiting. Without that, three hundred letters in a quarter hour would overrun a provider that
  takes ten requests a minute.
- **credit:** full when the answer names a workable place, said concretely for this workflow (the
  letter files in the shared folder not yet in the log, a file the agent would newly save beside
  each finished letter, or a list the workflow keeps as each letter arrives), and gives a reason
  tied to this workflow of any of the three kinds: what makes that place good here, what would go
  wrong here without it, or what would make a specific other place worse. The shared folder named
  with nothing about how the finished letters are told apart is not yet a workable place. A fact
  with no bearing on where the work waits, one resting on the size of the staff, or one the facts
  contradict is not a tied reason. A place named only generically ("put them in a queue") is ruled
  as a list the workflow keeps, which is workable here. Half when the place is workable but the
  reason is generic, untied or missing, or when the reason is tied but the place is unworkable (the
  folder alone, "because three hundred letters come at once"). None when the place is unworkable
  and the reason is generic, untied or missing, or when the answer says no place is needed.
- **tutor note:** if the answer names the shared folder alone, ask how the agent, halfway through
  the three hundred, tells which letters it has already thanked. If it says no place is needed
  because the letters are saved anyway, ask what stops the agent sending all three hundred to the
  provider at once.
