Priya is spending the summer in another city for a research job and needs a sublet there. Her workflow runs on her laptop at 7 each morning, while she is asleep. 

First the collecting program takes every listing that two housing sites have posted since the day began, saves each listing's page into a folder, and adds a line for it to the listings list; it pays no attention to what the list holds already. If a site doesn't answer, the collecting program writes a line about it in a problems file, in a folder Priya never opens, and goes on to the next site. Nothing changes a saved page after it is saved.

Next the assessing agent, following a skill file Priya wrote, reads each saved page and writes a notes file for that listing, saying whether it is furnished, which dates it is free, and a rating of 'worth a look' or 'skip' against her budget and her dates. It passes over any listing that already has a notes file, and if it can't open a saved page, it goes on to the next one without writing anything. Then the extracting program pulls the address, the monthly rent and the landlord's contact details out of each saved page and writes them into that listing's line, overwriting whatever is there. Last, a counting program compares the number of notes files with the number of saved pages, and if the two don't match, it puts a line saying how many notes files are missing at the top of the listings list. Each evening Priya reads that list, then reads the notes for every listing rated 'worth a look', with its saved page open beside it, before deciding which landlords to call.

### q1

Suppose the collecting program stops when the laptop's battery runs out, just after it has saved the 18th of 35 new listings and added its line. Nobody has opened the listings list since. If Priya runs the collecting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added, or an action outside the workflow gets repeated.
3. A partly written result gets trusted or tripped over.
4. A different result replaces one that a person or a later step has already used or checked.

### q2

Suppose the assessing agent stops when the laptop loses its internet connection, while the agent is writing the notes file for the 12th of 30 listings. Nobody has opened any notes file since. If Priya runs the assessing agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added, or an action outside the workflow gets repeated.
3. A partly written result gets trusted or tripped over.
4. A different result replaces one that a person or a later step has already used or checked.

### q3

Suppose the extracting program stops when the laptop restarts for an update, just after it has written the 40th of 55 lines. Since then Priya has read those first 40 lines and called the landlords of two of the listings. If Priya runs the extracting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added, or an action outside the workflow gets repeated.
3. A partly written result gets trusted or tripped over.
4. A different result replaces one that a person or a later step has already used or checked.

### q4

Suppose one morning one of the two housing sites doesn't answer when the collecting program asks it for its new listings. Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### q5

Suppose one morning the assessing agent can't open one of the saved pages. Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### q6

Suppose one morning the assessing agent rates a listing 'skip' though it is furnished, under her budget and free for every date she needs. Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.
