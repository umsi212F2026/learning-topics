Step 2 is `messy-volume-checked`: natural choice an AI agent, alternative a person. Step 4 is
`structured-irreversible`: natural choice a program, alternative an AI agent. Rule on the reasons,
never on the choice: any executor defended by reasons tied to the step's facts passes.

Where the facts are. The setup's second sentence gives step 2's volume: about 200 reports a week.
In the fleet lead's paragraph, step 2's facts are in sentences 1, 3 and 4: the reports are typed
on phones, from one word to a paragraph, and many name a bike by where it's parked, though two docks
are both called Main Street, so a report can be matched to the wrong bike (sentence 1, its input);
many carry the rider's full name and phone number (sentence 3, its data); a wrong match or mark
almost never gets past the fleet lead at step 3 (sentence 4, what a mistake costs). Step 4's facts
are in sentences 2, 5 and 7: the signed-off list, sixty or so bikes a week, has one line per bike
in a fixed form, and nothing on it is about riders, so the step handles no private data (sentence
2, its input and its data); a few lines a week carry two bike numbers (sentence 5, the odd
entries); a bike wrongly shown as available goes straight back for rent, and the next anyone hears
of it is from a hurt rider (sentence 7, what a mistake costs).

The irrelevant details, one per open step: for step 2, that the app's report button turned green
(sentence 6); for step 4, that the fleet system came secondhand from a neighboring city (sentence
8). A reason resting on either is not tied.

### q1

- **goal:** `c-assign-a-lane`
- **answer:** An AI agent rather than the fleet lead. It helps timeliness or cost: about 200
  reports a week, typed on phones in every style, would take the fleet lead hours to read and
  match. It hurts privacy: many reports carry the rider's full name and phone number, which would
  go to the agent's provider; or it hurts correctness: a report that names a bike by where it's
  parked invites the agent to match it to the wrong bike, since two docks are called Main Street (a
  slip the fleet lead almost never misses at step 3, which is also a tied reason the agent's
  mistakes are tolerable here). Other pairings that pass:
  - The fleet lead rather than an agent: helps privacy (the riders' names and phone numbers stay
    with the bike-share) or correctness (the fleet lead knows, or can check, which Main Street a
    rider meant); hurts timeliness or the fleet lead's time (200 reports a week).
  - An agent rather than a program: helps correctness (reports typed in riders' own words, which a
    program can't match to a bike or mark); hurts privacy (a program keeps the names and phone
    numbers in-house) or cost (an agent costs more per run).
  - A program rather than an agent: helps privacy (the names and phone numbers go nowhere) or
    cost; hurts correctness (free text that names bikes by place, so many would be matched or
    marked wrong and the fleet lead would spend step 3 fixing them).
  - The fleet lead rather than a program: helps correctness (reading free text and sorting out
    which dock a rider meant); hurts timeliness (the volume).
  - A program rather than the fleet lead: helps timeliness (the volume); hurts correctness (free
    text a program can't read).
- **credit:** full when the answer chooses an executor for step 2, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the reports being typed free text, their volume, bikes
  named by where they're parked and the two Main Street docks, the riders' names and phone numbers,
  or the fleet lead's review at step 3 that catches a wrong match. A reason is tied when it refers
  to this step: "an agent gets through these reports faster than the fleet lead" is tied; after
  ruling, the tutor says it would be stronger naming what about the reports makes speed matter,
  asks for that, and if the learner can't say, points to the 200 reports a week typed in every
  style. Generic reasons, which don't refer to the step at all: "an agent is faster", "a person has
  better judgment", "agents can be wrong in ways that look right". A reason resting on the green
  report button is not tied. An intermediate goal from the reading counts as a goal helped or hurt
  when its reason is tied to a fact here. Half when one of the two is tied and the other is generic
  or missing, or when both are tied but no alternative is named. None when neither is tied, or no
  executor is chosen.
- **tutor note:** a learner who says a wrong mark here could get a rider hurt has taken step 4's
  cost for step 2's; ask what happens to a wrong mark before any bike goes back to its dock.

### q2

- **goal:** `c-assign-a-lane`
- **answer:** A program rather than an AI agent. It helps correctness: it marks exactly the bikes
  on the signed-off list, every time, and a bike wrongly shown as available goes straight back for
  rent, with the next word of it coming from a hurt rider. It hurts timeliness or someone's time:
  the few lines a week with two bike numbers will stop it, and those repaired bikes sit out of
  service until someone splits the line by hand. Other pairings that pass:
  - An agent rather than a program: helps timeliness (it can read a two-bike line and mark both);
    hurts correctness (it may mark the wrong number, and a faulty bike goes out unchecked). A
    privacy reason does not hold here: nothing on the list is about riders.
  - A program rather than the fleet lead: helps timeliness or the fleet lead's time (sixty or so
    bikes a week marked by hand otherwise) or correctness (no typing slip on a bike number nobody
    rechecks); hurts timeliness on the two-bike lines it stops on.
  - The fleet lead rather than a program: helps correctness or timeliness on the two-bike lines
    (the fleet lead can mark both at once); hurts the fleet lead's time (the volume) or correctness
    (a typing slip puts a faulty bike back out unchecked).
  - An agent rather than the fleet lead: helps timeliness (the volume); hurts correctness (a
    misread bike number puts a faulty bike back out, unchecked).
  - The fleet lead rather than an agent: helps correctness (the fleet lead signed off the list
    and knows which bikes were fixed); hurts timeliness or the fleet lead's time (the volume).
- **credit:** full when the answer chooses an executor for step 4, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the signed-off list's fixed form, the two-bike lines, the
  volume, or a faulty bike going straight back for rent with nobody checking. A reason is tied when
  it refers to this step: "a program won't mark the wrong bikes" is tied; after ruling, the tutor
  says it would be stronger naming what about the step makes that matter, asks for that, and if
  the learner can't say, points to a faulty bike going straight back to its dock unchecked.
  Generic reasons, which don't refer to the step at all: "programs don't make mistakes", "a program
  costs almost nothing to run", "an agent is cheaper than paying the fleet lead". A privacy reason
  for this step contradicts the setup, which says nothing on the list is about riders, and is not
  tied. A reason resting on the secondhand fleet system is not tied. An intermediate goal from the
  reading counts on the same terms: "a program fails loudly on a two-bike line instead of guessing"
  is tied; "a program fails loudly" alone is generic. Half when one of the two is tied and the
  other is generic or missing, or when both are tied but no alternative is named. None when neither
  is tied, or no executor is chosen.
- **tutor note:** a learner who says a program hurts nothing has missed the two-bike lines; ask
  what a program would do with a line holding two bike numbers.
