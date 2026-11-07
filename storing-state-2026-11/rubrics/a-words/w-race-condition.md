# Rubric: Race condition

If the learner misses a question here, set a DEFINE or INTERPRET move for race condition live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A race condition is a fault in which the result depends on which of two things running at the same
time gets there first, such as two runs each saving over the other's changes. It needs more than
one writer at once and at least one of them changing what is already there; writers that only
append, or storage built for simultaneous edits, leave no race. Two things at once is not by itself
a race, and neither is the slowness that lets them overlap. A merge conflict is the course's
contrast: the same collision, but noticed and stopped for someone to resolve, rather than one
writer quietly winning. In the reading's words, a merge conflict is a race detected rather than
prevented.

### vs-merge-conflict

- **goal:** `w-race-condition`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** Monday is a race condition: the script and Dana changed the file at the same
  time, the later save quietly won, and the sign-ups were lost with no warning. Tuesday is best
  called a merge conflict: the same kind of collision, but Git noticed it and stopped to ask, so
  nothing was lost. A learner who answers race condition for Tuesday has seen the collision but
  not the detection; ask what Git did that the shared drive didn't. One who answers neither for
  Tuesday may think a merge conflict isn't a collision at all; ask what Luis and Mei both did to
  the same plot's line.

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2

### catch-pick

- **goal:** `w-race-condition`
- **move:** CATCH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. Two runs at once each save back the whole sheet, so whichever saves
  last wipes out what the other added: a race. Choice 1 misses that two runs of the same workflow
  can race, as the reading says. Choice 3 reads race condition as its confusable: stopping to ask
  is what a merge conflict does, and a race is the case where nothing stops. Choice 4 stretches
  the word to the slowness that lets the runs overlap; the race is the lost entries, not the long
  run.

### catch-nightly

- **goal:** `w-race-condition`
- **move:** CATCH
- **answer:** That isn't a race condition. There is only one writer, the nightly program, and
  nothing else runs at that hour, so nothing depends on who gets there first. The sign-ups were
  lost because the program copies in the wrong direction: a mistake in what the program does, not
  a race.
- **credit:** full for naming that there is only one writer and nothing running at the same time,
  so the result can't depend on which got there first, and so this is not a race condition. Naming
  it a settings mistake or a copy in the wrong direction is welcome but not required. Half for
  "it's a settings mistake" or "it copied the wrong way" with nothing on why that rules out a
  race. None for a different quibble alone, such as that the club should keep more than one
  backup.
- **tutor note:** a learner who says the backup "raced" the current list is reading race as any
  overwrite; ask what second thing was running at 2 a.m.
