# Rubric: Simulation trial

If the learner misses a question here, set a DEFINE or INTERPRET move for simulation trial live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A simulation trial is one run of the model from start to finish, with its chance events drawn
afresh. "Run", "replication" and "iteration" are other names for it, not confusables. Every trial
of one setting uses the same model parameters; only the chance draws differ. Changing a parameter
and running again starts a new setting, whose trials are compared with the first setting's, not
added to them. A trial is the whole run, not one step inside it, not a batch of many runs, and not
a test of the real thing.

### vs-different-parameters

- **goal:** `w-simulation-trial`
- **move:** DISTINGUISH
- **answer:** One more trial with 12 stations is the same model with the same parameters, only
  with runners' arrival moments drawn afresh, so it adds to the 12-station results. The run with 15
  stations changes a model parameter, so it belongs to a new setting: its trials make a separate
  set of results, to be compared with the 12-station ones, not pooled with them.
- **credit:** full for naming that a trial keeps every parameter the same and differs only in its
  fresh chance draws, while the 15-station run changes a parameter and so starts a different
  setting whose results are compared with, not added to, the first. Half for saying that one
  changes the number of stations and the other doesn't, without saying what a trial does vary (its
  chance draws) or that the two sets are compared rather than pooled. None for an incidental
  difference alone, such as that 15 stations should give shorter lines.

### catch-each-roll

- **goal:** `w-simulation-trial`
- **move:** CATCH
- **answer:** A simulation trial is one run of the model from start to finish: here, one whole game,
  from the first roll until someone reaches square 100. Each roll is one chance event inside a
  trial, so a 40-turn game is one trial that lasted 40 turns.
- **credit:** full for naming that a trial is one whole game played from start to finish, and that
  the rolls are chance events within it. Half for saying they need many games to answer their
  question without saying that one game, not one roll, is a trial. None for a different quibble
  alone, such as that the model leaves out how players choose their moves.

### catch-pick

- **goal:** `w-simulation-trial`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. One simulated weekday, run from start to finish with its calls drawn
  afresh, is one trial. Choice 1 is many trials of the 8-agent setting, not one. Choice 2 changes a
  model parameter, so the 9-agent day is a trial of a new setting, not one more trial of the 8-agent
  one. Choice 4 is a test of the real call center, with real agents and real calls; nothing
  simulated is run.
- **tutor note:** a learner who picks 2 is counting runs of the program; ask whether the 9-agent
  day's result belongs with the other 500 when the call center asks what happens with 8 agents.
