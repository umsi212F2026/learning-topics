# Rubric: Workflow outcome

If the learner misses a question here, set a DEFINE or INTERPRET move for workflow outcome live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A workflow outcome is the condition that holds once a run is over: the order shipped, the request
declined. It is a condition, not an action, and a workflow may have more than one. A trigger is
what starts a run. "End state" and "end event" are other names for an outcome, not
confusables.

### vs-trigger

- **goal:** `w-workflow-outcome`
- **move:** DISTINGUISH
- **answer:** An outcome is the condition that holds when a run is over, and a trigger is what
  starts a run. "Offer accepted" is both because it plays each role for a different
  workflow: it is how a hiring run ends and what starts an onboarding run.
- **credit:** full for naming that an outcome holds at the end of a run and a trigger is what a run
  starts from, and that which one "Offer accepted" is depends on whose run, hiring's or
  onboarding's. Half for the end-versus-start difference with the shared label left
  unexplained or called a mistake. None for an incidental difference alone, such as that a
  workflow can have several outcomes.

### catch-action

- **goal:** `w-workflow-outcome`
- **move:** CATCH
- **answer:** "Developer fixes the bug" is an action, a step, not an outcome. An outcome is a
  condition that holds once the run is over, such as "Bug fixed" or "Report closed". This workflow
  also has a second outcome, the report closed as "can't reproduce", which the label leaves out.
- **credit:** full for naming that the label is an action rather than a condition that holds at
  the end; the missing second outcome is welcome but not required. Half for noticing only the
  missing second outcome, with nothing on action versus condition. None for a different quibble
  alone, such as that a tester, not a developer, should confirm the fix.

### catch-pick

- **goal:** `w-workflow-outcome`
- **move:** CATCH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. Each is a condition that holds once a run is over, and this
  workflow has two. Choice 2 is an action, the last step, not a condition. Choice 3 is the
  trigger, what starts a run. Choice 4 stretches the word past one run: fewer
  complaints over a year is what the city hopes many runs add up to, not the condition any one
  run ends in.
