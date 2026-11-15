Tomas wants a cheap desk and a bookshelf for his new apartment.

- Each evening the collecting program reads the posts put up that day on a neighborhood swap site, and adds an entry to the furniture list for each post offering furniture.
- Then the sizing agent, following a skill file Tomas wrote, reads each entry and writes a verdict of 'fits' or 'too big' into it, from the measurements of his room.
- Then a details program pulls each post's asking price and pickup street into its entry.

On Monday evening the collecting program stopped when the laptop's wifi dropped, just after it added the entry for the 22nd of 35 posts. Tomas wants to run it again that same evening. Nobody has opened the furniture list since.

### q1

If Tomas runs the collecting program again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
