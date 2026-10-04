# Rubric: cold start

If the learner misses a question here, set a DEFINE or INTERPRET move for cold start live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A cold start is the wait while a sleeping app wakes for its first request. The confusable is a slow
server, which is slow on every request, awake or not. "Spin-up time" means the same as cold start
and is not a confusable.

### q1

- **goal:** `w-cold-start`
- **move:** DISTINGUISH
- **answer:** A cold start is a one-time wait: the app was asleep, and the first request after the
  quiet stretch waits while it wakes; after that it answers quickly. A slow server is slow on every
  request, even while it is awake and busy. To tell them apart, see whether only the first request
  after nobody has used it for a while is slow.
- **credit:** full for the difference that matters (a cold start is only the first request after
  the app has slept; a slow server is slow on every request) and a way to tell that follows from
  it. Half for the difference without a way to tell, or for "a cold start goes away" without
  saying when it happens. None for an incidental difference alone, such as how many seconds each
  takes, or that one is the host's fault.

### q2

- **goal:** `w-cold-start`
- **move:** CATCH
- **answer:** A cold start happens only on the first request after the app has been asleep. While
  the class is using it, the app is awake, so a wait on every click is not a cold start; it is
  something else, such as a slow server.
- **credit:** full for naming that a cold start comes only after the app has slept, and an app in
  steady use is awake. Half for "that's just a slow app" without saying why it can't be a cold
  start. None for a different quibble alone, such as that a bigger plan would fix it.
