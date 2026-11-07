Shape `takes-turns`, Hard: the timing is given only as times, for the learner to compare, and
Noor's action is described neutrally ("records her rating out of five in its entry"). The episode
agent writes from 2 a.m. until 2:30 and Noor only "between about 7 a.m. and 11 p.m.", so their
writes never meet. Three executors touch the listening list: the episode agent adds an entry for
each new episode, which it finds from her podcasts rather than in the list, and is described with a
plain verb saying it "never changes an entry already there"; Noor changes the rating in entries
already there, finding them by looking over "the newest entries at the top of the list" rather than
searching it; and the playlist program picks out particular entries from about twenty-five thousand
and changes nothing. Each executor question asks what that executor needs to do as the scenario
describes it, not how the workflow could be redesigned.

### episode-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. It "adds an entry to the listening list" for each new episode, so
  it changes the list, and a reading kind alone is not enough. It only ever adds new entries and
  never needs to change one already there, so it doesn't need edit: the scenario says it "never
  changes an entry already there".
- **credit:** full when the answer names appending as the agent's only writing kind, in any words
  ("adds only", "adds new entries"); a reading kind named beside it is fine. None when it names
  editing or changing entries (alone or with appending), names only a reading kind, or offers two
  kinds without committing to one.

### noor

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** free
- **answer:** Edit it. She "records her rating out of five in its entry", so she changes the list,
  and a reading kind alone is not enough. That rating goes into an entry already there, and "an
  entry shows one rating, her latest", so a changed rating replaces the old one; appending alone is
  not enough. She finds the entries by looking over "the newest entries at the top of the list",
  not by searching it.
- **credit:** full when the answer names editing, in any words ("changes entries", "fills in or
  updates the rating in each entry", "writes her rating into the episode's entry"); a reading kind
  named beside it is fine ("reads it and edits it"). None when it names only appending or adding
  new entries, names only a reading kind, or offers two kinds without committing to one.
- **tutor note:** "records" gives nothing away here; the facts that settle it are that the rating
  goes into the episode's own entry and that an entry shows one rating, her latest.

### playlist-program

- **goal:** `c-choose-access`
- **cases:** query
- **type:** free
- **answer:** Query it. It "picks out only that week's episodes she rated four or five" from a list
  of "about twenty-five thousand entries", so it needs particular entries out of tens of thousands,
  which rules out read it through. It "never changes or adds anything in the listening list", which
  rules out edit and append-only writes.
- **credit:** full when the answer says the program finds or picks out particular entries, in any
  words ("looks up the episodes rated four or five", "searches for them"). None for a bare reading
  answer ("reads it", "read access", "read-only"), for reading the whole list, for "reads it
  through or queries it" without committing, or for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** free
- **answer:** None. The episode agent's run starts "at 2 a.m." and "is done by 2:30"; Noor records
  ratings only "between about 7 a.m. and 11 p.m.", so the two writers never write at the same time.
  Ruled out: Noor and the episode agent, since their times never meet; the playlist program with
  either writer, since it "never changes or adds anything"; and one night's run of the episode agent
  and the next, since a half-hour run ends long before the next night's starts.
- **credit:** full for "none", in any words ("no writers", "there's no danger"). None when it names
  any pair of executors. A reason given alongside is not marked.
