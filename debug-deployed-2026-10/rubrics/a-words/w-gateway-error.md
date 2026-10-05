# Rubric: gateway error

If the learner misses a question here, set a DEFINE or INTERPRET move for gateway error live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A gateway error is the host answering for your app because your app didn't: it isn't running,
isn't listening where the host expects, or didn't answer in time. The confusable is a 500 error
from your app, where your code did handle the request and failed, usually leaving a stack trace in
the server log. "502 Bad Gateway" and "503 Service Unavailable" are names for gateway errors and
are not confusables. Brindlehost is a made-up host.

### q1

- **goal:** `w-gateway-error`
- **move:** DISTINGUISH
- **answer:** A gateway error comes from the host: it tried to pass the request to the app and got
  no answer, so the app's code never handled it (the app may be down or not listening). A 500 comes
  from the app itself: the request reached the code, the code failed while handling it, and the
  app answered with an error.
- **credit:** full for naming who answered: the host, because the app didn't, against the app
  itself after its code failed. Half for only one half, such as "a 500 is a bug in the code" with
  nothing on where a gateway error comes from. None for an incidental difference alone, such as the
  number, or how the error page looks.

### q2

- **goal:** `w-gateway-error`
- **move:** CATCH
- **answer:** A 502 is a gateway error: the host is answering because it got no answer from the
  app at all. A route throwing an error while handling a request would give a 500 from the app.
  Every data page failing this way points to the app not running or not answering, so the place to
  look is whether it started, not which route failed.
- **credit:** full for naming that a 502 means the host got no answer from the app, not that a
  route failed while handling the request (which would be a 500). Half for "a 502 isn't a route
  error" without saying what it is. None for a different quibble alone, such as that they should
  check the build log, or that the agent should be told to fix it.
