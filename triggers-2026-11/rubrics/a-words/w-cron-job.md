# Rubric: Cron job

If the learner misses a question here, set a DEFINE or INTERPRET move for cron job live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A cron job is a command the operating system starts at set times, with nothing of yours kept
running in between: at the set time the system starts it, and when it finishes it is gone. A
program left running in the background was started once and keeps running, waiting, and it is
the program that decides when to act. A cron job fires only if the machine is on at that time,
and cron does not run a time it missed. "Scheduled job" and "scheduled task" are other names for
it. A cron job is a schedule, so it is not started by an event, and it is not a
list of work.

### catch-pick

- **goal:** `w-cron-job`
- **move:** CATCH
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only. At the set time the operating system starts the command, and when
  it finishes nothing is left running; between runs there is nothing of the backup's to see.
  Choice 1 reads the cron job as a program left running in
  the background. Choice 2 reads it as started by an event, a new photo, when it is started at set
  times. Choice 3 reads it as the work waiting to be done, which is a work queue.

### catch-missed

- **goal:** `w-cron-job`
- **move:** CATCH
- **answer:** A cron job doesn't catch up. It fires only if the laptop is on at the set time, and
  cron does not run a time it missed, so that Monday's summary simply doesn't get built. Nothing
  was running in between that could notice the missed time.
- **credit:** full for naming that cron does not run a missed time, so the summary is not built
  that week. Half for "the laptop was off" with nothing on whether cron makes up the missed run.
  None for a different quibble alone, such as that 6 a.m. is too early. A learner who adds that a
  Mac's launchd would also not run a job missed while the Mac was turned off is right; one who
  says launchd would run it is wrong about launchd, but that is not this word, so rule only on
  what they say about cron.
