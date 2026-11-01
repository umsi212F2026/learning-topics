Steps 2 and 4 are the lumped ones; steps 1, 3 and 5 are single acts. Step 2 is Hard and step 4
is Medium.

Step 2 is `check-split`, done by the agent throughout, with its join with no change first and the
fixed side first. Its three parts are assigning referees to games, printing a card for each game,
and writing each game's message to its teams. The assignments and the cards look like different
kinds of thing, but both are checked the same way, against the availability list and the game
schedule: every game has two referees who are available, none due at two fields at once, none on
a game their child plays in, and each card shows its game's field, time and referees. The messages
are checked by a person reading them for courtesy and tone. So the only boundary goes before the
messages. This is the Hard join: a learner may take the move from assigning to printing cards as
a change in the kind of check, though nothing changes there.

Step 4 is `handoff-split`, with its change join first. Its three parts are the coordinator's
decisions on who is paid in full for each game, the program's pay for each referee, and the
program's total for the day. The decisions need the judgment of someone who knows the league's
practice and what happened at each field. The pay and the total are plainly one kind of act, both
checked against the decisions and the rate of $25 a game. So the only boundary goes at the handoff
from the coordinator to the program.

### q1

- **goal:** `c-divide-into-steps`
- **cases:** same-executor
- **answer:** The boundary goes after the game cards are printed and before the messages to the
  teams are written, not between assigning referees and printing the cards, since the agent does
  both and both are checked against the availability list and the schedule. It goes there because
  the kind of check changes: the assignments and cards are checked against the availability list
  and the rules about clashes and children's games, while the messages need a person to read them
  for courtesy and tone. Save the game cards, each game with its field, time and two referees, so
  the assignments can be checked before any team hears who is coming.
- **credit:** full when the answer puts the boundary between printing the cards and writing the
  messages; gives a reason naming the two kinds of check, each said even briefly (such as "check
  against availability" or "check for clashes" for one, "read for tone" for the other); and names
  a saved result concrete enough to check the assignments before the messages are written. The
  game cards pass, and so do the assignments themselves, since printing the cards only lays them
  out game by game. The availability list, a count or summary ("how many referees are working"),
  or the messages do not. Half when the boundary is at that join with only one of the other two: a
  reason that is missing, generic ("smaller steps are easier"), or resting only on an executor
  change the answer proposes (having the coordinator read the messages), which is not in this
  step; or a saved result that is missing or fails that test. At most half for an answer that also
  puts a boundary between assigning and printing the cards, since nothing changes there, so that
  boundary has no reason. None when the only boundary is between assigning and printing the cards,
  or no boundary is placed.
- **tutor note:** if they put a boundary before the cards, ask what someone would compare a card
  against to find a mistake, and what they would compare an assignment against.

### q2

- **goal:** `c-divide-into-steps`
- **cases:** executor-changes
- **answer:** The boundary goes at the handoff, after the coordinator decides who is paid in full
  for each game and before the program works out the pay, not between the pay and the day's
  total, since the program does both and both are checked against the decisions and the rate. It
  goes there because the executor changes from the coordinator to the program, and the check
  changes with it: the decisions need judgment about what happened at each field, while the pay
  can be checked by recomputing it from the decisions at $25 a game. Save the coordinator's
  decisions, each referee's games marked paid in full or not, so a referee who was paid wrongly
  can be traced to a decision or to the arithmetic.
- **credit:** full when the answer puts the boundary at the handoff between the coordinator's
  decisions and the program's pay; gives a reason naming the change of executor, or the change in
  the kind of check, or both; and names a saved result concrete enough to check the decisions
  before the pay is worked out. The coordinator's decision on each referee's games passes. The
  field marshals' reports, a count or summary ("how many referees were paid in full"), or the
  referees' pay or the day's total do not. Half when the boundary is at the handoff with only one
  of the other two: a reason that is missing or generic ("smaller steps are easier"), or a saved
  result that is missing or fails that test. At most half for an answer that also puts a boundary
  between working out each referee's pay and adding up the total, since nothing changes there, so
  that boundary has no reason. None when the only boundary is between the pay and the total, or
  no boundary is placed.
- **tutor note:** if they save the field marshals' reports, ask whether those would show what the
  coordinator decided about the referee who left at halftime.
