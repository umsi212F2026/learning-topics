Shape `hook-best`, case `hook`, Hard. The facts pull both ways: setting up the front desk computer
to take in the messages is a real bother (a full day of the computer person's time and an extra
paid visit), but the owner wants a reply within a minute or two, and each look at the requests is
slow and costly, so polling would have to run nearly without pause and still could not keep up.
The facts do not balance: the set-up is a one-time cost the clinic can pay, while polling cannot
meet the minute or two at any interval.

Accepted: a webhook, the website sending word each time an appointment request comes in. Polling
is not accepted at any interval: each look takes the agent several minutes, longer than the minute
or two an owner will wait, and polling often enough to come close would mean the agent rereading
every request almost without stopping, running up its bill.

The deciding facts, and the sentences carrying them:

- The source can send word: "The website can send a webhook each time a request comes in."
- Receiving it can be set up: "Setting up the front desk computer, which is never turned off, to
  take in those messages would take our computer person a full day, and since she only comes in on
  Thursdays, it means booking and paying for an extra visit."
- How soon the result is needed: "A worried owner wants that text within a minute or two, before
  they give up and drive to the emergency hospital across town."
- What rules out frequent polling: "Each look at the requests means the agent reading every
  request on the form again, which takes it several minutes and runs up the bill for the agent."

Why polling fits worse: to reply within a minute or two, a program would have to look every
minute or so, but each look takes several minutes and costs money, so the looks would pile up and
the bill with them; any interval the clinic could afford leaves owners waiting long past the
minute or two, and some would drive across town.

Irrelevant detail: "Our clinic cat, Biscuit, sleeps on the front desk most afternoons."

Generic reasons that fail: "a webhook is faster", "polling wastes resources", "it's simpler to
just poll".

True facts with no bearing on the method, which also fail: the agent finds the earliest open slot
with a vet; the owner gets the time by text rather than email.

Examples of each kind of tied reason, for a webhook:

- What makes it good here: "the website can send a webhook each time a request comes in"; or "the
  front desk computer is never turned off, so the messages will be received"; or "the computer
  person can set it up in a day, which is worth paying for once."
- What would go wrong here without it: "owners would wait for the agent's next slow look, past
  the minute or two, and drive to the emergency hospital instead."
- What would make the other method worse: "each look means the agent rereading every request,
  which takes several minutes and runs up the bill, so polling can't be quick enough."

### q1

- **goal:** `c-choose-noticing`
- **cases:** hook
- **answer:** A webhook: the website can send one each time a request comes in, and the computer
  person can set up the always-on front desk computer to take them, a bother but a one-time one.
  Polling can't meet the minute or two owners will wait, since each look takes the agent several
  minutes and runs up its bill.
- **credit:** full when the answer chooses a webhook and gives a reason tied to this workflow of
  any of the three kinds: what makes a webhook good here (the website can send one each time is a
  full reason on its own, as are a set-up the computer person can do and a front desk computer
  that is never turned off), what would go wrong here without it, or what would make polling
  worse. One tied reason is enough. A fact with no bearing on the method, one resting on Biscuit
  the cat, or one the facts contradict is not a tied reason. An answer is ruled on the design it
  describes: "a program looks every few minutes" is polling, whatever it is called. An answer
  listing both methods is ruled as choosing neither; a combined design ("a webhook, with a poll
  each evening as a backup") is ruled by its main method. Half when the answer chooses polling
  with a reason resting on a fact that bears on the method (for example, "poll, because setting up
  the webhook costs a full day and an extra visit"), or chooses a webhook with a generic, untied
  or missing reason. None when the answer chooses polling with a generic, untied or missing
  reason, or chooses no method.
- **tutor note:** if the answer chooses polling to save the set-up cost, ask how long one look
  takes the agent and how long an owner will wait. If it chooses polling every minute, ask what
  each of those looks would cost.
