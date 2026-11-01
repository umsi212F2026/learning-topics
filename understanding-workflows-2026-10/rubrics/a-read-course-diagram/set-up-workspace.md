diagram commit: 6b578e9

The plane under `Set up the workspace` in `bootstrap.bpmn`. Lanes, top to bottom: HUMAN
operator, AI AGENT, PROGRAM. The run starts at `setup-workspace skill invoked` (AI AGENT) and goes
to `Install tools; clone or update the repositories` (AI AGENT), then `Check the repositories`
(PROGRAM), then the split `repos installed?`. Its `yes` goes to the split `how far did I get
previously?`, which has four branches: `first time` to `Record where things live` (AI AGENT);
`addressing done` to the merge before `Write the receipt`; `Installation 1 done` to the merge
before `Install the editors`; `Installation 2 done` to the merge before `Publish the
repositories`. `Record where things live` goes to `Check the addressing` (PROGRAM), then the split
`Address good?`, whose `yes` goes through the merge to `Write the receipt` (PROGRAM). A solid arrow
joins `Write the receipt` directly to `Check the receipt landed` (PROGRAM); then the split `receipt
landed?`, whose `yes` goes to `Submit Installation 1` (HUMAN), which goes through a merge to
`Install the editors` (AI AGENT), then `Check the editors` (PROGRAM) and the split `editors
installed?`, whose `yes` goes to `Submit Installation 2` (HUMAN). That goes through a merge to
`Publish the repositories` (AI AGENT), then `Check the remote` (PROGRAM) and the split `remote set
up?`, whose `yes` goes to `Submit Installation 3` (HUMAN), then the end state `set up, checked and
submitted`. Every `no` (from `repos installed?`, `Address good?`, `receipt landed?`, `editors
installed?` and `remote set up?`) goes to one unnamed merge and on to the end state `stopped at a
checkpoint`.

Six named splits, four unnamed merges (before `Write the receipt`, before `Install the editors`,
before `Publish the repositories`, and before `stopped at a checkpoint`), two end states, no file.

Step pairs on this plane (step to step, gateways between ignored). Same actor, all PROGRAM: `Write
the receipt` to `Check the receipt landed`; `Check the repositories` to `Write the receipt`;
`Check the addressing` to `Write the receipt`. Handoffs: `Install tools; clone or update the
repositories` to `Check the repositories`; `Check the repositories` to `Record where things live`, to `Install the editors`,
or to `Publish the repositories`; `Record where things live` to `Check the addressing`; `Check the
receipt landed` to `Submit Installation 1`; `Submit Installation 1` to `Install the editors`;
`Install the editors` to `Check the editors`; `Check the editors` to `Submit Installation 2`;
`Submit Installation 2` to `Publish the repositories`; `Publish the repositories` to `Check the
remote`; `Check the remote` to `Submit Installation 3`.

### next-arrow

- **goal:** `c-read-diagram`
- **cases:** control-arrow
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### not-handoff

- **goal:** `c-read-diagram`
- **cases:** handoff
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** both steps sit in the PROGRAM lane, so the same actor does both. A learner who
  says yes may be reading every arrow as a handoff, as the session 2 glossary slide invites.

### handoff

- **goal:** `c-read-diagram`
- **cases:** handoff
- **answer:** any one of the handoff pairs in the key above, for example `Check the editors` to
  `Submit Installation 2`.
- **credit:** full for one of the accepted handoff pairs; none otherwise, including any of the
  three same-actor pairs. The two steps may be named in either order. A learner who names an arrow
  ending at a gateway is not marked wrong: credit it when the steps on either side of that gateway
  make an accepted pair, and otherwise ask which steps they mean. Credit a paraphrased step name
  when it is clear which step is meant; ask which only when it is not.
- **tutor note:** a learner who names `Write the receipt` and `Check the receipt landed` has
  missed that both are in PROGRAM; ask who does each.

### split-after-editors

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.

### merge-after-submit-2

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the paths that come back together here are the one from `Submit Installation 2`
  and the `Installation 2 done` branch from `how far did I get previously?`.

### split-after-receipt

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** the diamond meant is `receipt landed?`: `yes` to `Submit Installation 1`, `no`
  to the merge before `stopped at a checkpoint`.

### after-step

- **goal:** `c-read-diagram`
- **cases:** trace-steps
- **answer:** `Install the editors`, through the merge just after `Submit Installation 1`.
- **credit:** full for `Install the editors`; none otherwise. Mentioning the merge on the way is
  fine. Credit a paraphrased step name when it is clear which step is meant; ask which only when
  it is not.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
