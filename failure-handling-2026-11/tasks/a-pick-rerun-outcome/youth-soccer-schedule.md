Keiko wants every game of her son's soccer season on the family's shared calendar.

- At the start of the season a saving program saves the league's schedule page, which lists the season's games for every team.
- Then the calendar agent, following a skill file Keiko wrote, reads the saved page and adds an event to the family's shared calendar for each of her son's team's games, with the field and the start time. It passes over any game on its finished list, which it saves when a run ends.

On Saturday Keiko's laptop lost power just after the agent added the event for the 8th of 14 games. That was the agent's first run this season.

### q1

If Keiko runs the calendar agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
