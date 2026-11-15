Callum will spend June to August in another city for a summer program, and he needs a furnished room to sublet. A tracker on his laptop looks at two sublet sites each night at 3 a.m., while he is asleep, and one more step runs each day at noon.

- First the collecting program goes through the listings posted on the two sites in the past day. For each new listing, it does two things: it saves a copy of the listing's web page in the sublets folder, and it adds an entry for the listing to the sublets list. When a listing's page won't open, the program says nothing and goes on to the next listing, adding no entry for it.
- Next the assessing agent, following a skill file Callum wrote, reads each page saved that night and writes into that listing's entry a rating of 'worth a look' or 'skip' and a few lines on how well it fits his budget, his dates and his need for a quiet place to work, overwriting any rating already there. When it can't open a saved page, it leaves the entry's rating blank and goes on.
- Then the extracting program pulls the rent, the move-in date and the move-out date out of each saved page and writes them into a details file for that listing. It passes over any listing that already has a details file. When it finds no rent on a page, it adds the listing to the problems list and goes on.
- Once the extracting program finishes, a flagging program looks for any entry with no rating and puts it at the top of the sublets list.
- Each day at noon the viewing program goes through the listings collected the night before, and for each one rated 'worth a look' it posts the listing to the house-hunting board Callum shares with the two friends he will live with, asking which ones to view. When the board won't take a post, the program adds the listing to the problems list.
- Each morning Callum reads the problems list, then any entries at the top of the sublets list, then the details file of each listing rated 'worth a look'.

### rerun-assessing

Suppose the assessing agent stops just after it finishes the 11th of 20 new listings, when the laptop restarts for an update. At noon the viewing program posted to the shared board the three of those 11 listings that the agent had rated 'worth a look'.

If Callum runs the assessing agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-extracting

Suppose the extracting program stops while it is writing the details file for the 8th of 20 new listings, when the laptop's battery runs out. Nobody has opened any details files since.

If Callum runs the extracting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### rerun-viewing

Suppose the viewing program stops after posting 2 of the 5 listings rated 'worth a look' to the shared board, when the laptop goes to sleep.

If Callum runs the viewing program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.

### detect-collecting

Suppose one night one listing's page won't open when the collecting program tries to save it.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-assessing

Suppose one night the assessing agent rates 'skip' a listing that is under his budget, covers all his dates and is in a quiet house.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.

### detect-extracting

Suppose one night a listing's saved page shows its rent only in a photo, so the extracting program finds no rent on the page.

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.
