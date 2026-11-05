Shape `event-best`, case `event`, Hard. The work comes often enough (ten or fifteen times a day)
that a schedule every fifteen or thirty minutes looks tempting; the cost of each run is the fact
that tips it.

Accepted: an event, each sale that takes an item down to its last three starting a run. Cheap
repeated looks at the register's counts that start the agent only when an item has newly run low
("a program checks the counts every few minutes and starts the agent only when something is low")
are this same choice, whatever the answer calls them.

The deciding facts, and the sentences carrying them:

- How soon the result is needed: "I want to know within half an hour, because contractors come in
  and clear out the last few boxes of screws or fittings fast."
- How often and how unpredictably the work comes: "On a busy day that happens ten or fifteen times,
  at no set times."
- What each run costs: "Each time the agent runs, it reads through the counts for all twenty
  thousand items in the store and the supplier's whole price list, which costs real money even when
  nothing has run low."
- The watching fact, which rules out a person: "Nobody at the counter can keep an eye on the counts
  all day, since items run low at no set times."

Why the other kinds fit worse:

- A person: items run low at no set times, so someone would have to watch the counts all day, and
  the scenario says nobody at the counter can.
- A schedule: one slow enough to keep runs few (a few times a day) leaves most alerts hours past
  the half hour. One frequent enough to meet the half hour (every fifteen or thirty minutes) runs
  dozens of times a day for ten or fifteen low items, so many of those runs find nothing new, and
  every one of them reads all twenty thousand counts and the whole price list, at real cost. This
  is the Hard part: with ten or fifteen a day, a frequent schedule finds work more often than in a
  quiet workflow, and only the cost sentence shows it is still worse.

Never accepted, by name: a person at the counter starting a run when an item runs low (nobody can
watch the counts all day); a schedule a few times a day (too late for the half hour); a schedule
every fifteen or thirty minutes that runs the agent itself each time (dozens of costly runs, many
finding nothing).

The scenario does not say when the back-office computer is on. An answer that assumes it is never
off is bringing in a fact from outside the scenario; see the activity's doesn't-show.

Irrelevant detail: "My grandfather opened the store in 1962."

Generic reasons that fail: "a schedule is automatic", "events are faster", "a person can make sure
it's done right".

True facts with no bearing on the choice, which also fail: the alert says how many to bring out
from the stockroom; an item counts as low at its last three.

Examples of each kind of tied reason, for the event:

- What makes it good here: "items run low ten or fifteen times a day at no set times, so a run
  should start when one does."
- What would go wrong here without it: "on a schedule slow enough to be cheap, contractors could
  clear out the last boxes before the owner hears an item is low."
- What would make a specific other kind worse: "a schedule every fifteen minutes would read all
  twenty thousand counts and the whole price list dozens of times a day, paying each time, even
  when nothing has run low"; or "a person would have to watch the counts all day, and nobody at
  the counter can."

### q1

- **goal:** `c-choose-trigger`
- **cases:** event
- **answer:** An event: each sale that takes an item down to its last three should start a run.
  Items run low ten or fifteen times a day at no set times and the owner wants to know within half
  an hour, so a slow schedule would be too late, a frequent one would pay to read every count and
  the whole price list dozens of times a day, many of them for nothing, and nobody at the counter
  can watch the counts all day.
- **credit:** full when the answer chooses an event (including cheap repeated looks that start the
  agent only when an item has newly run low) and gives a reason tied to this workflow of any of the
  three kinds: what makes an event good here, what would go wrong here without it, or what would
  make a specific other kind worse. One tied reason is enough, and a reason that also names what
  the event costs still earns full credit. A fact with no bearing on the choice (what the alert
  says, the last-three rule), one resting on the irrelevant detail, or one the facts contradict is
  not a tied reason. An answer listing two choices is ruled as choosing neither; a combined design
  is ruled by its main choice. Half when the answer chooses an event with a generic, untied or
  missing reason, or chooses a person or a schedule that runs the agent itself with a reason
  resting on a fact that bears on the choice (for example, a schedule every fifteen minutes
  "because the owner wants to know within half an hour"). None when the choice is not accepted and
  the reason is generic, untied or missing, or no trigger is chosen.
- **tutor note:** the likely miss is a schedule every fifteen or thirty minutes, chosen because ten
  or fifteen low items a day seems like plenty of work for it; that is half. After the ruling, ask
  what each of those runs reads, and what it costs, when nothing has run low since the last one.
