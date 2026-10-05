# Rubric: stack trace

If the learner misses a question here, set a DEFINE or INTERPRET move for stack trace live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A stack trace is the trail an error leaves in the log of where in the code it happened: the chain
of function calls, file by file and line by line, that was running when the error was thrown. It is
left only when code throws an error and the error is logged. The confusable is the error message,
the one line saying what went wrong. "Traceback" and "backtrace" are other names for a stack trace
and are not confusables.

### q1

- **goal:** `w-stack-trace`
- **move:** DISTINGUISH
- **answer:** The error message, the first line, says what went wrong: the code tried to read
  `map` from something that was undefined. The stack trace, the `at` lines under it, says where:
  in `listRooms` at line 18 of `server/routes/rooms.js`, called from Express's router.
- **credit:** full for naming both halves: the message says what went wrong, the stack trace says
  where in the code it happened (or the chain of calls that led there). Half for only one half,
  such as "the trace gives the file and line" with nothing on what the message says. None for an
  incidental difference alone, such as that the trace is longer or indented, or which line comes
  first.
- **tutor note:** if they say the trace points into Express, ask which of the `at` lines is in
  their own code.

### q2

- **goal:** `w-stack-trace`
- **move:** CATCH
- **answer:** A stack trace is left only when the backend's code throws an error and logs it. A
  failure that never reaches that code leaves none: a frontend calling a wrong address, a browser
  blocking the answer under CORS, or an app that isn't running at all. So no stack trace doesn't
  mean nothing is failing.
- **credit:** full for naming that a stack trace appears only where the code itself threw an
  error, so failures that don't happen in the backend's code leave none. Half for "no trace
  doesn't prove it works" without saying why. None for a different quibble alone, such as that an
  hour is too short, or that they should check the build log.
