# Rubric: instance

If the learner misses a question here, set a DEFINE or INTERPRET move for instance live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

An instance is one running copy of your app on a host's machine. The confusable is the server host,
the vendor's service that keeps your backend running, which may run one copy or several. "Dyno" is
one vendor's name for an instance and is not a confusable.

### q1

- **goal:** `w-instance`
- **move:** DISTINGUISH
- **answer:** The server host is the vendor's service that keeps your backend running. An instance
  is one running copy of the backend on one of its machines. Here the host is running two copies
  of the same backend, and could run more or fewer without being a different host.
- **credit:** full for the difference that matters: the server host is the service doing the
  running, and an instance is one running copy of the app, of which a host can run several. Half
  for "an instance is a copy" with nothing on what the host is. None for an incidental difference
  alone, such as that instances cost money or are smaller.

### q2

- **goal:** `w-instance`
- **move:** CATCH
- **answer:** An instance is one running copy of the app, not a seat for one user. A single
  running copy answers requests from many visitors, one after another and at once, so a class can
  use it together.
- **credit:** full for naming that one running copy serves many visitors, so instances are not one
  per user. Half for "it can handle more than one" without saying what an instance is. None for a
  different quibble alone, such as that free plans have other limits, or that the app might sleep.
