Shape `everyone-adds`, Medium: the timing is said plainly ("often while a run is going") and each
writer's need is said in words close to its kind ("adds an entry"). Three executors touch the bills
record: the bill agent adds an entry for each new statement, which it finds in the statements saved
from email; Rosa adds an entry for each paper bill that came that day; and the budget program takes
in every entry and changes nothing. Both writers only add, and Rosa "wants every entry left exactly
as it was entered". The download program saves statements into a folder and never touches the
record, so no question asks about it. Each executor question asks what that executor needs to do as
the scenario describes it, not how the workflow could be redesigned.

### bill-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. It "adds an entry to the bills record" for each new statement, so
  it changes the record, and a reading kind alone is not enough. It only ever adds new entries and
  never needs to change one already there, so it doesn't need edit. And Rosa "wants every entry left
  exactly as it was entered", so holding it to appending keeps every past entry as it was; she also
  adds entries "often while a run is going".
- **credit:** full when the answer names appending as the agent's only writing kind, in any words
  ("adds only", "adds new entries"); a reading kind named beside it is fine. None when it names
  editing or changing entries (alone or with appending), names only a reading kind, or offers two
  kinds without committing to one.

### rosa

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. She "adds an entry by hand for each paper bill", so she changes
  the record, and a reading kind alone is not enough. She only adds new entries and never needs to
  change one already there, so she doesn't need edit. And she "wants every entry left exactly as it
  was entered", so holding her to appending keeps every past entry as it was; she also adds hers
  "often while a run is going".
- **credit:** full when the answer names appending as Rosa's only writing kind, in any words ("adds
  only", "adds new entries"); a reading kind named beside it is fine. None when it names editing or
  changing entries (alone or with appending), names only a reading kind, or offers two kinds
  without committing to one.
- **tutor note:** a learner who answers "edit" because Rosa is the person, as in other scenarios,
  has missed that she only ever adds entries.

### budget-program

- **goal:** `c-choose-access`
- **cases:** read-through
- **type:** free
- **answer:** Read it through. It "goes over the whole bills record" to add up "what the household
  has spent in each category so far this year", and the record holds only this year's bills, so it
  needs every entry, which rules out query. It "never changes or adds anything in the bills
  record", which rules out edit and append-only writes.
- **credit:** full when the answer says the program takes in the whole record, in any words ("reads
  all of it", "goes through every entry"). None for a bare "read access" or "read-only", for
  querying or picking out particular entries, for "reads it through or queries it" without
  committing, or for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** free
- **answer:** None. Rosa adds entries "often while a run is going", so she and the bill agent's runs
  write at the same time, but both only add entries and neither changes one already there, so
  neither can wipe out the other's work. Ruled out: Rosa and the bill agent's runs, since both only
  add; the budget program with either writer, since it "never changes or adds anything"; and one run
  of the bill agent and the next, since both only add and a fifteen-minute run ends long before the
  next starts an hour later.
- **credit:** full for "none", in any words ("no writers", "there's no danger"). None when it names
  any pair of executors. A reason given alongside is not marked.
- **tutor note:** a learner who names Rosa and the bill agent has seen that they write at once but
  not that a race needs one of them to change what is already there.
