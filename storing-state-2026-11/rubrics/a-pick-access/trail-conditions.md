Shape `hand-edit-runs-add`, Medium: the timing is said plainly ("often while a run is going") and
each executor's need is said in words close to its kind. Three executors touch the conditions
record: the conditions agent only adds entries, in hourly ten-minute runs; Omar fixes trail names
in that day's new entries, which he finds at the end of the record, most evenings, often while a
run is going; and the planning program picks out particular entries from about thirty thousand
and changes nothing. The download program saves posts into a folder and never touches the
record, so no question asks about it. Each executor question asks what that executor needs to do
as the scenario describes it, not how the workflow could be redesigned.

### conditions-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "the conditions agent adds an entry to the conditions record" and
  "The conditions agent never changes an entry already in the record." It changes the record, so
  a reading choice alone, Read it through (1) or Query it (2), is not enough. It only ever adds
  new entries and never needs to change one already there, so it doesn't need Edit it (3). And
  since Omar changes entries "often while a run is going", holding it to appending keeps it from
  writing over his fixes.

### omar

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "Omar looks over that day's new entries at the end of the record and
  fixes any trail name the agent got wrong." He changes the record, so a reading choice alone,
  Read it through (1) or Query it (2), is not enough. Fixing a trail name changes an entry already
  there rather than adding a new one, so Append-only writes (4) is not enough. He finds the entries
  he fixes by looking over that day's new ones at the end of the record, so he needs no search
  among the thirty thousand.

### planning-program

- **goal:** `c-choose-access`
- **cases:** query
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "the planning program picks out only the past two weeks' entries for
  the trails on Omar's weekend shortlist" and "The record now holds about thirty thousand
  entries." That it needs particular entries out of tens of thousands rules out Read it through
  (1). "The planning program changes nothing in the record and adds nothing to it" rules out Edit
  it (3) and Append-only writes (4).

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "Most evenings, often while a run is going, Omar looks over that
  day's new entries ... and fixes any trail name", against runs "every hour from 6 a.m. to 10
  p.m.". Omar changes entries already there while a run is writing, so Omar and the conditions
  agent's runs (3) are in danger. None (1) is wrong for that reason. Omar and the planning
  program (2) is wrong because a race needs two writers and the planning program only reads. One
  run of the conditions agent and the next (4) is wrong because a run "takes about ten minutes"
  and the next starts an hour later, so one run ends long before the next starts.
