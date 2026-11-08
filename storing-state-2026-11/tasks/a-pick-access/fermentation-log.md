Yusuf brews beer at home and keeps a fermentation log of readings from the batch in his
fermenter. Two programs on his laptop take readings from sensors in the fermenter, and the
brewing agent, following a skill file Yusuf wrote, checks each morning how the batch is doing.

About this workflow: The temperature program records the fermenter's temperature in the
fermentation log every fifteen minutes, starting on the hour. The gravity program records the
beer's gravity, a measure of how much sugar is left in it, in the fermentation log once an hour,
on the hour. Each program takes under a minute to take its reading and record it. Yusuf wants every
past reading kept as it was, so he can see how each batch fermented. Each morning at 7 the brewing
agent picks out only the past day's readings for the batch now in the fermenter and tells Yusuf
whether it is on track. The brewing agent changes nothing in the log and adds nothing to it. The
log now holds about fifty thousand readings, from five years of batches.

### temperature-program

What kind of access to the fermentation log does the temperature program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### gravity-program

What kind of access to the fermentation log does the gravity program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### brewing-agent

What kind of access to the fermentation log does the brewing agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the fermentation log? (Two runs of the same executor count as a pair.)

1. The temperature program and the gravity program
2. The brewing agent and the gravity program
3. The brewing agent and the temperature program
4. None
