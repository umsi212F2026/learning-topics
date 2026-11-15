Shape `redoes-acted-on`, Hard: the one acting on the results is a later step, the shortlist program, not Ines, and the run stopped in the middle of writing one listing's rating. The rating agent writes each listing's rating in place with no test for done, so a rerun asks it to judge all 48 listings anew, and an agent may judge a listing otherwise when asked a second time. The shortlist program has already acted on the first 30 ratings.

### q1

- **goal:** `c-judge-rerunnable`
- **cases:** replaces-used
- **type:** mcq
- **answer:** 5
- **credit:** full for 5 only.
- **tutor note:** Settled by "reads every listing in the list on each run, passing over none, and writes a rating ... overwriting any rating already there" together with "the shortlist program put five listings rated 'buy now' onto Wednesday's shortlist": the agent rates listings 1 to 30 anew, may rate one of the five 'maybe' or 'skip' this time, or another 'buy now', and its new rating overwrites the one the shortlist was built from, so the ratings and Wednesday's shortlist no longer agree. Not 1: an agent that rewrites every result with no test for done is not idempotent, whatever it happens to answer this time (see the check note). Not 2: the agent writes each listing's rating into that listing's own row and adds no rows. Not 3: the agent does nothing outside the workflow; the shortlist is a kept list inside it. Not 4: the rerun rewrites every listing's rating, the 31st's included, and the five on the shortlist were all among the first 30, so nothing has relied on the 31st's unfinished rating. A learner who picks 4 has spotted the stop in the middle of writing; ask what the rerun does to the 31st listing's row.
