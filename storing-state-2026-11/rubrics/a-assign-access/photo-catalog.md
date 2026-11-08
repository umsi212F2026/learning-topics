Shape `everyone-adds`, Hard: the timing is given only as times, for the learner to compare, and the
tagging agent's action is described neutrally ("records the photo in the photo catalog"). Runs start
"every hour" and a run "can take two hours", so after a party or a holiday weekend one run is still
going when the next one or two start, and the runs write at the same time. Two executors touch the
catalog: the tagging agent, whose runs each add an entry for every photo copied in that hour, which
it finds in the folder rather than in the catalog; and the calendar program, which picks out
particular entries from about seventy thousand and changes nothing. The copying program puts photos
into a folder and never touches the catalog, so no question asks about it. Each executor question
asks what that executor needs to do as the scenario describes it, not how the workflow could be
redesigned.

### tagging-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. It "records the photo in the photo catalog" for each photo copied
  in that hour, so it changes the catalog, and a reading kind alone is not enough. Each of those is
  a new photo, so it only ever adds new entries and never needs to change one already there, and it
  doesn't need edit. And since runs start "every hour" and one "can take two hours", several runs
  write at the same time, so holding each to appending keeps one run from writing over another's
  entries.
- **credit:** full when the answer names appending as the agent's only writing kind, in any words
  ("adds only", "adds new entries", "adds a record for each photo"); a reading kind named beside it
  is fine. None when it names editing or changing entries (alone or with appending), names only a
  reading kind, or offers two kinds without committing to one.

### calendar-program

- **goal:** `c-choose-access`
- **cases:** query
- **type:** free
- **answer:** Query it. It "picks out only that year's photos tagged with both of Greta's
  grandchildren" from a catalog of "about seventy thousand", so it needs particular entries out of
  tens of thousands, which rules out a full scan. It "never changes or adds anything in the
  photo catalog", which rules out edit and append-only writes.
- **credit:** full when the answer says the program finds or picks out particular entries, in any
  words ("looks up the photos with both grandchildren", "searches for them"). None for a bare
  reading answer ("reads it", "read access", "read-only"), for reading the whole catalog, for
  "a full scan or a query" without committing, or for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** free
- **answer:** None. Runs start "every hour" and one "can take two hours", so two runs of the tagging
  agent can write at the same time, but each only adds entries for its own new photos and never
  changes one already there, so neither can wipe out the other's work. Ruled out: one run of the
  tagging agent and the next, since both only add; and the calendar program with the tagging agent,
  since it "never changes or adds anything".
- **credit:** full for "none", in any words ("no writers", "there's no danger"). None when it names
  any pair of executors, including two runs of the tagging agent. A reason given alongside is not
  marked.
- **tutor note:** a learner who names two runs of the tagging agent has found the overlap but not
  that a race needs one of the writers to change what is already there.
