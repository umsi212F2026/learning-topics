Marisol collects running shoes and watches for limited releases.

- Each night, for each new release announced on a sneaker news site, a saving program does two things: it saves a copy of the release's web page in the releases folder, and it adds an entry for the release to the releases list. Nothing changes a saved page after it is saved.
- Then the judging agent, following a skill file Marisol wrote, reads each saved page and writes 'want' or 'pass' into that release's entry.
- Then the details program pulls the release date, the price and the store out of each saved page. It writes them into that release's date, price and store fields in the releases list, overwriting whatever is there.

On Saturday the laptop's battery ran out while the details program was writing the fields for the 34th of 50 releases. Since then Marisol has looked over the entries for the first 33 releases and put in orders for two pairs.

### q1

If Marisol runs the details program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
