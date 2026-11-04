Shape `no-queue`, case `no-queue`, variant `always-ready`, Medium.

No queue is needed: the front desk program takes up each booking the moment the website sends it.
The condition that holds is that the worker is always available and never overloaded, resting on
"The front desk computer is never turned off" (always available), "The program handles each
booking in about a second" and "Bookings come in a few an hour" (never overloaded: a few seconds of
work an hour). The other condition, that dropping some work is acceptable, does not hold: "A
swimmer who books expects that lane to be theirs on arrival", so a lost booking is a swimmer with
no lane and no confirmation.

Other places, all needless rather than wrong: a list the program keeps, a record the website keeps,
or files and a log would each hold bookings that never have to wait. "Swimmers often book on their
way over, so the confirmation should go out right away" also tells against any place that holds a
booking for a later run.

Irrelevant detail: "The pool is heated year round."

Generic reasons that fail: "a queue would be overkill", "simpler is better", "it's fast enough".

True facts with no bearing on whether the work waits, which also fail: the program marks the lane
taken on the schedule screen by the entrance; swimmers book for lap swim.

Examples of each kind of tied reason, for no place:

- What makes no place good here: "the front desk computer is never off and each booking takes a
  second, with only a few an hour, so every booking is done as soon as it arrives."
- What would go wrong here with a place: "holding bookings for a later run would delay the
  confirmation for swimmers already on their way over."
- What would make a specific other place worse: "a list the program keeps would only ever hold one
  booking for a second, since the program is never off and never behind."

### q1

- **goal:** `c-when-to-queue`
- **cases:** no-queue
- **answer:** Nowhere: the program handles each booking as the website sends it. The front desk
  computer is never turned off and each booking takes about a second, with only a few an hour, so
  no booking ever has to wait. Losing one would not be acceptable, since a swimmer counts on the
  lane, but nothing is ever lost or held up here.
- **credit:** full when the answer says the work needn't wait anywhere and gives a reason tied to
  this workflow of any of the three kinds: what makes having no place good here (the computer is
  never off, and a second a booking at a few an hour never overloads it), what would go wrong here
  with a place (the confirmation would come late for swimmers on their way), or what would make a
  specific other place worse. A fact with no bearing on whether the work waits, one resting on the
  heated pool, or one the facts contradict ("losing a booking doesn't matter") is not a tied
  reason. Half when the answer says no place is needed but the reason is generic, untied, missing
  or contradicted. None when the answer names a place where the work should wait.
- **tutor note:** if the answer names a place, ask when a booking would ever be sitting there and
  for how long. If it says losing a booking is fine, ask what the swimmer finds when they arrive.
