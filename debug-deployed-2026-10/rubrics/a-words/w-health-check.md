# Rubric: health check

If the learner misses a question here, set a DEFINE or INTERPRET move for health check live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A health check is an address on the running app that the host keeps asking, over and over, to see
whether the app still answers; if it stops answering, the host acts (holds back a new deploy,
restarts the app). The confusable is a test, code the developer runs on demand, before deploying,
to check the code does what it should. "Health endpoint" is another name for the address and is
not a confusable. Pebblerun is a made-up host.

### q1

- **goal:** `w-health-check`
- **move:** DISTINGUISH
- **answer:** The health check is the host asking the deployed, running app at one address, again
  and again, whether it answers at all. A test is something you run when you choose, usually before
  deploying, to check that the code behaves as it should, and it is not run by the host against the
  live app.
- **credit:** full for naming the difference in who asks and what about: the host repeatedly
  asking the running app whether it answers, against the developer checking the code's behaviour.
  Half for only one half, such as "the host runs the health check" with nothing on what a test
  checks. None for an incidental difference alone, such as that one is a URL and one is a command,
  or which is faster.

### q2

- **goal:** `w-health-check`
- **move:** CATCH
- **answer:** The health check only asks whether the app answers at its one address. It doesn't
  submit a sign-up or touch the database, so a passing health check says nothing about whether the
  sign-up route saves correctly.
- **credit:** full for naming that the health check asks only whether the app answers at that
  address, so it can't show that another route works. Half for "that doesn't prove sign-ups work"
  without saying what the health check does check. None for a different quibble alone, such as
  that once a minute is too rarely, or that they should write a test.
