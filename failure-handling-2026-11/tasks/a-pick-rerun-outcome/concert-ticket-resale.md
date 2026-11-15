Ines is hunting for resale tickets to a sold-out concert tour that reaches her city in March. Each morning a program adds a row to the listings list for each new listing on a ticket resale site, then the rating agent rates the listings, and then a details program pulls each listing's price, date and section into its row. The rating agent, following a skill file Ines wrote, reads every listing in the list on each run, passing over none, and writes a rating of 'buy now', 'maybe' or 'skip' into the listing's row, with a sentence of reasons, overwriting any rating already there. At noon each day the shortlist program copies every listing rated 'buy now' onto that day's shortlist, which Ines reads each evening. On Wednesday morning the laptop restarted for an update while the agent was writing the rating for the 31st of 48 listings. At noon the shortlist program put five listings rated 'buy now' onto Wednesday's shortlist, all of them among the first 30.

### q1

If Ines runs the rating agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
