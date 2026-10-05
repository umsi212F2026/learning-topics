# Rubric: deploy status

If the learner misses a question here, set a DEFINE or INTERPRET move for deploy status live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A deploy status is the host's one-word verdict on the latest deploy, such as live, building or
failed: whether that deploy got built and running. The confusable is whether the app works, which
is about what visitors' requests get back. Larkyard is a made-up host.

### q1

- **goal:** `w-deploy-status`
- **move:** DISTINGUISH
- **answer:** `live` says only that the latest deploy was built, started and is now the one
  serving. Whether the app works is whether visitors' requests do what they should, and a live
  deploy can still fail them: one route throwing an error, or a frontend calling the backend at
  the wrong address.
- **credit:** full for naming that the status is the host's verdict on getting the deploy running,
  and says nothing about whether each request succeeds. Half for "live doesn't mean it works"
  without saying what the status does cover. None for an incidental difference alone, such as
  where each is shown or that the status is one word.

### q2

- **goal:** `w-deploy-status`
- **move:** CATCH
- **answer:** The status is a verdict on the new deploy only. It says that deploy didn't get
  running, not what is being served: the previous, working deploy can still be the one visitors
  get, so the site may be up and simply without the change.
- **credit:** full for naming that the status is about the latest deploy, not about whether
  anything is serving, so the earlier version may still be up. Half for "the site might not be
  down" without connecting it to what the status is a verdict on. None for a different quibble
  alone, such as that they should read the build log first, or that "failed" might be a mistake.
- **tutor note:** a learner who says "it depends on the host" has the point if they say on what:
  whether the host keeps the previous deploy serving.
