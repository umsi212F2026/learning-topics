Step 2 is `messy-volume-checked`: natural choice an AI agent, alternative a person. Step 4 is
`structured-irreversible`: natural choice a program, alternative an AI agent. Rule on the reasons,
never on the choice: any executor defended by reasons tied to the step's facts passes.

Where the facts are. The setup's second sentence gives the volume: well over a hundred requests in
a busy week, which is also roughly how many refunds reach step 4. In the manager's paragraph,
sentences 2 to 4 carry step 2's facts: the requests are typed free text in mixed lengths, many
name the show but not the night (sentence 2, its input); they carry health details (sentence 3,
its data); a request in the wrong pile is nearly always caught at step 3 (sentence 4, what a
mistake costs). Sentences 5 and 6 carry step 4's facts: the approved list has one line per refund
in a fixed form, with a few lines a week carrying a note such as "half, see email" where the
amount should be, and each line holds a card number (sentence 5, its input and its data); a wrong
amount comes out of the theater's account and nobody looks at it again (sentence 6, what a mistake
costs).

The irrelevant details, one per open step: for step 2, the form's heading, "Sorry you can't make
it!" (sentence 1); for step 4, that refunds went to cards rather than checks two seasons ago
(sentence 7). A reason resting on either is not tied.

### q1

- **goal:** `c-assign-a-lane`
- **answer:** An AI agent rather than the manager. It helps timeliness or cost: well over a hundred
  requests a week, typed in patrons' own words and of mixed length, would take the manager hours
  to read and sort. It hurts privacy: the requests carry health details, which would go to the
  agent's provider; or it hurts correctness: many requests name the show but not the night, and
  the agent may guess the night wrong (a slip the manager nearly always catches at step 3, which
  is also a tied reason the agent's mistakes are tolerable here). Other pairings that pass:
  - The manager rather than an agent: helps privacy (the health details stay inside the theater)
    or correctness (the manager can tell, or ask, which night a patron meant); hurts timeliness or
    the manager's time (over a hundred typed requests a week).
  - An agent rather than a program: helps correctness (the requests are free text in patrons' own
    words, which a program can't sort by the policy); hurts privacy (a program keeps the health
    details in-house) or cost (an agent costs more per run).
  - A program rather than an agent: helps privacy (the health details go nowhere) or cost; hurts
    correctness (free text in mixed styles, so much would land in the wrong pile and the manager
    would spend step 3 fixing it).
  - The manager rather than a program: helps correctness (reading free text and the missing
    nights); hurts timeliness (the volume).
  - A program rather than the manager: helps timeliness (the volume); hurts correctness (free
    text a program can't read).
- **credit:** full when the answer chooses an executor for step 2, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the requests being typed free text, their volume, the
  missing nights, the health details, or the step 3 review that catches a wrong pile. A reason is
  tied when it would not hold for that executor on a step with different facts. Generic reasons,
  which fail even when they mention the requests: "an agent is faster at sorting these requests",
  "a person has better judgment", "agents can be wrong in ways that look right". A reason resting
  on the form's heading is not tied. An intermediate goal from the reading counts as a goal helped
  or hurt when its reason is tied to a fact here. Half when one of the two is tied and the other
  is generic or missing, or when both are tied but no alternative is named. None when neither is
  tied, or no executor is chosen.
- **tutor note:** a learner who names privacy as hurt without saying what is private ("agents send
  data to a provider") has given a reason that holds for any agent step; ask what in these
  requests would be going to the provider.

### q2

- **goal:** `c-assign-a-lane`
- **answer:** A program rather than an AI agent. It helps correctness: it sends exactly the amount
  on the approved list, every time, and a wrong amount here comes out of the theater's account
  with nobody looking at it again. It hurts timeliness or the manager's time: the few lines a week
  with a note such as "half, see email" where the amount should be will stop it, and someone has
  to sort them out by hand. Other pairings that pass:
  - An agent rather than a program: helps timeliness (it can read a note like "half, see email"
    and keep going); hurts correctness (it may misread a note or an amount, and a wrong refund is
    never caught) or privacy (the card numbers go to the agent's provider).
  - A program rather than the manager: helps timeliness or the manager's time (over a hundred
    refunds a week keyed in by hand otherwise) or correctness (no typing slip in an amount nobody
    rechecks); hurts timeliness on the note lines it stops on.
  - The manager rather than a program: helps correctness on the note lines (the manager can read
    the email the note points to); hurts timeliness or the manager's time (the volume) or
    correctness (a typing slip goes out unchecked).
  - An agent rather than the manager: helps timeliness (the volume); hurts privacy (the card
    numbers go to the provider) or correctness (an unchecked misread amount).
  - The manager rather than an agent: helps privacy (the card numbers stay in the theater);
    hurts timeliness (the volume).
- **credit:** full when the answer chooses an executor for step 4, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the approved list's fixed form, the note lines where an
  amount should be, the card numbers, the volume, or a wrong amount leaving the theater's account
  with nobody looking again. A reason is tied when it would not hold for that executor on a step
  with different facts. Generic reasons, which fail even when they mention the refunds: "programs
  don't make mistakes", "a program costs almost nothing to run for these refunds", "an agent is
  cheaper than paying the manager". A reason resting on the switch from checks to cards is not
  tied. An intermediate goal from the reading counts on the same terms: "a program fails loudly on
  the note lines instead of guessing the amount" is tied; "a program fails loudly" alone is
  generic. Half when one of the two is tied and the other is generic or missing, or when both are
  tied but no alternative is named. None when neither is tied, or no executor is chosen.
- **tutor note:** a learner who says a program hurts nothing has missed the note lines; ask what
  a program would do with a line that says "half, see email".
