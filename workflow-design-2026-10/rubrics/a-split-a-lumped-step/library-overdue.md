Steps 2 and 4 are the lumped ones; steps 1, 3 and 5 are single acts. Step 2 is Medium and step 4
is Hard.

Step 2 is `handoff-split`, with its join with no change first. Its three parts are the agent's
match of each message to its loan, the agent's list of matched messages under each loan, and the
manager's decisions on which fines to waive. Matching and listing under each loan are plainly one
kind of act, both checked against the messages and the overdue list: each message sits under the
loan it is about. The waiver decisions need the judgment of someone who knows the library's
practice and its borrowers. So the only boundary goes at the handoff from the agent to the
manager.

Step 4 is `check-split`, done by the agent throughout, with its join with no change first and the
fixed side first. Its three parts are listing each borrower's books and fines, looking up how each
borrower prefers to be reached, and writing the reminders. The list of books and fines and the
contact details look like different kinds of thing, but both are checked the same way, against
the library's own records (the loans, the fines worked out in step 3, and the borrowers'
accounts). The reminders are checked by a person reading them for tone. So the only boundary goes
before the reminders. This is the Hard join: a learner may take the move from fines to contact
details as a change in the kind of check, though nothing changes there.

### q1

- **goal:** `c-divide-into-steps`
- **cases:** executor-changes
- **answer:** The boundary goes at the handoff, after the agent lists the matched messages under
  each loan and before the manager decides on waivers, not between matching and listing, since
  the agent does both and both are checked against the messages and the overdue list. It goes
  there because the executor changes from the agent to the manager, and the check changes with it:
  the matching can be checked against the messages and loans, while the waivers need judgment
  about each borrower's situation. Save the matched messages listed under each loan, so a message
  put under the wrong loan can be caught before a fine is waived or kept because of it.
- **credit:** full when the answer puts the boundary at the handoff between the agent's matched
  list and the manager's decisions; gives a reason naming the change of executor, or the change in
  the kind of check, or both; and names a saved result concrete enough to check the matching before
  the manager decides. The matched messages listed under each loan pass, and so does the matching
  of each message to its loan, since listing them under each loan only arranges it. The borrowers'
  messages, a count or summary ("how many messages came in"), or the manager's waiver decisions do
  not. Half when the boundary is at the handoff with only one of the other two: a reason that is
  missing or generic ("smaller steps are easier"), or a saved result that is missing or fails that
  test. At most half for an answer that also puts a boundary between matching and listing, since
  nothing changes there, so that boundary has no reason. None when the only boundary is between
  matching and listing, or no boundary is placed.
- **tutor note:** if they save the messages themselves, ask whether those would show which loan
  the agent put each one under.

### q2

- **goal:** `c-divide-into-steps`
- **cases:** same-executor
- **answer:** The boundary goes after the contact details are looked up and before the reminders
  are written, not between listing the fines and looking up the contact details, since the agent
  does both and both are checked against the library's records. It goes there because the kind of
  check changes: the books, fines and contact details are checked against the loans, the fines and
  the borrowers' accounts, while the reminders need a person to read them for whether they are
  friendly and clear. Save each borrower's overdue books and fines together with how they prefer to
  be reached, so all of it can be checked before any reminder is written.
- **credit:** full when the answer puts the boundary between looking up the contact details and
  writing the reminders; gives a reason naming the two kinds of check, each said even briefly
  (such as "check against the records" for one, "read for tone" for the other); and names a saved
  result concrete enough to check the listing and the lookup before the reminders are written.
  Each borrower's books and fines with their contact details passes. The list of books and fines
  alone does not, since it leaves the lookup unchecked; nor do the overdue loans, the fines from
  step 3, a count or summary ("how many borrowers owe fines"), or the reminders. Half when the
  boundary is at that join with only one of the other two: a reason that is missing, generic
  ("smaller steps are easier"), or resting only on an executor change the answer proposes (having
  the manager read the reminders), which is not in this step; or a saved result that is missing or
  fails that test. At most half for an answer that also puts a boundary between listing the fines
  and looking up the contact details, since nothing changes there, so that boundary has no reason.
  None when the only boundary is between those two, or no boundary is placed.
- **tutor note:** if they put a boundary before the lookup because "contact details are a
  different kind of thing", ask what someone would compare each against to find a mistake.
