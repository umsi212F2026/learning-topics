# Event-driven

### vs-polling

A dentist's office wants a text sent to each patient soon after they book an appointment online.
The booking site offers no way to send the office a message when a booking is made, so the
office's program asks the booking site every five minutes for any new appointments, and texts each
new patient it finds.

In this workflow, what is the difference between being event-driven and polling? Answer in two or
three sentences, in your own words.

### catch-pick

A small online store's site sends a message to the warehouse's program each time a customer places
an order, and the program prints a packing slip for that order. Separately, a cron job emails the
owner a sales summary every Friday at 5 p.m.

In this workflow, what is event-driven?

1. The Friday sales summary
2. Both jobs, since no person starts either
3. The packing slips
4. Neither, since nothing checks for orders

### catch-backup

An office manager describes the backup on the office's file server:

"Our backup is event-driven: it runs every night at 2 a.m., whether or not anything has changed."

What is wrong with that? Answer in two or three sentences, in your own words.
