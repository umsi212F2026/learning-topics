Shape `hand-edit-runs-add`, Hard: the timing is given only as times, for the learner to compare.
The runs start "every hour from 7 a.m. to 11 p.m." and take "about ten minutes", and Omar changes
entries "from about 7:30 until about nine", so the 8 o'clock run is going while he works. Three
executors touch the bike list: the bike agent adds entries for new listings, which it finds in the
listings saved from the site; Omar changes entries already there, finding them by going down the
list of about sixty from the top rather than searching it; and the summary program takes in every
entry and changes nothing. The download program saves listings into a folder and never touches
the list, so no question asks about it. Each executor question asks what that executor needs to do
as the scenario describes it, not how the workflow could be redesigned.

### bike-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. It "adds an entry to the bike list for each one worth a look", so
  it changes the list, and a reading kind alone is not enough. It only ever adds new entries and
  never needs to change one already there, so it doesn't need edit. And since Omar changes entries
  "from about 7:30 until about nine" while the 8 o'clock run is going, the agent should leave
  entries already there alone.
- **credit:** full when the answer names appending as the agent's only writing kind, in any words
  ("adds only", "adds new entries"); a reading kind named beside it is fine. None when it names
  editing or changing entries (alone or with appending), names only a reading kind, or offers two
  kinds without committing to one.

### omar

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** free
- **answer:** Edit it. He "changes an entry's status to 'messaged'" and later "to 'gone'", so he
  changes the list, and a reading kind alone is not enough. Those are changes to entries already
  there, so appending alone is not enough. He finds them by going "down the bike list from the
  top", a list of about sixty, not by searching it.
- **credit:** full when the answer names editing, in any words ("changes entries", "updates their
  status"); a reading kind named beside it is fine ("reads it and edits it"), and so is editing plus
  appending ("edits it and appends"). None when it names only appending, names only a reading kind,
  or offers two kinds without committing to one.

### summary-program

- **goal:** `c-choose-access`
- **cases:** read-through
- **type:** free
- **answer:** Full scan. It "goes over the whole bike list" to make a table "of every bike on
  it", so it needs every entry, which rules out query. It "never changes or adds anything in the
  bike list", which rules out edit and append-only writes.
- **credit:** full when the answer says the program takes in the whole list, in any words ("a full
  scan", "reads all of it", "goes through every entry"). None for a bare "read access" or
  "read-only", for querying or picking out particular entries, for "a full scan or a query" without
  committing, or for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** free
- **answer:** Omar and the bike agent's runs. The runs start "every hour from 7 a.m. to 11 p.m." and
  each "takes about ten minutes"; Omar changes entries "from about 7:30 until about nine", so the 8
  o'clock run is going while he works. One writer changes what is already there while the other
  writes, so Omar's save can lose the agent's new entries, even though the agent only adds. Naming
  the bike agent, its runs, or "the runs" for that writer all count. Ruled out: the summary program
  with either writer, since it "never changes or adds anything"; and one run of the bike agent and
  the next, since a ten-minute run ends long before the next starts an hour later.
- **credit:** full when the answer names Omar and the bike agent (or its runs) as the pair, and
  only that pair. None when it says "none", names a pair the facts rule out, or adds the summary
  program or the download program to the right pair. A reason given alongside is not marked.
- **tutor note:** a learner who answers "none" has usually not set Omar's evening hours against
  the hourly runs.
