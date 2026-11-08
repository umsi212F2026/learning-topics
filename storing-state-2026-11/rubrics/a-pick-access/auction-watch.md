Shape `runs-overlap-change`, Hard: the times must be compared (a run every hour that during a big
sale takes about seventy-five minutes). Three executors touch the watch list: the bid-watch agent
replaces every lot's current bid and verdict on each run; Gus only adds new lots, on Saturday
mornings between 9 and 11, when no runs happen; and the report program takes in every entry and
changes nothing. The last run before the Saturday pause starts at 5 a.m. and is done by 6:15 at
the latest, and runs resume at noon, so Gus's times never meet a run. Each executor question asks
what that executor needs to do as the scenario describes it, not how the workflow could be
redesigned.

### bid-watch-agent

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "Each run checks every lot on the watch list and replaces each lot's
  current bid and its bid-or-pass verdict with the latest ones" and "Each lot's entry shows one
  current bid and one verdict." It changes the list, so a reading choice alone, Full scan
  (1) or Query it (2), is not enough. It changes entries already there rather than adding new
  ones, so Append-only writes (4) is not enough. It changes every entry its run checks, so it
  needs no search among many.

### gus

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "Gus adds new lots to the watch list ... and never changes an entry."
  He changes the list, so a reading choice alone, Full scan (1) or Query it (2), is not
  enough. He only ever adds new entries and never needs to change one already there, so he doesn't
  need Edit it (3). No other writer writes while he does and no rule keeps past entries as they
  were; what holds him to appending is that plain statement that he never changes an entry.

### report-program

- **goal:** `c-choose-access`
- **cases:** read-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by "the report program goes over every entry on the watch list and
  emails Gus a table of all the lots." That it needs every entry, not particular ones, rules out
  Query it (2). "The report program changes nothing on the list and adds nothing to it" rules out
  Edit it (3) and Append-only writes (4).

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by comparing "starts a run every hour, on the hour" with "during a big
  sale ... a run takes about seventy-five minutes": a seventy-five-minute run is still going when
  the next starts, and both replace the same lots' bids and verdicts, so one run of the bid-watch
  agent and the next (4) are in danger. None (2) is wrong for that reason. Gus and the bid-watch
  agent's runs (1) is wrong because their times never meet: there are no runs "on Saturday
  mornings from 6 a.m. to noon", Gus adds lots only "between 9 and 11" then, and the last run
  before the pause, started at 5 a.m., is done by 6:15 even on a long day. The report program and
  the bid-watch agent's runs (3) is wrong because a race needs two writers and the report program
  only reads.
