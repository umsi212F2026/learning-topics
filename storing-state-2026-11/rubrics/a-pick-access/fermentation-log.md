Shape `everyone-adds`, Hard: both writers are described neutrally ("records the fermenter's
temperature", "records the beer's gravity"), so the fact that decides between append-only and
edit is "Yusuf wants every past reading kept as it was"; and the writers that do write at once
only add. Three executors touch the fermentation log: the temperature program and the gravity
program each only add readings, and on the hour both are writing; the brewing agent picks out
particular readings from about fifty thousand and changes nothing. Both writers only add, so
there is no danger of a race condition. Each executor question asks what that executor needs to
do as the scenario describes it, not how the workflow could be redesigned.

### temperature-program

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "The temperature program records the fermenter's temperature in the
  fermentation log every fifteen minutes" and "Yusuf wants every past reading kept as it was." It
  changes the log, so a reading choice alone, Full scan (1) or Query it (2), is not enough.
  Each reading is a new one and no past reading may change, so it only ever adds and never needs
  to change one already there, so it doesn't need Edit it (3). That past readings must stay as
  they were is what holds it to appending.

### gravity-program

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "The gravity program records the beer's gravity ... in the
  fermentation log once an hour" and "Yusuf wants every past reading kept as it was." It changes
  the log, so a reading choice alone, Full scan (1) or Query it (2), is not enough. Each
  reading is a new one and no past reading may change, so it only ever adds and never needs to
  change one already there, so it doesn't need Edit it (3). That past readings must stay as they
  were is what holds it to appending; the temperature program also writes on the hour, while it
  does.

### brewing-agent

- **goal:** `c-choose-access`
- **cases:** query
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "the brewing agent picks out only the past day's readings for the
  batch now in the fermenter" and "The log now holds about fifty thousand readings." That it needs
  particular readings out of tens of thousands rules out Full scan (1). "The brewing agent
  changes nothing in the log and adds nothing to it" rules out Edit it (3) and Append-only writes
  (4).

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by the two writers' times and what they do: the temperature program
  records "every fifteen minutes, starting on the hour" and the gravity program "once an hour, on
  the hour", so on the hour both are writing, but each only adds a new reading and "Yusuf wants
  every past reading kept as it was", so neither changes what is already there. The temperature
  program and the gravity program (1) is wrong because both only add. The brewing agent and the
  gravity program (2), and the brewing agent and the temperature program (3), are wrong because a
  race needs two writers and the brewing agent only reads, even though its 7 a.m. run falls on the
  hour.
