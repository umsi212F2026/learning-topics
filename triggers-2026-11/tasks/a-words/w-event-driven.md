# Event-driven

### vs-schedule

A dentist's office has a program that sends patients two kinds of text.

- **Booking texts.** Every five minutes, the program asks the booking site for any appointments
  booked since it last asked, and texts each of those patients a confirmation.
- **Reminder texts.** Every evening at 6, the program texts every patient who has an appointment
  the next day.

Which of these is event-driven?

1. The booking texts
2. The reminder texts
3. Both, since the program starts each one with no person involved
4. Neither, since both come from checks at set times

### catch-backup

An office manager describes the backup on the office's file server:

"Our backup is event-driven: it runs every night at 2 a.m., whether or not anything has changed."

What is wrong with that? Answer in two or three sentences, in your own words.
