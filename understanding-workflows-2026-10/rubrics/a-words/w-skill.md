# Rubric: Skill

If the learner misses a question here, set a DEFINE or INTERPRET move for skill live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A skill is the written instructions an AI agent follows for a step, kept in a file the agent reads
each time the step runs. The agent brings judgment to whatever the file doesn't settle. A script
is instructions a computer follows exactly, with no judgment. A prompt is a one-off message
someone sends an agent in the moment; a skill is standing instructions. Everyday shorthand that
gives the skill credit ("the skill sorts the issues") is fine and is not a misuse; the misuses are
treating the skill as the thing that carries out the step, as if no agent were needed, or as code
that runs exactly.

### vs-script

- **goal:** `w-skill`
- **move:** DISTINGUISH
- **answer:** Both are instructions, but a script is followed by a computer exactly, with no
  judgment: every photo is shrunk to 800 pixels, every time. A skill is followed by an AI agent,
  which brings judgment to what the file doesn't settle: the file never said what to do with a
  photo that has no notes, so the scene caption was the agent's call.
- **credit:** full for naming that a script is followed exactly with no judgment and a skill is
  followed by an AI agent that brings judgment where the file leaves a case open; the no-notes
  photo as the example is welcome but not required. Half for naming only that a computer follows
  the script and an AI agent follows the skill, with nothing on exactness or judgment. None for an
  incidental difference alone, such as that the skill is written in plain English or the files
  end differently.

### vs-prompt

- **goal:** `w-skill`
- **move:** DISTINGUISH
- **answer:** The skill is newsletter.md: standing instructions kept in a file that the agent reads
  every Monday, each time it drafts. The owner's typed message is a prompt: a one-off, sent in the
  moment for this Monday only, so next week's draft won't mention the signing unless someone sends
  it again or puts it in the file.
- **credit:** full for naming either difference: that the skill is standing instructions the agent
  reads on every run and the prompt is a one-off message for this run only, or that the skill is
  kept in a file the agent reads and the prompt is a message typed to it. None for an incidental
  difference alone, such as that the skill is
  longer or more general, or that the owner wrote one and not the other (she may have written
  both).

### catch-exact

- **goal:** `w-skill`
- **move:** CATCH
- **answer:** A skill is not code that runs exactly. It is instructions an AI agent follows, and
  the agent brings judgment to whatever the file doesn't settle, so the results need checking. A
  rename that must match a pattern exactly is a job for a script, which a computer follows exactly.
- **credit:** full for naming that a skill is followed by an AI agent that brings its own judgment,
  not run exactly like code; saying a script would fit the job is welcome but not required. Half
  for "the AI agent might make mistakes" with nothing on the skill being instructions for an agent
  rather than code that runs exactly. None for a different quibble alone, such as that the files
  should be backed up first.

### catch-pick

- **goal:** `w-skill`
- **move:** CATCH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. The skill is instructions; whether a crash request is a bug report
  or a feature request is a case it doesn't settle, so the label was the agent's judgment. Choice
  2 reads the skill as a script that runs exactly. Choice 3 treats the skill as the executor,
  though the setup says an AI agent does the sorting. Choice 4 takes the everyday sense of
  "skill", a person's know-how, which is not what the word names here.
- **tutor note:** a learner who picks 3 may be reading it as everyday shorthand ("the skill
  labels the issues"), which would be fine; what makes 3 wrong is "with no agent there to follow
  it". Ask who reads triage.md.
