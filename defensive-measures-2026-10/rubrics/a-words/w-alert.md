# Rubric: alert

If the learner misses a question here, set a DEFINE or INTERPRET move for alert live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

An alert is a message that comes to you, by email or text or chat, when something about the live
app crosses a line you set, such as more than five errors in an hour or no answer at all. The
confusables are the server log, which is what the server prints while it runs, a record that sits
there until someone goes and reads it; and a health check, which is an address the host keeps
asking to see whether the app still answers, so that the host can act (restart it, say). Neither
of those comes to a person. "Alerting" is another name for setting alerts up and is not a
confusable. Choirsheet and Lanternwell are made up, and appear nowhere else in this topic.

### q-catch-page-nobody-opens

- **goal:** `w-alert`
- **move:** CATCH
- **answer:** The admin page doesn't come to anyone; it only goes red for someone who already has
  it open. If Choirsheet starts failing in the middle of the night, nobody is looking, so nobody
  knows until someone happens to open the page. An alert is a message that reaches the builder,
  by email or text or chat, when the line is crossed.
- **credit:** full for naming that the page waits to be looked at and nothing is sent to the
  builder, so a failure at night goes unseen. Half for "that isn't a real alert" or "it should
  send an email" without saying why the page falls short here. None for a different quibble
  alone, such as that five errors is the wrong line, that an hour is too long, or that the page
  should be protected by a sign-in.
- **tutor note:** a learner who says the page is still useful is right about that; ask who sees
  it go red at three in the morning.

### q-alert-vs-server-log

- **goal:** `w-alert`
- **move:** DISTINGUISH
- **answer:** The server log is the record: every error is written there, and it stays there
  until someone goes and reads it. An alert is a message that comes to the builder when something
  crosses a line they set, such as more than five errors in an hour, telling them to go and look.
  The log holds what happened; the alert is what makes someone find out.
- **credit:** full for naming that the log is a record someone has to go and read, while an alert
  comes to a person, unasked, when a line they set is crossed. Half for only one half, such as
  "the log just stores errors" with nothing on what an alert does. None for an incidental
  difference alone, such as that the log is kept for thirty days, that alerts arrive by email, or
  that the log has more detail.
- **tutor note:** a learner who says the alert would be built from what the log records has a
  point, since an error count usually comes from the log; ask who reads the log on a night when
  nothing is sent.

### q-alert-vs-health-check

- **goal:** `w-alert`
- **move:** DISTINGUISH
- **answer:** The health check is Lanternwell asking Choirsheet whether it still answers, so that
  Lanternwell can act on its own, by restarting the app; no person is told. The alert is a message
  that comes to the builder when Choirsheet stops answering, so a person finds out and can look
  into it. The health check is for the host; the alert is for the builder.
- **credit:** full for naming that the health check is the host asking the app so the host can
  act, while the alert is a message that goes to a person. Half for only one half, such as "the
  health check restarts the app" with nothing on who the alert tells. None for an incidental
  difference alone, such as how often each one runs, or that one is free and the other isn't.
- **tutor note:** a learner who says the alert could be set off by the health check failing is
  right, and the two often work together; ask who hears about it if the restarts keep failing and
  there is no alert.
