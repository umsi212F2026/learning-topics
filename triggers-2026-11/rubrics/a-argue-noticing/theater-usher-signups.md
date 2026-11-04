Shape `poll-best`, variant `cant-be-reached`, case `poll`, Medium. One fact settles it: the website
can send a notice each time someone signs up, but notices need a web server to arrive at, and the
box office computer doesn't run one. The box office computer can still reach out and fetch the
list itself, quickly and for nothing, and a reply by the end of the day is fine.

Accepted: polling, the box office computer fetching the list of sign-ups from the website at any
interval that replies before the end of the day a volunteer signs up (every ten minutes, every
hour, a few times a day). A webhook is never accepted, nor a design that adds a web server or any
other receiver the scenario doesn't supply.

The deciding facts, and the sentences carrying them:

- What rules out being told: "The website can send a notice each time someone signs up, but
  notices need a web server to arrive at, and the box office computer doesn't run one."
- The machine can look: "The box office computer is connected to the internet and can fetch the
  list of sign-ups from the website."
- A look is cheap: "Fetching the list is quick and costs nothing."
- How long the result can wait: "A reply by the end of the day is fine."

Why a webhook fits worse: the website's notices would have nowhere on the box office computer to
arrive, so the agent would never hear of a sign-up. Polling needs only the box office computer to
reach out to the website, which it can; a webhook needs something the website can reach, which it
lacks.

Irrelevant detail: "The theater's lobby was once a bank, and the old vault is now the coat room."

Generic reasons that fail: "a webhook is faster", "polling wastes resources", "it's simpler to
just poll".

True facts with no bearing on the method, which also fail: the agent assigns each volunteer a
door; the volunteers are ushers.

Examples of each kind of tied reason, for polling:

- What makes it good here: "the box office computer can fetch the list of sign-ups itself"; or
  "fetching the list is quick and costs nothing"; or "a reply by the end of the day is fine, so
  fetching every hour is plenty."
- What would go wrong here without it: "waiting on the website's notices, the agent would hear of
  no sign-ups, since the box office computer has no web server for them to arrive at."
- What would make the other method worse: "notices need a web server to arrive at, and the box
  office computer doesn't run one."

### q1

- **goal:** `c-choose-noticing`
- **cases:** poll
- **answer:** Polling: the box office computer fetches the list of sign-ups every hour or so. The
  website's notices need a web server to arrive at, and the box office computer doesn't run one,
  while fetching the list is quick, free and something the computer can do itself.
- **credit:** full when the answer chooses polling, at any interval that replies before the end of
  the day, and gives a reason tied to this workflow of any of the three kinds: what makes polling
  good here (that the box office computer has no web server for the notices to arrive at is a full
  reason on its own, as are that it can fetch the list itself, the quick, free fetch and a reply
  that can wait until the end of the day), what would go wrong here without it, or what would make
  a webhook worse. One tied reason is enough. A fact with no bearing on the method, one resting on
  the old bank lobby, or one the facts contradict is not a tied reason. An answer is ruled on the
  design it describes: "the website pings the box office computer when someone signs up" is a
  webhook, whatever it is called. An answer listing both methods is ruled as choosing neither; a
  combined design is ruled by its main method. Half when the answer chooses polling with a
  generic, untied or missing reason, or polls too seldom to reply by the end of the day (once every
  few days) with a reason resting on a fact that bears on the method. None when the answer chooses
  a webhook, whatever its reason, including a design that adds a web server or other receiver the
  scenario doesn't supply; when it polls too seldom with a generic, untied or missing reason; or
  when it chooses no method.
- **tutor note:** if the answer chooses a webhook because the website can send one, ask where on
  the box office computer the notices would arrive.
