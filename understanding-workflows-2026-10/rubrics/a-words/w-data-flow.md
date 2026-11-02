# Rubric: Data flow

If the learner misses a question here, set a DEFINE or INTERPRET move for data flow live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

Data flow is data one step writes and another step reads, possibly much later and not as the next
step: the dotted lines to and from files. It does not say which step runs next; that is control
flow, the solid arrows. A dotted line from a step to a file says the step writes it, not that the
run moves to the file. Data flow between steps done by different actors is also a handoff; inside
one lane it is not. "Data association" is another name for it, not a confusable.

### vs-control-flow

- **goal:** `w-data-flow`
- **move:** DISTINGUISH
- **answer:** Control flow is the solid arrows, saying which step runs next: booking the bus comes
  after collecting the slips. Data flow is the dotted lines, data one step writes and another
  reads: the slip list written when the slips are collected is read when attendance is taken,
  steps later and on another day, though no arrow joins those two steps.
- **credit:** full for naming that control flow says which step runs next and data flow is data
  one step leaves for another to read, which need not be the next step. Half for the right
  difference with the slip list read as the run moving to the file. None for an incidental
  difference alone, such as that one line is solid and the other dotted.

### catch-run-moves

- **goal:** `w-data-flow`
- **move:** CATCH
- **answer:** The dotted line does not move the run anywhere; it says "Mark the test" writes the
  grade into the gradebook, where a later step can read it. The gradebook is a file, not a step.
  Which step runs next is the solid arrow's job, and that says "Email the student".
- **credit:** full for naming that a dotted line is data written (or read), not the run moving, so
  the run goes next to "Email the student". Half for "the gradebook is not a step" with nothing on
  what the dotted line says. None for a different quibble alone, such as that the student should
  be emailed before the grade is recorded.

### catch-pick

- **goal:** `w-data-flow`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The weighing step writes the stock sheet and the planning step
  reads it on Friday: data one step leaves for another. Choice 1 reads a dotted line as the run
  moving; it says the step writes the stock sheet. Choice 2 forgets that data flow can be read
  much later. Choice 4 reads a solid arrow as data flow; it says which step runs next.
