Steps 2 and 4 are the lumped ones. Step 2 is `check-split`: the same agent does all three parts.
Picking out each patient's choice of text or email and making the sending list are both checked
against the appointments and the patient records (every appointment appears once, with the right
time, dentist and choice), so there is no boundary between them, though they produce things that
look different. The reminders need a person to read them for tone and clarity, so the boundary
goes before the reminders, and the sending list is what lets the first two parts be checked
before any reminder is written. Step 4 is `handoff-split`: the agent's marks can be checked
against what each reply says, while the manager's two choices are judgment calls, checked by
someone who knows the patients and the schedule. Its join with no change is between the
manager's two choices.

### q1

- **goal:** `c-divide-into-steps`
- **cases:** same-executor
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** make-up `both-right-join`, Hard. All three split at the same place, so only what
  is kept tells them apart. If they chose Ben's, ask whether the appointment list alone would show
  that a patient who wants email was put down for a text. If they chose Chloe's, ask what a count
  would show about which patient got which choice.

### q2

- **goal:** `c-divide-into-steps`
- **cases:** executor-changes
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** make-up `both-wrong-join`, Medium. Daniel and Elena both split between two of the
  manager's own choices, where nothing changes, and leave the agent's marking inside the
  manager's step. If they chose Daniel's because his list sounds careful, ask who does each part
  of step 4 and how each would be checked.
