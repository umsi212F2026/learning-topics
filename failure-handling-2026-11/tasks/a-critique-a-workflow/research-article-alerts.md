Lucia is writing a class project on how city trees cool streets in summer, and she wants to keep up with new research on it. She gets article alerts by email from two research sites, and a tracker on her laptop works through them each night at 1 a.m., while she is asleep.

- First the collecting program goes through every alert that arrived in the past day. For each article in an alert, it does two things: it saves a copy of the article's summary page in the articles folder, and it adds an entry for the article to the articles list. It passes over any article on its finished list, which it saves when a run ends. When an article's page won't open, the program shows a warning in a window that closes when the run ends, and goes on to the next article, adding no entry for it.
- Next the assessing agent, following a skill file Lucia wrote, reads the saved page of each article collected that night. It writes a rating of 'read it' or 'skip' into that article's entry, with one sentence on how close the article comes to her topic, overwriting any rating already there. When it can't open a saved page, it writes 'unreadable' in place of a rating.
- Then the extracting program pulls the year, the authors and the journal's name out of each saved page and writes them into that article's year, authors and journal fields, overwriting whatever is there. It passes over any article marked 'details done', a mark it adds only after all three fields are written. When it finds no year on a page, it leaves the year field empty and goes on.
- Once the extracting program finishes, a flagging program looks for any entry whose year field is empty and puts that entry at the top of the articles list.
- Each afternoon after class Lucia reads the articles list from the top, then opens the saved page of every article rated 'read it' and reads it in full.

### rerun-collecting

Suppose the collecting program stops after it has worked through one of the night's three alerts, when Lucia's laptop restarts for an update. Nobody has opened the articles list since.

If Lucia runs the collecting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-assessing

Suppose the assessing agent stops just after it finishes the 10th of 16 new articles, when the laptop's battery runs out. Since then, Lucia has read those ten ratings and started reading the four articles rated 'read it'.

If Lucia runs the assessing agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-extracting

Suppose the extracting program stops while it is writing the fields for the 7th of 16 new articles, when the laptop goes to sleep. Nobody has opened the articles list since.

If Lucia runs the extracting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### detect-collecting

Suppose one night one article's page won't open when the collecting program tries to save it.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-assessing

Suppose one night the assessing agent rates 'read it' an article about cooling office buildings with fans, which says nothing about trees or streets.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-extracting

Suppose one night, for an article the assessing agent rated 'skip', the extracting program takes the year of an older study the article cites, 2009, as the article's year, which the page gives as 2024.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.
