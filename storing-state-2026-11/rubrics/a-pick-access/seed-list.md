Shape `hand-edit-runs-add`, Hard: the times must be compared (Hana's evenings from about seven
until nine against runs every hour until 11 p.m.), and Hana's action is described neutrally
("records each variety's order status"), with the contrary fact that each entry holds one value
("Each variety's entry shows one order status, its current one"). Three executors touch the seed
list: the catalog agent only adds entries; Hana changes each entry's status as she goes down the
list of about three hundred; and the planting agent takes in every entry and changes nothing. The
two writers meet at the 7, 8 and 9 p.m. runs. Each executor question asks what that executor
needs to do as the scenario describes it, not how the workflow could be redesigned.

### catalog-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "adds an entry to the seed list for each one" and "The catalog agent
  never changes an entry already on the list." It changes the list, so a reading choice alone,
  Read it through (1) or Query it (2), is not enough. It only ever adds new entries and never needs
  to change one already there, so it doesn't need Edit it (3). And since Hana changes entries
  "from about seven until nine" on most evenings, while runs start every hour until 11 p.m.,
  holding it to appending keeps it from writing over her changes.

### hana

- **goal:** `c-choose-access`
- **cases:** edit
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "Hana goes down the list and records each variety's order status" and
  "Each variety's entry shows one order status, its current one." She changes the list, so a
  reading choice alone, Read it through (1) or Query it (2), is not enough. Since each entry shows
  only its current status, recording a new one changes an entry already there rather than adding a
  new entry, so Append-only writes (4) is not enough. She finds the entries she changes by going
  down the list, about three hundred entries, so she needs no search among many.

### planting-agent

- **goal:** `c-choose-access`
- **cases:** read-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by "the planting agent reads every entry on the list and drafts a
  planting calendar showing when each variety would go in the ground." That it needs every entry,
  not particular ones, rules out Query it (2). "The planting agent changes nothing on the list and
  adds nothing to it" rules out Edit it (3) and Append-only writes (4).

### race

- **goal:** `c-choose-access`
- **cases:** race
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by comparing the writers' times: runs start "every hour from 7 a.m. to
  11 p.m." and Hana changes entries "most evenings, from about seven until nine", so the 7, 8 and
  9 p.m. runs write while she is changing entries already there. Hana and the catalog agent's runs
  (2) are in danger, so None (3) is wrong. One run of the catalog agent and the next (1) is wrong
  because a run "takes about ten minutes" and the next starts an hour later, so one run ends long
  before the next starts. The planting agent and the catalog agent's runs (4) is wrong because a
  race needs two writers and the planting agent only reads.
