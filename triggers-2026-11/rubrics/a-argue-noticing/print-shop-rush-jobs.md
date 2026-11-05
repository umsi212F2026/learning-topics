Shape `hook-best`, case `hook`, Medium. The facts favor a webhook clearly: the source can send
word, receiving it is easy to set up, and the order page allows a look only once an hour against a
result needed within a few minutes.

Accepted: a webhook, the order page sending word each time a rush job comes in. Polling is not
accepted at any interval: the order page allows a look at most once an hour, and an hourly check leaves most
customers waiting far past the few minutes they want.

The deciding facts, and the sentences carrying them:

- The source can send word: "The order page can send a message to a web address each time a rush
  job comes in."
- Receiving it can be set up: "My partner, who looks after our computers, can set up the front
  computer, which is never turned off, to take in those messages in an afternoon."
- How soon the result is needed: "Customers want that email within a few minutes."
- What rules out frequent polling: "To protect itself from being flooded with requests, the
  website lets a program check for new orders no more than once an hour."

Why polling fits worse: to answer within a few minutes, a program would have to look every minute
or two, which the order page doesn't allow; the most it allows, once an hour, would leave a rush
job waiting up to an hour.

Irrelevant detail: "Our shop's sign is a pelican holding a pencil."

Generic reasons that fail: "a webhook is faster", "polling wastes resources", "it's simpler to
just poll".

True facts with no bearing on the method, which also fail: the agent works out a price and a
pickup time; the customers need their printing the same day.

Examples of each kind of tied reason, for a webhook:

- What makes it good here: "the order page can send a message each time a rush job comes in"; or
  "the partner can set up the front computer to take in those messages in an afternoon"; or "the
  front computer is never turned off, so the message will be received."
- What would go wrong here without it: "customers would wait up to an hour for the next look,
  long past the few minutes they want."
- What would make the other method worse: "the order page lets a program look only once an hour,
  so polling can't be quick enough."

### q1

- **goal:** `c-choose-noticing`
- **cases:** hook
- **answer:** A webhook: the order page can send a message each time a rush job comes in, and the
  partner can set up the always-on front computer to take those messages in an afternoon. Polling
  can't meet the few minutes customers want, since the website allows a check only once an hour.
- **credit:** full when the answer chooses a webhook and gives a reason tied to this workflow of
  any of the three kinds: what makes a webhook good here (the order page can send a message each
  time is a full reason on its own, as are the easy afternoon set-up and the front computer that
  is never turned off), what would go wrong here without it, or what would make polling worse.
  One tied reason is enough. A fact with no bearing on the method, one resting on the pelican sign,
  or one the facts contradict is not a tied reason. An answer is ruled on the design it describes:
  "a program looks every few minutes" is polling, whatever it is called. An answer listing both
  methods is ruled as choosing neither; a combined design ("a webhook, with hourly polling as a
  backup") is ruled by its main method. Half when the answer chooses polling with a reason resting
  on a fact that bears on the method (for example, "poll once an hour, since that is what the order
  page allows"), or chooses a webhook with a generic, untied or missing reason. None when the
  answer chooses polling with a generic, untied or missing reason, or chooses no method.
- **tutor note:** if the answer chooses polling every minute, ask what the order page allows. If
  it chooses hourly polling, ask how long a customer could wait.
