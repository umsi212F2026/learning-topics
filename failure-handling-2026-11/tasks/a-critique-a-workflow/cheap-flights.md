Owen wants to fly home to see his parents in April, and he is watching for a cheap fare. He subscribes to three flight-deal newsletters, and a tracker on his laptop works through them each night at 2 a.m., while he is asleep.

- First the collecting program goes through every newsletter that arrived in the past day. For each deal in a newsletter, it does two things: it saves a copy of the deal's web page in the deals folder, and it adds an entry for the deal to the deals list. It adds an entry for every deal it finds, even if the list already has one for that deal. Nothing changes a saved page after it is saved. When a deal's page won't open, the program writes a line saying so to a problems file in the tracker's folder and goes on to the next deal, adding no entry for it.
- Next the assessing agent, following a skill file Owen wrote, reads each saved page and writes a notes file for that deal on how well it fits his trip (the airports, his April dates and the length of any layover), ending in a rating of 'worth a look' or 'skip'. The agent passes over any deal that already has a notes file. When it can't open a saved page, it goes on to the next deal without writing anything.
- Then the extracting program pulls the total fare and the airline out of each saved page and writes them into that deal's fare and airline fields in the deals list, overwriting whatever is there. When it finds no fare on a page, it leaves the fare field empty and goes on.
- Once the extracting program finishes, a counting program compares the number of notes files with the number of entries in the deals list, and when the two numbers don't match it puts a line at the top of the list saying how many deals have no notes.
- Each morning over breakfast Owen reads the deals list from the top, then reads the notes of every deal rated 'worth a look', along with its fare and airline from the list.

### rerun-collecting

Suppose the collecting program stops after it has worked through two of the night's three newsletters, when Owen's laptop restarts for an update. Nobody has opened the deals list since.

If Owen runs the collecting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-assessing

Suppose the assessing agent stops while it is writing the notes for the 9th of 14 new deals, when the laptop's battery runs out. Nobody has opened any notes since.

If Owen runs the assessing agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-extracting

Suppose the extracting program stops just after it finishes the 6th of 14 new deals, when the laptop goes to sleep. Since then, Owen has read those six fares and picked one deal he may book.

If Owen runs the extracting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### detect-collecting

Suppose one night the travel site doesn't answer when the collecting program tries to save one deal's page.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-assessing

Suppose one night the assessing agent can't open one saved page.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-extracting

Suppose one night, for a deal the assessing agent rated 'worth a look', the extracting program takes the fare before taxes and fees, $248, as the total fare, which the page gives as $331.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.
