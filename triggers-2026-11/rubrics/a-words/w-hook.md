# Rubric: Hook

If the learner misses a question here, set a DEFINE or INTERPRET move for hook live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A hook is a place where a tool or service runs your command, or sends your address a message,
when something happens inside it, so you are told rather than having to ask. Event-driven names
something else: that a run starts because something happened, rather than at set times or when a
person starts it. A hook is one way an event-driven workflow learns of its event; polling is the
other, so a workflow can be event-driven with no hook. "Callback" and "webhook" are other names
for a hook, not confusables. A hook is not the place the work ends up, and it never involves the
workflow asking.

### vs-event-driven

- **goal:** `w-hook`
- **move:** DISTINGUISH
- **answer:** Event-driven says why each run starts: because something happened, a form being
  submitted, rather than at set times or because a person started it. The hook is the place in
  the form service where the coordinator entered her web address, so the service tells her
  program when a form is submitted. The hook is how the program learns of the event; the workflow
  could still be event-driven without one, by checking the form service again and again.
- **credit:** full for naming that event-driven is about what starts a run (something happening)
  and the hook is the place in the tool that tells the program when it happens, matched to this
  workflow. Saying that an event-driven workflow could do without a hook by polling is welcome but
  not required. Half for "the hook is the specific mechanism and event-driven is the general
  idea" with nothing on what each does. Half at most for the right difference joined to a claim
  that every event-driven workflow needs a hook. None for treating the two as names for one
  thing.
- **tutor note:** if the learner says they are the same, ask how the program would learn of a new
  sign-up if the form service had no setting for a web address.

### catch-pick

- **goal:** `w-hook`
- **move:** CATCH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. The hook is the place in git where she named a command, which git
  runs when a commit happens. Choice 1 stretches the word to the place the work ends up. Choice 3
  reads a hook as checking again and again, which is polling; with a hook, git tells, nobody
  asks. Choice 4 reads hook as another name for event-driven: the backup is event-driven, and the
  hook is how it learns of each commit.

### catch-weather

- **goal:** `w-hook`
- **move:** CATCH
- **answer:** That isn't a hook. The script asks the weather service every hour whether there is a
  warning, which is polling. With a hook, the weather service would send the farm's address a
  message, or run its command, when a warning is issued, and the script would never have to ask.
- **credit:** full for naming that the script is asking rather than being told, so this is
  polling and not a hook; naming polling is welcome but not required. Half for "that's polling"
  with nothing on why a hook is different. None for a different quibble alone, such as that once
  an hour is too seldom for storm warnings.
