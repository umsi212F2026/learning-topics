Shape `redoes-acted-on`, Medium: the picking agent writes each event's verdict in place with no test for done, and Bao has already acted on the first 26 verdicts by buying tickets.

### q1

- **goal:** `c-judge-rerunnable`
- **cases:** replaces-used
- **type:** mcq
- **answer:** 5
- **credit:** full for 5 only.
- **tutor note:** Settled by "reads every event in the list and writes a verdict ... overwriting any verdict already there" together with "Bao has read the first 26 verdicts and bought tickets for two of the shows marked 'go'": the agent judges all 41 events anew, may mark one of Bao's two shows 'maybe' or 'pass' this time, and its new verdict overwrites the one he bought tickets on, so the list and his tickets no longer agree. Not 1: an agent that rewrites every result with no test for done is not idempotent, whatever it happens to answer this time (see the check note). Not 2: the agent writes into each event's own entry and adds no entries. Not 3: the agent does nothing outside the workflow; buying the tickets was Bao's own doing. Not 4: the stop came just after the 26th verdict was finished, between events.
