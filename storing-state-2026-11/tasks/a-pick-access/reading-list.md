Ana subscribes to many newsletters and keeps a reading list of the articles she wants to read. The
newsletter agent, following a skill file Ana wrote, picks out articles from the newsletters in her
inbox; a feed program collects new posts from writers she follows; and a digest program lays out
each week's reading for her.

About this workflow: Every thirty minutes, on the hour and the half hour, the newsletter agent
reads the new newsletters in Ana's inbox, picks out the articles on topics she follows, and adds
an entry to the reading list for each one, with its title and link. Every hour, on the hour, the
feed program adds an entry to the reading list for each new post on a dozen writers' sites Ana
follows. A run of either takes about five minutes, so on the hour both are adding entries at once.
Neither the newsletter agent nor the feed program ever changes an entry already on the list.
Every Sunday morning the digest program picks out only the past week's entries and lays them out
on one page for Ana to read. The digest program changes nothing on the list and adds nothing to
it. The list now holds about twenty-four thousand entries, from four years of reading.

### newsletter-agent

What kind of access to the reading list does the newsletter agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### feed-program

What kind of access to the reading list does the feed program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### digest-program

What kind of access to the reading list does the digest program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the reading list? (Two runs of the same executor count as a pair.)

1. The digest program and the newsletter agent
2. None
3. The newsletter agent and the feed program
4. The digest program and the feed program
