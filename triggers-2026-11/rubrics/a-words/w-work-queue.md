# Rubric: Work queue

If the learner misses a question here, set a DEFINE or INTERPRET move for work queue live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A work queue is whatever a worker consults to tell what work is still to be done. It may be a list
the workflow keeps on purpose, an outside source that already holds the waiting work, or a list
worked out each time from the state of files. A log records what has happened, so a queue is
about what is still to come and a log about what is done. They need not be two records: a queue
can be worked out from a log, as everything not yet in it. "Job queue" and "task queue" are other
names for it, not confusables. The trigger that starts the worker is not the queue.

### vs-log

- **goal:** `w-work-queue`
- **move:** DISTINGUISH
- **answer:** `done.txt` is the log: a record of what has happened, one line per photo already
  resized. The work queue is what the script consults to find what is still to be done: every
  photo in `incoming` not named in `done.txt`. Nobody keeps that list; it is worked out each night
  from the folder and the log, so here the queue comes from the log rather than being a second
  record.
- **credit:** full for naming `done.txt` as the log, because it records photos already resized,
  and the photos in `incoming` not named in `done.txt` as the work queue, because they are what
  the script consults to find what is still to be done. Saying that the queue is worked out from
  the log is welcome but not required. Half for naming `incoming` (the whole folder) as the work
  queue, since it also holds photos already done. Half also for naming `done.txt` as the log
  while saying this workflow has no work queue because nobody keeps a separate list. None for
  calling `done.txt` the work queue, or for a general difference ("the log is the past, the queue
  is the future") with neither matched to this workflow.
- **tutor note:** a learner who says there is no queue here is holding the term too narrowly; ask
  how the script knows, each night, which photos it still has to do.

### catch-pick

- **goal:** `w-work-queue`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The booking site already holds the waiting work, and the bookings
  it returns when the script asks for those since its last run are what the script consults to
  tell what is still to be done, so they are the work queue, with nothing extra kept. Choice 1 is a record of what has been done, a log, not what is still to be done. Choice 2
  holds the term too narrowly: a queue need not be kept on purpose, and an outside source holding
  the waiting work is one. Choice 4 is the trigger that starts the worker, not where the work
  waits.
- **tutor note:** a learner who picks 2 thinks a queue has to be a list someone keeps; ask where
  the script finds out which bookings it hasn't emailed about yet.

### catch-shipped

- **goal:** `w-work-queue`
- **move:** CATCH
- **answer:** `shipped.txt` lists orders that have already been packed and sent, so it is a log
  of work done, not a list of work waiting. The work queue is the orders not yet in
  `shipped.txt`. The file could be used to work out the queue, but the orders in it are exactly
  the ones not waiting.
- **credit:** full for naming that the orders in `shipped.txt` are done, not waiting, so the file
  records what has happened rather than what is still to be done. Naming the orders not in the
  file as the queue is welcome but not required. Half for "that's a log, not a queue" with nothing
  on what the orders in it are. Half at most for saying a log can never serve as a queue, since a
  queue can be worked out from one; the error is reading the done orders as the waiting ones.
  None for a different quibble alone, such as the file's name.
