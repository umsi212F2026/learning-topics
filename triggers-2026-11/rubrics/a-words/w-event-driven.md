# Rubric: Event-driven

If the learner misses a question here, set a DEFINE or INTERPRET move for event-driven live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A workflow is event-driven when a run starts because something happened, rather than at set times
or when a person starts it. Polling is one way of noticing the event, by asking again and again
whether anything has changed; a hook, being told, is the other. So the two are not alternatives:
an event-driven workflow may notice its events by polling. A program running with no person
starting it is not enough to make a workflow event-driven: a run at set times is a schedule, even
though nobody starts it. The reading's line "polling is a schedule doing an event trigger's job"
describes the checks, which run on a schedule; the texts they lead to are still started by the
event.

### vs-schedule

- **goal:** `w-event-driven`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. Each booking text goes out because a patient booked; the
  five-minute checks are polling, a way of noticing that event, and on most checks no text is
  sent. Each reminder goes out because it is 6 p.m., whatever has happened, so the reminders are
  on a schedule. Choice 2 reverses the two. Choice 3 stretches the word to anything automatic.
  Choice 4 reads the five-minute checks as the run, when the run that matters, the text to a
  patient, is started by the booking.
- **tutor note:** a learner who picks 4 is reading the checks as what starts each text; ask what
  makes a particular patient get a booking text.

### catch-backup

- **goal:** `w-event-driven`
- **move:** CATCH
- **answer:** A backup that runs every night at 2 a.m. is started by a schedule, at set times, not
  because something happened. It even runs when nothing has changed. An event-driven backup would
  run because something happened, such as a file being saved.
- **credit:** full for naming that the backup runs at set times rather than because something
  happened, so it is scheduled, not event-driven. Half for "that's a cron job" or "that's
  scheduled" with nothing on why that isn't event-driven. Half at most for calling 2 a.m. arriving
  an event, and so the sentence right. None for a different quibble alone, such as that running
  when nothing changed is wasteful.
