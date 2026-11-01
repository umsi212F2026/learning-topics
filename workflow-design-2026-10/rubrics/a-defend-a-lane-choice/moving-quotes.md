Step 2 is `judgment-few-costly`: natural choice a person, alternative an AI agent. Step 4 is
`structured-irreversible`: natural choice a program, alternative an AI agent. Rule on the reasons,
never on the choice: any executor defended by reasons tied to the step's facts passes.

Where the facts are. In the office manager's paragraph, step 2's facts are in sentences 1, 2, 5
and 7: three to five requests a week, each turning on something the rate table doesn't cover
(sentence 1, its input); they list the home's valuables, such as a safe or a gun cabinet, next to
its address (sentence 2, its data); a quote too low leaves the family paying for a second trip,
often four hundred dollars or more, and each quote goes out with no one checking it (sentence 5,
what a mistake costs); Rosa prices these only on Monday and Thursday evenings (sentence 7, when
the decider is free). Step 4's facts are in sentences 3, 4 and 6: the approved list has one line
per move in a fixed form, about thirty-five a week, holding only a date, a job number and a crew
size, and nothing on it is about the customers, so the step handles no private data (sentence 3,
its input and its data); a few lines a week say "end of month, flexible" where the date should be
(sentence 4, the odd entries); a move booked on the wrong date leaves a family with no crew on the
day their lease ends, and nobody looks at the calendar again (sentence 6, what a mistake costs).

The irrelevant details, one per open step: for step 2, that most piano requests come from around
the music school (sentence 8); for step 4, that the calendar is color-coded by truck (sentence 9).
A reason resting on either is not tied.

### q1

- **goal:** `c-assign-a-lane`
- **answer:** A person, Rosa, rather than an AI agent. It helps correctness: each of the three to
  five requests turns on something the rate table doesn't cover, such as a piano on a curved
  staircase, and a quote too low costs the family four hundred dollars or more for a second trip,
  with no one checking the quote before it goes out; or it helps privacy: the lists of valuables
  next to home addresses stay in the company. It hurts timeliness: Rosa prices only on Monday and
  Thursday evenings, so a customer who asks on Friday waits until Monday for a quote; or it takes
  her evenings. Other pairings that pass:
  - An agent rather than Rosa: helps timeliness (a quote the day the request arrives, not the
    next Monday or Thursday evening); hurts correctness (the table doesn't cover these, and a
    quote too low goes out unchecked at four hundred dollars or more to the family) or privacy
    (a list of a home's safe and jewelry beside its address goes to the provider).
  - A person rather than a program: helps correctness (no rule could price a piano down a curved
    staircase, which is why the rate table can't); hurts timeliness (Monday and Thursday evenings)
    or Rosa's time.
  - A program rather than a person: helps timeliness (it quotes at once); hurts correctness (a
    rule's price for a move the table doesn't cover goes out unchecked).
  - An agent rather than a program: helps correctness (it can read what each unusual request
    describes); hurts privacy (the valuables and addresses go to the provider) or cost.
  - A program rather than an agent: helps privacy (the valuables lists stay in-house) or cost;
    hurts correctness (these are exactly the requests the rate table can't price).
- **credit:** full when the answer chooses an executor for step 2, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the few requests the rate table doesn't cover; the
  valuables listed beside the home's address; a quote too low costing the family a second trip,
  with no one checking; or Rosa being free only on Monday and Thursday evenings. A reason is tied
  when it refers to this step: "Rosa would price these moves more accurately than an agent" is
  tied; after ruling, the tutor says it would be stronger naming what about these moves makes
  accuracy hard, asks for that, and if the learner can't say, points to each request turning on
  something the rate table doesn't cover and a low quote going out unchecked. Generic reasons,
  which don't refer to the step at all: "a person has better judgment", "an agent is faster",
  "agents can be wrong in ways that look right". A reason resting on the piano requests coming
  from around the music school is not tied. An intermediate goal from the reading counts on the
  same terms as a final goal. Half when one of the two is tied and the other is generic or
  missing, or when both are tied but no alternative is named. None when neither is tied, or no
  executor is chosen.
- **tutor note:** a learner who says the cost of a mistake is the company's has misread who pays;
  ask who pays for the second trip when a quote is too low.

### q2

- **goal:** `c-assign-a-lane`
- **answer:** A program rather than an AI agent. It helps correctness: it books exactly the date
  on each approved line, every time, and a move on the wrong date leaves a family with no crew on
  the day their lease ends, with nobody looking at the calendar again. It hurts timeliness or the
  office manager's time: the few "end of month, flexible" lines a week will stop it, and someone
  has to settle a date with those customers by hand. Other pairings that pass:
  - An agent rather than a program: helps timeliness (it can pick a date for a "flexible" line and
    keep going); hurts correctness (it may pick or copy a wrong date, which nobody checks before
    moving day). A privacy reason does not hold here: nothing on the list is about the customers.
  - A program rather than the office manager: helps timeliness or the manager's time (about
    thirty-five bookings a week entered by hand otherwise) or correctness (no typing slip in a date
    nobody rechecks); hurts timeliness on the "flexible" lines it stops on.
  - The office manager rather than a program: helps correctness or timeliness on the "flexible"
    lines (the manager can call the customer and settle a date); hurts the manager's time (the
    volume) or correctness (a typing slip goes unchecked to moving day).
  - An agent rather than the office manager: helps timeliness (the volume); hurts correctness (it
    may guess a date for a "flexible" line, which nobody checks before moving day).
  - The office manager rather than an agent: helps correctness (on a "flexible" line the manager
    calls the customer to settle the date instead of guessing one); hurts timeliness or the
    manager's time (the volume).
- **credit:** full when the answer chooses an executor for step 4, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the approved list's fixed form, the "flexible" lines, the
  volume, or a wrong date leaving a family with no crew and nobody checking. A
  reason is tied when it refers to this step: "a program books these moves for less than the
  office manager's time costs" is tied; after ruling, the tutor says it would be stronger naming
  what about the bookings makes that hold, asks for that, and if the learner can't say, points to
  the approved list's fixed form and its thirty-five lines a week. Generic reasons, which don't
  refer to the step at all: "programs don't make mistakes", "a program costs almost nothing to
  run", "an agent is cheaper than paying the office manager". A privacy reason for this step contradicts
  the setup, which says nothing on the list is about the customers, and is not tied. A reason
  resting on the calendar's
  color-coding is not tied. An intermediate goal from the reading counts on the same terms: "a
  program fails loudly on a flexible date instead of guessing one" is tied; "a program fails
  loudly" alone is generic. Half when one of the two is tied and the other is generic or missing,
  or when both are tied but no alternative is named. None when neither is tied, or no executor is
  chosen.
- **tutor note:** a learner who says a program hurts nothing has missed the "flexible" lines; ask
  what a program would book for a line that says "end of month, flexible".
