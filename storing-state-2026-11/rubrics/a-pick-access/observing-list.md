Shape `takes-turns`, Medium. The observing list has three executors: two writers and one reader.
The finder agent only adds entries ("never changes an entry already on the list") and writes
only on Monday from 6 to 6:20 a.m. Dara changes entries already there, marking them "seen", and
only on Saturday nights. The print program takes in every entry on Fridays and changes nothing.
The two writers' times never meet, so there is no danger of a race condition. Each executor
question asks what that executor needs to do as the scenario describes it, not how the workflow
could be redesigned.

### finder-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "adds an entry to the observing list for each one worth looking
  for" and "The finder agent never changes an entry already on the list." It changes the list,
  so a reading choice alone, Full scan (1) or Query it (2), is not enough. It only ever
  adds new entries and never needs to change one already there, so it doesn't need Edit it (3).
  No other writer writes while it runs and no rule keeps past entries as they were; what holds it
  to appending is that plain statement that it never changes an entry.

### dara

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "Dara changes entries only on Saturday nights, ... marking each
  object she found that night as 'seen'." She changes the list, so a reading choice alone, Full scan
  (1) or Query it (2), is not enough. She changes entries already there rather than
  adding new ones, so Append-only writes (4) is not enough. She finds her entries as she looks
  the list over, so she needs no search among many.

### print-program

- **goal:** `c-choose-access`
- **cases:** full-scan
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by "the print program goes over every entry on the list and prints
  them all." That it needs every entry, not particular ones, rules out Query it (2). "The print
  program changes nothing on the list and adds nothing to it" rules out Edit it (3) and
  Append-only writes (4).

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by the two writers' times: "The finder agent runs once a week, starting
  at 6 a.m. on Monday, and is done by 6:20" and "Dara changes entries only on Saturday nights."
  The finder agent and Dara (3) are the only two writers, but their times never meet. The finder
  agent and the print program (2), and Dara and the print program (4), are wrong because a race
  needs two writers and the print program only reads the list.
