Hana grows vegetables in a community garden plot and keeps a seed list of the varieties she might
grow this year. The catalog agent, following a skill file Hana wrote, picks out varieties from
the seed companies' emails; Hana keeps track of her orders on the list; and the planting agent
drafts her a calendar from it.

About this workflow: Every hour from 7 a.m. to 11 p.m., the catalog agent reads any new emails
from the seed companies Hana buys from, decides which of the varieties offered would suit her
plot, and adds an entry to the seed list for each one, with its price and days to harvest. The
catalog agent never changes an entry already on the list. A run of the catalog agent takes about
ten minutes. Most evenings, from about seven until nine, Hana goes down the list and records each
variety's order status: "to order", "ordered" or "arrived". Each variety's entry shows one order
status, its current one. Every Sunday afternoon the planting agent reads every entry on the list
and drafts a planting calendar showing when each variety would go in the ground. The planting
agent changes nothing on the list and adds nothing to it; it saves the calendar in a folder. The
list now holds about three hundred entries.

### catalog-agent

What kind of access to the seed list does the catalog agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### hana

What kind of access to the seed list does Hana need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### planting-agent

What kind of access to the seed list does the planting agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the seed list? (Two runs of the same executor count as a pair.)

1. One run of the catalog agent and the next
2. Hana and the catalog agent's runs
3. None
4. The planting agent and the catalog agent's runs
