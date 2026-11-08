Gus collects stamps and keeps a watch list of lots he might bid on at an online stamp auction
site. The bid-watch agent, following a skill file Gus wrote, checks each lot on the site and
judges whether it is still worth a bid; Gus adds lots to watch; and a report program sends him a
weekly summary.

About this workflow: The bid-watch agent starts a run every hour, on the hour, except on Saturday
mornings from 6 a.m. to noon, when the auction site is closed for upkeep. Each run checks every
lot on the watch list and replaces each lot's current bid and its bid-or-pass verdict with the
latest ones. Each lot's entry shows one current bid and one verdict, since only the latest matter
to Gus. Most runs take about forty minutes, but during a big sale, when many lots are drawing
bids, a run takes about seventy-five minutes. Gus adds new lots to the watch list only on Saturday
mornings between 9 and 11, as he goes through the week's new sale catalogs, and never changes an
entry. Every Sunday evening the report program goes over every entry on the watch list and emails
Gus a table of all the lots with their current bids and verdicts. The report program changes
nothing on the list and adds nothing to it. The list now holds about eighty entries.

### bid-watch-agent

What kind of access to the watch list does the bid-watch agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### gus

What kind of access to the watch list does Gus need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### report-program

What kind of access to the watch list does the report program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the watch list? (Two runs of the same executor count as a pair.)

1. Gus and the bid-watch agent's runs
2. None
3. The report program and the bid-watch agent's runs
4. One run of the bid-watch agent and the next
