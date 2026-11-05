# Rubric: Hook

If the learner misses a question here, set a DEFINE or INTERPRET move for hook live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A hook is an arrangement in which a tool or service runs your command, or sends you a message,
when something happens inside it, so you are told rather than having to ask. Event-driven names
something else: that a run starts because something happened, rather than at set times or when a
person starts it. A hook is one way an event-driven workflow learns of its event; polling is the
other, so a workflow can be event-driven with no hook. "Callback" and "webhook" are other names
for a hook, not confusables. A hook is not the place the work ends up, and it never involves the
workflow asking.

### vs-event-driven

- **goal:** `w-hook`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** both set-ups are event-driven, since each volunteer is added because a sign-up
  happened; only A uses a hook. A learner who marks (d) false thinks event-driven needs a hook;
  ask what makes a volunteer get added in set-up B.

#### a

- **type:** mcq
- **answer:** 1
- **tutor note:** the web-address setting is the hook: the form service sends a message when a
  sign-up happens, so the program is told rather than having to ask. The word "hook" never
  appears; recognizing one from its description is the point.

#### b

- **type:** mcq
- **answer:** 1

#### c

- **type:** mcq
- **answer:** 2
- **tutor note:** in B the program asks; nothing tells it. A hook is the form service running a
  command or sending a message when a sign-up happens.

#### d

- **type:** mcq
- **answer:** 1
- **tutor note:** the ten-minute asks are polling, a way of noticing the event; each volunteer is
  still added because a sign-up happened.

### catch-pick

- **goal:** `w-hook`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The hook is the arrangement: Git runs her command when a commit
  happens, so she is told rather than having to ask. Choice 1 takes the hook to be the place the
  work ends up. Choice 2 stretches the word to anything automatic; a cron job also runs with no
  person starting it, and is no hook. Choice 4 calls asking a hook; a script asking every hour is
  polling.
- **tutor note:** a learner who picks 2 is treating "hook" as "automatic"; ask whether a backup
  that runs every night at 1 a.m. would be a hook.

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
