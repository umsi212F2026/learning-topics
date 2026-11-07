Dara keeps an observing list of the sky objects she wants to find with her backyard telescope.
The finder agent, following a skill file Dara wrote, judges the objects mentioned in new posts on
an astronomy forum she follows; Dara marks off what she finds; and a print program makes her a
sheet to take outside.

About this workflow: The finder agent reads each new post on the forum, decides whether the
object it mentions can be seen from Dara's backyard with her telescope, and adds an entry to the
observing list for each one worth looking for, with its name and the best month to see it. The
finder agent never changes an entry already on the list. The finder agent runs once a week,
starting at 6 a.m. on Monday, and is done by 6:20. Dara changes entries only on Saturday nights,
after she comes in from observing, looking the list over and marking each object she found that
night as "seen". Every Friday afternoon the print program goes over every entry on the list and
prints them all on a sheet for Dara to take outside. The print program changes nothing on the
list and adds nothing to it. The list now holds about four hundred entries.

### finder-agent

What kind of access to the observing list does the finder agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### dara

What kind of access to the observing list does Dara need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### print-program

What kind of access to the observing list does the print program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the observing list?

1. None
2. The finder agent and the print program
3. The finder agent and Dara
4. Dara and the print program
