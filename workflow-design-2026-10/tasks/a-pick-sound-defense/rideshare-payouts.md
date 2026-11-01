Valley Rides is a ride-share co-op owned by its 80 drivers. Its treasurer runs this workflow every
week to pay the drivers for the week's rides and to answer drivers who ask for money early.

1. Add up each driver's fares for the week from the ride records. (a program)
2. Check the totals, take off the co-op's fee, and approve the list of payouts. (the treasurer)
3. Send each payout on the approved list to the driver's bank account. (who?)
4. Decide each driver's request for an advance on next week's pay: grant it, grant part of it, or
   decline it, and reply to the driver. (who?)
5. Email each driver a statement of the week's rides and pay. (a program)

**About step 3:** Its input is the list the treasurer approved at step 2, one line per driver with
the amount to pay. A mistake here pays a driver too much or too little, and nothing later catches
it. It handles each driver's name and bank account number. About two lines a week give the amount
in words, such as "two hundred ten", rather than in figures. The approved list is ready each Monday
at noon.

**About step 4:** Its input is about four requests a week, each a driver explaining why they need
money early, and the co-op's rules don't say which reasons qualify. A wrong decision can leave a
driver unable to pay rent, or owing more than they will earn, and the reply reaches the driver with
no one checking it. The requests often describe a driver's debts, such as rent owed or a loan
payment. The treasurer handles these on Wednesday evenings. Requests come in on any day of the
week.

## Framing

Each question gives two people's defenses of the same choice for one step.

### q1

Priya and Tom both think step 3 should be done by a program rather than an AI agent. Here is how
each puts it.

**Defense 1, Priya's:** A program rather than an AI agent helps correctness, because it pays
exactly the amounts on the approved list. It hurts timeliness, because it has to set aside the
amounts written out in words.

**Defense 2, Tom's:** A program rather than an AI agent helps correctness, because it pays exactly
the amounts on the approved list. It hurts timeliness, because no payout can go out before the
list is ready on Monday at noon.

Which defense is sound?

1. Priya's
2. Tom's

### q2

Grace and Mateo both think step 4 should be done by a person rather than an AI agent. Here is how
each puts it.

**Defense 1, Grace's:** A person rather than an AI agent helps privacy, because the co-op's rules
don't say which reasons for an advance qualify. It hurts timeliness, because the treasurer only
gets to these on Wednesday evenings.

**Defense 2, Mateo's:** A person rather than an AI agent helps privacy, because drivers' debts
stay out of the agent's provider. It hurts timeliness, because the treasurer
only gets to these on Wednesday evenings.

Which defense is sound?

1. Grace's
2. Mateo's
