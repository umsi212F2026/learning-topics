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
- What would make a specific other place worse: "a list the program keeps would only ever hold one
  booking for a second, since the program is never off and never behind."

### q1

- **goal:** `c-when-to-queue`
- **cases:** no-queue
- **answer:** Nowhere: the program handles each booking as the website sends it. The front desk
  computer is never turned off and each booking takes about a second, with only a few an hour, so
  no booking ever has to wait. Losing one would not be acceptable, since a swimmer counts on the
  lane, but nothing is ever lost or held up here.
- **credit:** full when the answer says the work needn't wait anywhere and gives as the reason
  that the program is always available and never overloaded, tied to the facts that make it hold,
  with both halves: the front desk computer is never turned off, and a second a booking at a few
  an hour never overloads it. A fact with no bearing on whether the work waits, one resting on the
  heated pool, or one the facts contradict ("losing a booking doesn't matter") is not a tied
  reason. Half when the answer says no place is needed but the reason is generic, not tied, or
  missing, or names the condition that doesn't hold (dropping some bookings is acceptable); when
  it says no place is needed with only half of the condition (the program is fast enough for a few
  an hour, with nothing about the computer never being off, or the reverse); when it proposes a
  place while correctly saying that the program is always available and never overloaded here; or
  when it proposes a place with a "good here" reason that is true of this workflow (the website
  sends every booking, so a list the program keeps would lose none), since a place is workable but
  not needed. None when it proposes a place and names a loss the facts rule out, or with a reason
  that is generic or not tied, or gives no reason.
- **tutor note:** if the answer names a place, ask when a booking would ever be sitting there and
  for how long. If it says losing a booking is fine, ask what the swimmer finds when they arrive.
  If it gives only that the program is fast, ask what would happen to a booking sent while the
  computer was off; if it gives only that the computer is never off, ask how long the program
  takes over each booking.
