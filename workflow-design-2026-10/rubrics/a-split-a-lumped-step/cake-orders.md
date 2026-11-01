Steps 2 and 4 are the lumped ones; steps 1 and 3 are single acts. Step 2 is Hard and step 4 is
Medium.

Step 2 is `handoff-split`, with its join with no change first. Its three parts are the program's
price lookup, the program's draft quotes, and the owner's decisions on which designs the bakery
can make. The prices and the draft quotes look like different kinds of thing, but both are checked
the same way, by the same program, against the requests and the price chart: each quote carries
the right price for its size and flavor and the request's own details. The owner's decisions need
the judgment of someone who knows what the bakery's decorators can do and how busy the week is. So
the only boundary goes at the handoff from the program to the owner. This is the Hard join: a
learner may take the move from looking up a price to writing a quote as a change in the kind of
check, though nothing changes there.

Step 4 is `check-split`, done by the agent throughout, with its change join first and the fixed
side first. Its three parts are listing the days that still have room, writing the post and
writing the sign. The list of open days is checked against the confirmed orders and the limit of
eight a day. The post and the sign are plainly one kind of act, both read by a person for whether
they are clear and inviting. So the only boundary goes after the list of open days.

### q1

- **goal:** `c-divide-into-steps`
- **cases:** executor-changes
- **answer:** The boundary goes at the handoff, after the program fills in the draft quotes and
  before the owner decides which designs to take on, not between looking up the prices and filling
  in the quotes, since the program does both and both are checked against the requests and the
  price chart. It goes there because the executor changes from the program to the owner, and the
  check changes with it: the quotes can be checked against the price chart, while the decisions
  need judgment about what the bakery can make in time. Save the draft quotes, so a wrong price can
  be caught, and told apart from a wrong decision, before anything goes to a customer.
- **credit:** full when the answer puts the boundary at the handoff between the program's draft
  quotes and the owner's decisions; gives a reason naming the change of executor, or the change
  in the kind of check, or both; and names a saved result concrete enough to check the program's
  work before the owner decides. The draft quotes pass, and so do the looked-up prices for each
  request, since filling in a quote only sets the price beside the request's own details. The
  requests, the price chart, a count or summary ("the total value of the week's requests"), or the
  owner's decisions do not. Half when the boundary is at the handoff with only one of the other
  two: a reason that is missing or generic ("smaller steps are easier"), or a saved result that is
  missing or fails that test. At most half for an answer that also puts a boundary between looking
  up the prices and filling in the quotes, since nothing changes there, so that boundary has no
  reason. None when the only boundary is between looking up the prices and filling in the quotes,
  or no boundary is placed.
- **tutor note:** if they put a boundary between the prices and the quotes, ask how a mistake in
  each would be found, and whether the two ways differ.

### q2

- **goal:** `c-divide-into-steps`
- **cases:** same-executor
- **answer:** The boundary goes after the list of days that still have room and before the post
  and sign are written, not between the post and the sign, since the agent does both and both are
  read the same way. It goes there because the kind of check changes: the list of open days is
  checked against the confirmed orders and the limit of eight cakes a day, while the post and sign
  need a person to read them for whether they are clear and inviting. Save the list of open days
  with how many more cakes each can take, so it can be checked against the orders before anything
  is announced.
- **credit:** full when the answer puts the boundary between listing the open days and writing
  the post; gives a reason naming the two kinds of check, each said even briefly (such as "check
  against the orders" or "count against the limit" for one, "read for clarity" for the other); and
  names a saved result concrete enough to check the list before the post and sign are written. The
  list of open days, with how many more each can take, passes. The confirmed orders, a count or
  summary ("how many days are open"), or the post or sign do not. Half when the boundary is at
  that join with only one of the other two: a reason that is missing, generic ("smaller steps are
  easier"), or resting only on an executor change the answer proposes (having the owner read the
  post), which is not in this step; or a saved result that is missing or fails that test. At most
  half for an answer that also puts a boundary between the post and the sign, since nothing
  changes there, so that boundary has no reason. None when the only boundary is between the post
  and the sign, or no boundary is placed.
- **tutor note:** if they save "how many days are open", ask whether that would show a day listed
  as open that is already full.
