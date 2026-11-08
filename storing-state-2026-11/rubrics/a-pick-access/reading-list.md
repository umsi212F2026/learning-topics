Shape `everyone-adds`, Medium: the timing is said plainly ("on the hour both are adding entries at
once") and each writer's need is said in words close to its kind ("adds an entry"). Three
executors touch the reading list: the newsletter agent and the feed program each only add
entries, and on the hour both are writing; the digest program picks out particular entries from
about twenty-four thousand and changes nothing. Both writers only add, so there is no danger of a
race condition. Each executor question asks what that executor needs to do as the scenario
describes it, not how the workflow could be redesigned.

### newsletter-agent

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "adds an entry to the reading list for each one" and "Neither the
  newsletter agent nor the feed program ever changes an entry already on the list." It changes
  the list, so a reading choice alone, Full scan (1) or Query it (2), is not enough. It only
  ever adds new entries and never needs to change one already there, so it doesn't need Edit it
  (3). And since the feed program writes at the same time ("on the hour both are adding entries at
  once"), holding it to appending keeps it from writing over the other's entries.

### feed-program

- **goal:** `c-choose-access`
- **cases:** append-only
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only; none for the others.
- **tutor note:** settled by "the feed program adds an entry to the reading list for each new
  post" and "Neither the newsletter agent nor the feed program ever changes an entry already on
  the list." It changes the list, so a reading choice alone, Full scan (1) or Query it (2),
  is not enough. It only ever adds new entries and never needs to change one already there, so it
  doesn't need Edit it (3). And since the newsletter agent writes at the same time ("on the hour
  both are adding entries at once"), holding it to appending keeps it from writing over the
  other's entries.

### digest-program

- **goal:** `c-choose-access`
- **cases:** query
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "the digest program picks out only the past week's entries" and "The
  list now holds about twenty-four thousand entries." That it needs particular entries out of tens
  of thousands rules out Full scan (1). "The digest program changes nothing on the list and
  adds nothing to it" rules out Edit it (3) and Append-only writes (4).

### race

- **goal:** `c-choose-access`
- **cases:** no-race
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "on the hour both are adding entries at once" together with "Neither
  the newsletter agent nor the feed program ever changes an entry already on the list": the two
  writers do write at the same time, but both only add, so neither can wipe out the other's work.
  The newsletter agent and the feed program (3) is wrong because both only add. The digest
  program and the newsletter agent (1), and the digest program and the feed program (4), are wrong
  because a race needs two writers and the digest program only reads.
