# Rubric: Event-driven

If the learner misses a question here, set a DEFINE or INTERPRET move for event-driven live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A workflow is event-driven when a run starts because something happened, rather than at set times
or when a person starts it. Polling is one way of noticing the event, by asking again and again
whether anything has changed; a hook, being told, is the other. So the two are not alternatives:
an event-driven workflow may notice its events by polling. A program running with no person
starting it is not enough to make a workflow event-driven: a run at set times is a schedule, even
though nobody starts it. The reading's line "polling is a schedule doing an event trigger's job"
describes the checks, which run on a schedule; the texts or slips they lead to are still started
by the event.

### vs-polling

- **goal:** `w-event-driven`
- **move:** DISTINGUISH
- **answer:** Being event-driven is about what starts a run: here, a patient booking an
  appointment, which leads to a text. Polling is how the program notices that event: by asking the
  booking site every five minutes whether there are new appointments, since the site won't tell
  it. So this workflow is event-driven, and it notices its events by polling; the two are not
  rivals.
- **credit:** full for naming that event-driven is about a run starting because something
  happened, and polling is a way of noticing the event by asking again and again, matched to this
  workflow. Saying outright that this workflow is both is welcome but not required. Half for "an
  event-driven workflow reacts to events, polling checks on a schedule" with nothing on how the
  two relate here. Half at most for the right definitions joined to a verdict that this workflow
  is not event-driven because it polls. None for an incidental difference alone, such as that
  polling is slower.
- **tutor note:** a learner who calls the workflow scheduled because of the five-minute checks is
  reading the checks as the run; ask what makes a text go out to a particular patient.

### catch-pick

- **goal:** `w-event-driven`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. Each slip is printed because an order was placed, which is what
  event-driven names. Choice 1 takes the cron job for event-driven: the Friday summary runs at a
  set time, which is a schedule. Choice 2 stretches the word to anything automatic; the summary
  has no person starting it but is still a schedule. Choice 4 reads event-driven as needing the
  program to check; here the site tells the program, and that is still event-driven.

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
