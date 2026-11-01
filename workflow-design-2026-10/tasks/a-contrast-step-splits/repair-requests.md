A landlord with two small apartment buildings handles the tenants' repair requests with a weekly
workflow. About 25 requests come in a week.

1. Gather the week's repair requests from the tenants' web form into one list. (a program)
2. Label each request urgent or routine by the landlord's written rules, then choose which routine
   repairs are worth doing this week and put the week's repairs in the order they should be done.
   (an AI agent, then the landlord)
3. Send each repair, in that order, to the repair company the landlord uses for that kind of work,
   and record the day and hour the company gives back. (a program)
4. Match each tenant to the repair booked for them and its day and hour, list the week's visits by
   day, and write each of those tenants a short, polite text saying when the worker will come. (an
   AI agent)
5. Send each text to its tenant. (a program)

Some of these steps do more than one step's work.

### q1

Priya, Marcus and Lena each propose splitting step 2 into two steps.

1. Priya: split after the landlord chooses which routine repairs to do, and keep the list of
   repairs chosen for this week.
2. Marcus: split after the agent labels the requests, and keep the list of requests, each marked
   urgent or routine.
3. Lena: split after the agent labels the requests, and hand the labels straight to the landlord
   without keeping them.

Which proposal is the best division of step 2?

1. Priya's
2. Marcus's
3. Lena's

### q2

Omar, Grace and Tomas each propose splitting step 4 into two steps.

1. Omar: split after the agent matches each tenant to their booking, and keep the bookings the
   program recorded in step 3.
2. Grace: split after the agent matches each tenant to their booking, and keep the list of each
   tenant's matched repair and time.
3. Tomas: split after the agent lists the visits by day, and keep that list of visits, one line
   per tenant.

Which proposal is the best division of step 4?

1. Omar's
2. Grace's
3. Tomas's
