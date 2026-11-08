Shape `hand-edit-runs-add`, Medium: the timing is said plainly ("often while a run is going") and
each executor's need is said in words close to its kind. Three executors touch the recipe list:
the recipe agent adds entries at its end; Lena changes that day's new entries, which she finds by
looking over the end of the list rather than searching it; and the planning program picks out
particular entries from about twenty-two thousand and changes nothing. The download program saves
posts into a folder and never touches the list, so no question asks about it. Each executor
question asks what that executor needs to do as the scenario describes it, not how the workflow
could be redesigned.

### recipe-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** free
- **answer:** Append-only writes. It "adds an entry at the end of the recipe list for each one worth
  keeping", so it changes the list, and a reading kind alone is not enough. It only ever adds new
  entries and never needs to change one already there, so it doesn't need edit. And since Lena
  changes entries "often while a run is going", the agent should leave entries already there
  alone.
- **credit:** full when the answer names appending as the agent's only writing kind, in any words
  ("adds only", "adds new entries"); a reading kind named beside it is fine. None when it names
  editing or changing entries (alone or with appending), names only a reading kind, or offers two
  kinds without committing to one.

### lena

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** free
- **answer:** Edit it. She "fixes any cooking time the agent got wrong, and marks the dishes she
  wants to make 'this week'", so she changes the list, and a reading kind alone is not enough. Those
  are changes to entries already there, so appending alone is not enough. She finds them by looking
  over "that day's new entries at the end of the list", not by searching the whole list.
- **credit:** full when the answer names editing, in any words ("changes entries", "updates them");
  a reading kind named beside it is fine ("reads it and edits it"), and so is editing plus appending
  ("edits it and appends"). None when it names only appending, names only a reading kind, or offers
  two kinds without committing to one.

### planning-program

- **goal:** `c-choose-access`
- **cases:** query
- **type:** free
- **answer:** Query it. It "picks out only the entries marked 'this week'" from a list of "about
  twenty-two thousand entries", so it needs particular entries out of tens of thousands, which
  rules out a full scan. It "never changes or adds anything in the recipe list", which rules
  out edit and append-only writes.
- **credit:** full when the answer says the program finds or picks out particular entries, in any
  words ("looks up the ones marked 'this week'", "searches for them"). None for a bare reading
  answer ("reads it", "read access", "read-only"), for reading the whole list, for "a full scan or a
  query" without committing, or for any writing kind.

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** free
- **answer:** Lena and the recipe agent's runs. The runs start "every two hours from 7 a.m. to 11
  p.m." and each "takes about fifteen minutes"; Lena makes her changes "most evenings, often while a
  run is going". One writer changes what is already there while the other writes, so Lena's save can
  lose the agent's new entries, even though the agent only adds. Naming the recipe agent, its runs,
  or "the runs" for that writer all count. Ruled out: the planning program with either writer, since
  the planning program "never changes or adds anything"; and one run of the recipe agent and the
  next, since a fifteen-minute run ends long before the next starts two hours later.
- **credit:** full when the answer names Lena and the recipe agent (or its runs) as the pair, and
  only that pair. None when it says "none", names a pair the facts rule out, or adds the planning
  program or the download program to the right pair. A reason given alongside is not marked.
