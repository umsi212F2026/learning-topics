Mateo is gathering his household's receipts for this year's taxes.

- Whenever Mateo photographs a receipt, a filing program does two things: it saves the photo in the receipts folder, and it adds an entry for the receipt to the receipts list.
- Each Saturday the sorting agent, following a skill file Mateo wrote, reads each photo and writes the tax category the receipt belongs in, with a sentence of reasons, into the receipt's category field. It passes over any receipt whose category field isn't empty.
- At the end of the year a totals program adds up the receipts in each category.

On Saturday the laptop restarted for an update while the agent was writing the category field for the 58th of 90 receipts. Nobody has opened the receipts list since.

### q1

If Mateo runs the sorting agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
