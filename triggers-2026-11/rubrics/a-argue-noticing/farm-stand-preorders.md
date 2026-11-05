Shape `poll-best`, variant `costly-setup`, case `poll`, Hard. The facts pull both ways: the
preorder form can send a message each time a preorder comes in, which favors a webhook, but
receiving those messages needs the friend who built the website, who is away until the end of the
month, and preorders open this Saturday. Meanwhile a look at the list is quick and free, and a
confirmation within the hour is fine, so polling every ten minutes or so serves. The facts do not
balance: a webhook can't be ready when preorders open.

Accepted: polling, a program looking at the form's list of preorders at any interval that confirms
each within the hour (every ten minutes, every half hour). A webhook is not accepted: nobody can set
up receiving the messages before preorders open on Saturday.

The deciding facts, and the sentences carrying them:

- What rules out being told: "Receiving those messages means asking the friend who built our
  website, who is away on a sailing trip until the end of the month, and preorders open this
  Saturday."
- The machine can look, and a look is cheap: "A program can look at the form's list of preorders
  in a moment, at no cost."
- How long the result can wait: "A confirmation within the hour is fine."

The fact that pulls the other way: "The preorder form can send a message to a web address each
time a preorder comes in." It shows the source can send word, but nothing can take that word in
when preorders open.

Why a webhook fits worse: the form would send its messages from Saturday on, with nothing on the
farmhouse computer set up to receive them until the friend is back at the end of the month, so
every preorder in between would go unconfirmed.

Irrelevant detail: "The stand is painted red, with a hand-lettered sign at the end of our lane."

Generic reasons that fail: "a webhook is faster", "polling wastes resources", "it's simpler to
just poll".

True facts with no bearing on the method, which also fail: the boxes are berries; the agent picks
a pickup time when enough berries will be picked.

Examples of each kind of tied reason, for polling:

- What makes it good here: "a look at the list takes a moment and costs nothing"; or "a
  confirmation within the hour is fine, so looking every ten minutes is plenty."
- What would go wrong here without it: "waiting on a webhook, the preorders from Saturday on would
  sit unconfirmed until the friend gets back at the end of the month."
- What would make the other method worse: "receiving the messages needs the friend, who is away
  until the end of the month, and preorders open this Saturday."

### q1

- **goal:** `c-choose-noticing`
- **cases:** poll
- **answer:** Polling, a program looking at the list of preorders every ten minutes. A webhook
  would need the friend who built the website to set up receiving the messages, and that friend is away
  until the end of the month while preorders open Saturday; a look is quick and free, and a
  confirmation within the hour is fine.
- **credit:** full when the answer chooses polling, at any interval that confirms a preorder
  within the hour, and gives a reason tied to this workflow of any of the three kinds: what makes
  polling good here (the quick, free look is a full reason on its own, as is a confirmation that
  can wait up to an hour), what would go wrong here without it, or what would make a webhook worse
  (the friend away until the end of the month, with preorders opening Saturday). One tied reason is
  enough. A fact with no bearing on the method, one resting on the red stand and its sign, or one
  the facts contradict is not a tied reason. An answer is ruled on the design it describes: "the
  form pings the farmhouse computer when a preorder arrives" is a webhook, whatever it is called.
  An answer listing both methods is ruled as choosing neither; a combined design is ruled by its
  main method. Half when the answer chooses a webhook with a reason resting on a fact that bears
  on the method (for example, "a webhook, since the form can send a message each time"), or polls
  too seldom to confirm within the hour (once a day) with such a reason, or chooses polling at an
  accepted interval with a generic, untied or missing reason. None when the answer chooses a
  webhook, or polls too seldom, with a generic, untied or missing reason, or chooses no method.
- **tutor note:** if the answer chooses a webhook because the form can send one, ask who would set
  up receiving it and when they are back. An answer that polls now and plans to switch to a
  webhook once the friend returns is ruled by its main method for opening day, polling.
