Bao wants a weekly list of shows worth going to at the small music venues in his city.

- Each Monday a collecting program reads the newsletters he subscribes to from six venues, and adds an entry to the events list for each event in them, with the newsletter's description of it.
- Then the picking agent, following a skill file Bao wrote, reads every event in the list and writes a verdict of 'go', 'maybe' or 'pass' into the event's entry, with a sentence of reasons, overwriting any verdict already there.
- Then a details program pulls each event's date, start time and ticket price into its entry.

On Monday the laptop's battery ran out just after the picking agent finished the verdict for the 26th of 41 events. Since then Bao has read the first 26 verdicts and bought tickets for two of the shows marked 'go'.

### q1

If Bao runs the picking agent again from the start, which of these happens?

1. Nothing goes wrong: as it stands, the step is idempotent.
2. Duplicate records get added.
3. An action outside the workflow gets repeated.
4. A partly written result gets trusted or tripped over.
5. A different result replaces one that a person or a later step has already used or checked.
