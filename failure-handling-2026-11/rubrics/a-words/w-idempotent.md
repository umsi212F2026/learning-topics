# Rubric: Idempotent

If the learner misses a question here, set a DEFINE or INTERPRET move for idempotent live, as help (it is recorded as helped and doesn't count), then come back to a production question.

A step is idempotent when running it several times leaves things the same as running it once, so it is safe to run again after a run stops partway. "Things" includes what the step does outside the workflow: a step that sends a message sends it again on a rerun, even if it changes no file. Changing nothing on a second run is not the same as changing nothing at all; an idempotent step may write plenty the first time. Deterministic is the course's contrast: a deterministic step gives the same output from the same input every time. The two are separate. In the reading's words, a step can be idempotent even when its executor is not predictable, because a step that skips what is already done never asks the agent twice. And a perfectly predictable step that adds to a total is not idempotent, because every run adds again.

Two DISTINGUISH questions against deterministic, kept on purpose (instructor's decision, 2026-11-15): `vs-deterministic-hana` is idempotent but not deterministic, `vs-deterministic-dues` the reverse, so between them they show the two words come apart both ways. They were one compound question until it was split because the two scenarios share nothing.

### vs-deterministic-hana

- **goal:** `w-idempotent`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Hana's step is idempotent: the program skips any entry that already has a summary and never saves a half-finished one, so a second run changes nothing. It is not deterministic, since the agent words each summary differently. A learner who answers 4 is reading idempotent as deterministic, so an unpredictable agent rules it out; ask what a second run would do to an entry that already has a summary.

### vs-deterministic-dues

- **goal:** `w-idempotent`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** The dues program is deterministic, since it does the same arithmetic every time, but not idempotent: run twice in a month, it adds $40. A learner who answers 3 is reading idempotent as deterministic, so a predictable program seems safe to rerun; ask what a member's balance would be after two runs on the first of the month.

### catch-pick

- **goal:** `w-idempotent`
- **move:** CATCH
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only. The step adds a row per workout without looking at the sheet, so a rerun adds the first three workouts a second time: running it twice does not leave things as running it once did. Choice 1 reads idempotent as its confusable: giving the same rows from the same export is being deterministic, and the same rows written twice are duplicates. Choice 2 reads "leaves things the same" as "changes nothing": an idempotent step may write to the sheet, as long as a second run adds nothing more. Choice 3 stretches the word to a step that never fails; idempotent is about what a rerun does, and a step that stops is just the case where that matters.

### catch-weekly-email

- **goal:** `w-idempotent`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. Leaving the sheet alone doesn't make the step idempotent: a rerun sends Jun a second email, so two runs don't leave things the same as one. Idempotent is about everything the step does, including actions outside the sheet. Choice 1 agrees with Jun, reading idempotent as "changes no stored data". Choice 2 is a different quibble: a wrong summary is a mistake, not a rerun problem. Choice 4 reads idempotent as its confusable: a summary that changes with the week's spending says nothing about what a second run on the same Sunday does.
- **tutor note:** a learner who picks 1 is reading idempotent as "changes no stored data"; ask what Jun's inbox holds after the step runs twice.
