Shape `poll-best`, variant `no-word`, case `poll`, Medium. One fact settles it: the shared mailbox
sends no notice when new mail arrives, so the workflow can only find out by looking, and a look is
quick and free while a note can wait until the end of the day.

Accepted: polling, a program opening the shared mailbox and looking for new absence notes, at any
interval that handles each note before the end of the day it arrives (every ten minutes, every
hour, a few times a day). A hook is not accepted: the mailbox sends no notice, so there is nothing
to be told by.

The deciding facts, and the sentences carrying them:

- What rules out being told: "The mailbox sends no notice when new mail arrives."
- The machine can look, and a look is cheap: "A program can open it and look, which takes a
  moment and costs nothing."
- How long the result can wait: "The section leaders read the missing list each morning, so a note
  handled any time before the end of the day it arrives is fine."

Why a hook fits worse: a hook needs the source to send word when something happens, and the
mailbox never does, so a hook would never fire.

Irrelevant detail: "Our players wear green and gold uniforms."

Generic reasons that fail: "polling is simpler", "a hook is faster", "polling wastes resources"
(this last fails as a reason for a hook, and says nothing about this mailbox).

True facts with no bearing on the method, which also fail: the agent sends the parent a short
thank-you; the notes are about rehearsals.

Examples of each kind of tied reason, for polling:

- What makes it good here: "the mailbox sends no notice, so looking is the only way"; or "a look
  takes a moment and costs nothing"; or "a note can wait until the end of the day, so looking every
  hour is plenty."
- What would go wrong here without it: "waiting to be told, the agent would never hear of a note,
  since the mailbox sends no notice, and the missing list would stay empty."
- What would make the other method worse: "a hook needs the mailbox to send word, and it sends no
  notice of new mail."

### q1

- **goal:** `c-choose-noticing`
- **cases:** poll
- **answer:** Polling: a program opens the mailbox every hour or so and looks for new notes. The
  mailbox sends no notice of new mail, so a hook would never fire, and a look is quick and free
  while a note can wait until the end of the day.
- **credit:** full when the answer chooses polling, at any interval that handles a note before the
  end of the day it arrives, and gives a reason tied to this workflow of any of the three kinds:
  what makes polling good here (that the mailbox sends no notice is a full reason on its own, as
  are the quick, free look and a note that can wait until the end of the day), what would go wrong
  here without it, or what would make a hook worse. One tied reason is enough. A fact with no
  bearing on the method, one resting on the uniforms, or one the facts contradict is not a tied
  reason. An answer is ruled on the design it describes: "the mailbox tells the computer when a
  note arrives" is a hook, whatever it is called. An answer listing both methods is ruled as
  choosing neither; a combined design is ruled by its main method. Half when the answer chooses
  polling with a generic, untied or missing reason, or polls too seldom to handle a note by the end
  of its day (once every few days) with a reason resting on a fact that bears on the method. None
  when the answer chooses a hook, whatever its reason, since the mailbox can only be looked at;
  when it polls too seldom with a generic, untied or missing reason; or when it chooses no method.
- **tutor note:** if the answer chooses a hook, ask what the mailbox does when new mail arrives.
