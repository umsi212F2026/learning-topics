Odile wants a permit for a popular backcountry trail this summer, and the park runs a lottery for each week's permits.

- Each morning, for each new lottery on the park's permit site, a saving program does two things: it saves a copy of the lottery's web page in the lotteries folder, and it adds an entry for the lottery to the lotteries list.
- Then the planning agent, following a skill file Odile wrote, reads each saved page and writes a notes file for that lottery on how well its dates fit her vacation and her hiking group, overwriting any notes already in it. Once a lottery's notes file is written in full, the agent marks the lottery's entry 'rated'. It passes over any lottery marked 'rated'.
- Then a details program pulls each lottery's entry deadline and number of permits into its entry.

On Friday the laptop restarted for an update while the agent was writing the notes for the 12th of 20 lotteries. Since then Odile has read the notes for the first 11 and picked three of those lotteries to enter.

### q1

If Odile runs the planning agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
