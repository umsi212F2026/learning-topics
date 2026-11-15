Amara is a high school senior keeping track of scholarships she could apply for.

- Each week, for each new scholarship on a scholarship search site, a collecting program does two things: it saves a copy of the scholarship's web page in the scholarships folder, and it adds an entry for the scholarship to the scholarships list.
- Then the fit agent, following a skill file Amara wrote, reads each saved page and writes a verdict of 'apply' or 'skip' into the scholarship's entry, from her grades and her plans.
- Then the details agent, following another skill file Amara wrote, reads each saved page and writes a details file for that scholarship in the details folder, giving its deadline, its award amount and its essay topic. It passes over any scholarship that already has a details file.

On Thursday the laptop's battery ran out while the details agent was writing the details file for the 17th of 40 scholarships. Amara hasn't opened the scholarships list or the details folder since.

### q1

If Amara runs the details agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
