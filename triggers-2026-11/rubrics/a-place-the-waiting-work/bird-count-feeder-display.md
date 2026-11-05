Shape `no-queue`, case `no-queue`, variant `drop-ok`, Hard.

No queue is needed: the program shows each count as it arrives, and the counts sent while the
laptop is off are simply not shown. The condition that holds is that dropping some work is
acceptable, resting on "each new count replaces the one before it" (a missed count is replaced a
minute later by a newer one) and "The screen is there for visitors to enjoy, and the volunteers
keep the official tally on paper sheets out on the trails" (no count on the screen is the record of
anything). The other condition, that the worker is always available, does not hold: "The lobby
laptop is turned off each evening when the center closes ... and now and then a volunteer turns it
off during the day," while the camera sends a count "every minute, day and night."

Other places, all needless: holding the night's counts for the morning would only have the screen
run through hundreds of old counts, each replaced at once by the next, when "The screen should show
each count as it comes in." Nothing in the scenario says the camera keeps its counts, and nothing
in it is on to keep a list overnight, so a place would also have to be newly built, for counts nobody
needs.

Irrelevant detail: "Chickadees are the most common birds at the feeder."

Generic reasons that fail: "a queue would be overkill", "simpler is better", "it's fast enough".

True facts with no bearing on whether the work waits, which also fail: the camera is at the big
feeder outside the lobby window; the program takes about a second to show each count (true, but
it would not keep the laptop on overnight).

Examples of each kind of tied reason, for no place:

- What makes no place good here: "each count replaces the last on a screen that is only for
  visitors, and the official tally is on paper, so missing the counts from while the laptop is off
  costs nothing."
- What would make a specific other place worse: "keeping the night's counts would save hundreds of
  numbers that the next count replaces anyway."

### q1

- **goal:** `c-when-to-queue`
- **cases:** no-queue
- **answer:** Nowhere: the program shows each count as it comes in, and counts sent while the
  laptop is off are simply skipped. Each new count replaces the last on a screen that is only for
  visitors, and the official tally is kept on paper, so a missed count costs nothing. The laptop is
  off every night and at times by day, so it is not always available, but it doesn't need to be.
- **credit:** full when the answer says the work needn't wait anywhere and gives as the reason
  that dropping some counts is acceptable, tied to the fact that makes it hold: each new count
  replaces the one before it, or the screen is for visitors and the official tally is on paper.
  A fact with no bearing on whether the work waits, one resting on the chickadees, or one the facts
  contradict ("the laptop is always on") is not a tied reason. Half when the answer says no place
  is needed but the reason is generic, not tied, or missing, or names the condition that doesn't
  hold (the laptop is always available and never overloaded); when it proposes a place while
  correctly saying that dropping some counts is acceptable here; when it proposes a place with a
  "good here" reason that is true of this workflow, since a place is workable but not needed; or
  when it proposes a place for a loss that is
  real but harmless (keeping every count so none is missed, when each is replaced by the next).
  None when it proposes a place and names a loss the facts rule out, or with a reason that is
  generic or not tied, or gives no reason.
- **tutor note:** if the answer names a place for the night's counts, ask what the screen would
  do with them in the morning, and who needs them. If it says no place because the program is
  fast, ask what happens to the counts sent at midnight.
