# Rubric: Handoff

If the learner misses a question here, set a DEFINE or INTERPRET move for handoff live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A handoff is where work passes from a step done by one actor to a step done by another. There are
two kinds of flow: control flow (solid arrows, which step runs next) and data flow (dotted lines,
data one step writes and another reads, possibly later). A handoff is either kind when the two
steps belong to different actors; on a diagram, the flow crosses lanes. A control flow or data flow
inside one lane is not a handoff. Data one actor's step leaves for another actor's step to pick up
later is a handoff, even with no solid arrow between them.

The session 2 deck labels its arrow symbol "Handoff: between actors or to/from a document". The
"between actors" part agrees with this topic. A line to or from a document is a handoff only when
the step on the other side of that data belongs to a different actor. A learner who reads every
arrow, or every line to a file, as a handoff is reading the slide; that is the confusion these
questions are aimed at.

### vs-control-flow

- **goal:** `w-handoff`
- **move:** DISTINGUISH
- **answer:** any solid arrow that stays inside one lane: "Check in the patient" to "Pull up the
  chart" (both Receptionist), or "Examine the patient" to "Write treatment notes" (both Dentist).
  Each says which step runs next, and the same actor does both steps, so nothing passes to anyone
  else.
- **credit:** full for either of those two pairs, named in either order; a paraphrased step name
  counts when it is clear which step is meant. None for "Pull up the chart" to "Examine the
  patient", which crosses into the Dentist lane and so is a handoff, or for the treatment plan,
  which is data flow between actors and also a handoff.
- **tutor note:** a learner who names the arrow from "Pull up the chart" to "Examine the patient"
  has missed that it crosses lanes; ask who does each of its two steps.

### catch-every-arrow

- **goal:** `w-handoff`
- **move:** CATCH
- **answer:** Only one of those arrows is a handoff. A handoff is where work passes to a step done
  by a different actor, and only the arrow from "Put it on the cart" into the Shelver lane does
  that. The arrows between the desk clerk's own steps are control flow inside one lane: they say
  which step runs next, with no change of who does it.
- **credit:** full for naming that a handoff needs the work to pass to a different actor, so the
  arrows inside the Desk clerk lane are not handoffs. Half for "only the last arrow is a handoff"
  with no reason that rests on who does the steps. None for a different quibble alone, such as
  that checking for damage should come before scanning.

### catch-pick

- **goal:** `w-handoff`
- **move:** CATCH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. The office manager writes the job sheet and the crew lead reads it
  the next morning, so data passes from one actor's step to another's: a data handoff. Choice 2
  reads handoff as control flow; both of those steps are the office manager's, so that arrow is
  control flow inside one lane. Choice 3 takes the slide's "to/from a document" too far: the same
  actor writes and reads the booking log, so nothing passes to anyone else. Choice 4 stretches
  the word to anything moving; both steps are the crew lead's.
