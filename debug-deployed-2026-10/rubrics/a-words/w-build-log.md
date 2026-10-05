# Rubric: build log

If the learner misses a question here, set a DEFINE or INTERPRET move for build log live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A build log is what the host printed while turning your code into what it runs: installing
packages, running the build, for one deploy, and it ends when that build ends. The confusable is
the server log, what the running app prints while it handles requests, for as long as it runs.
Ferncastle is a made-up host.

### q1

- **goal:** `w-build-log`
- **move:** DISTINGUISH
- **answer:** The build log is the output from the host preparing one deploy (installing packages,
  building), written before the app runs, and it stops when the build finishes. The server log is
  what the app prints once it is running, as it starts and as it handles each request, and it
  keeps growing as long as the app runs.
- **credit:** full for naming the difference in stage: the build log covers the host preparing the
  code before it runs, the server log covers the running app and its requests. Half for only one
  half, such as "the server log shows requests" with nothing on what the build log covers. None
  for an incidental difference alone, such as which is longer or which the dashboard shows first.

### q2

- **goal:** `w-build-log`
- **move:** CATCH
- **answer:** The build log covers only this morning's build, which finished before the app
  started. An error on a request at 3:12 happened in the running app, so its stack trace, if it
  left one, is in the server log, not the build log.
- **credit:** full for naming that the build log ends with the build, so an error in the running
  app at 3:12 is in the server log instead. Half for "look in the server log" without saying why
  the build log can't hold it. None for a different quibble alone, such as that the deploy might
  not be the latest, or that the agent should be asked to fix the bug.
