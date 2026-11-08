Shape `runs-overlap-change`, Medium: the timing is said plainly ("it is still going when the next
one starts") and the price agent's action is said in words that change entries already there
("replaces the entry's lowest price"). Two executors touch the game list: the price agent changes
every one of its forty entries on each run, so it has no entries to find among many; and Kofi takes
in every entry and changes nothing. The download program saves shop pages into a folder and never
touches the list, so no question asks about it. Each executor question asks what that executor needs
to do as the scenario describes it, not how the workflow could be redesigned.

### price-agent

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** free
- **answer:** Edit it. It "replaces the entry's lowest price" and "replaces its verdict with a new
  one" for every game on the list, so it changes the list, and a reading kind alone is not enough.
  Those are changes to entries already there, and "only the current price and verdict matter", so
  appending alone is not enough. It works on every entry, all forty, so it finds them without
  searching.
- **credit:** full when the answer names editing, in any words ("changes entries", "updates each
  game's price and verdict"); a reading kind named beside it is fine ("reads it and edits it"), and
  so is editing plus appending ("edits it and appends"). None when it names only appending, names
  only a reading kind, or offers two kinds without committing to one.

### kofi

- **goal:** `c-choose-access`
- **cases:** full-scan
- **type:** free
- **answer:** Full scan. He "reads the whole game list, all forty entries", so he needs every
  entry, which rules out query. He "never changes or adds anything in it", which rules out edit and
  append-only writes.
- **credit:** full when the answer says Kofi takes in the whole list, in any words ("a full scan",
  "reads all of it", "goes through every entry"). None for a bare "read access" or "read-only", for
  querying or picking out particular entries, for "a full scan or a query" without committing, or
  for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** free
- **answer:** One run of the price agent and the next. Runs start "every 30 minutes", and on slow
  evenings a run "takes nearly an hour, so it is still going when the next one starts"; each run
  replaces every entry's price and verdict, so two runs change the same entries at the same time.
  Naming "two runs of the price agent", "one run and the next", the price agent alone, or the price
  agent "with itself" all count, since it is the only writer in danger. Ruled out: Kofi and the
  price agent's runs, since Kofi "never changes or adds anything".
- **credit:** full when the answer names the price agent's runs (in any of the ways above) as the
  pair, and only that pair. None when it says "none", names Kofi or the download program as one of
  the pair, or adds a pair to the right one. A reason given alongside is not marked.
- **tutor note:** a learner who answers "none" because there is only one writer has missed that a
  run still going when the next starts makes two writers.
