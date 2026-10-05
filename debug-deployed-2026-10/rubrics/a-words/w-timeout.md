# Rubric: timeout

If the learner misses a question here, set a DEFINE or INTERPRET move for timeout live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A timeout is giving up on a request that took too long to answer: the browser, the host or the
backend itself (waiting on its database) stops waiting. The thing being waited on may still be
running. The confusable is a crash, where the app's process dies and answers nothing until it is
started again.

### q1

- **goal:** `w-timeout`
- **move:** DISTINGUISH
- **answer:** A timeout means whoever was waiting for the search answer gave up because it took
  too long; the backend may still be running, and may even be answering other requests. A crash
  means the backend's process died, so it answers nothing at all until it is restarted.
- **credit:** full for naming that a timeout is giving up on a slow answer while the app may still
  be running, and a crash is the app itself stopping. Half for only one half, such as "a crash
  means the app stopped" with nothing on what a timeout is. None for an incidental difference
  alone, such as the error code, or which is more common.

### q2

- **goal:** `w-timeout`
- **move:** CATCH
- **answer:** A timeout isn't a crash: the search request was too slow, and something gave up
  waiting for it. Nothing needs to have thrown an error, so there may be no stack trace at all; the
  backend may still be running, slowly working on the search.
- **credit:** full for naming that a timeout means the answer took too long, not that the app
  crashed, so there may be no stack trace to find. Half for "it didn't crash" without saying what
  a timeout is. None for a different quibble alone, such as that search should be made faster, or
  that the build log should be checked.
