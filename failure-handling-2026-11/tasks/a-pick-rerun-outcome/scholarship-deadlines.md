Priya is a high school senior keeping track of scholarships she might apply for. Every Monday a program saves the pages of newly posted scholarships from a scholarship listings site into a folder. Then the assessing agent, following a skill file Priya wrote, reads each saved page and writes a notes file for that scholarship with its deadline, its award amount and whether she meets its requirements. It passes over any scholarship that already has a notes file. This Monday her laptop shut down for a system update while the agent was writing the notes for the 23rd of 38 new scholarships. Priya hasn't opened any of the notes since.

### q1

If Priya runs the assessing agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added, or an action outside the workflow gets repeated.
3. A partly written result gets trusted or tripped over.
4. A different result replaces one that a person or a later step has already used or checked.
