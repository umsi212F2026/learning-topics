diagram commit: eb7b655

The plane under `Set up the workspace` in `bootstrap.bpmn`, opened from the small arrow button at
the bottom-right corner of its box. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
start circle `setup-workspace skill invoked` (AI AGENT) leads to `Install tools; clone or update
the repositories` (AI AGENT; its second line is `setup-repos`, a skill), then `Check the
repositories` (PROGRAM), then the split `repos installed?`. Its `yes` goes to the split `how far
did I get previously?`, with four branches: `first time` to `Record where things live` (AI AGENT);
`addressing done` to the merge before `Write the receipt`; `Installation 1 done` to the merge
before `Install the editors`; `Installation 2 done` to the merge before `Publish the
repositories`. `Record where things live` goes to `Check the addressing` (PROGRAM), then the split
`Address good?`, whose `yes` goes through the merge (AI AGENT, two arrows in, one out) to `Write
the receipt` (PROGRAM). A solid arrow joins `Write the receipt` directly to `Check the receipt
landed` (PROGRAM); then the split `receipt landed?`, whose `yes` goes to `Submit Installation 1`
(HUMAN), then through a merge (AI AGENT) to `Install the editors` (AI AGENT), `Check the editors`
(PROGRAM) and the split `editors installed?`, whose `yes` goes to `Submit Installation 2` (HUMAN).
That goes through a merge to `Publish the repositories` (AI AGENT), joined by a solid arrow
directly to `Check the remote` (PROGRAM), then the split `remote set up?` (one arrow in), whose
`yes` goes to `Submit Installation 3` (HUMAN), then the end circle `set up, checked and
submitted`. Every `no` (five of them) goes to one unnamed merge and on to the end circle `stopped
at a checkpoint`. No step on this plane is drawn across lanes, and the plane has no file. All
gateways are exclusive.

Step pairs used here (step to step, gateways between ignored): `Check the addressing` to `Write
the receipt`, both PROGRAM, not a handoff; `Submit Installation 1` (HUMAN) to `Install the
editors` (AI AGENT), a handoff. Gateways between two steps don't break a pair, so a choice saying a
gateway between them decides it is wrong.

Compound parts in this scenario: nine, four True and five False.

### next-arrow

- **goal:** `c-read-diagram`
- **cases:** control-arrow
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** `Check the remote` and the split `remote set up?` come between; `Submit
  Installation 3` is two steps on.

#### b

- **type:** mcq
- **answer:** 1

#### c

- **type:** mcq
- **answer:** 2
- **tutor note:** a plain solid arrow says only which step runs next. The condition is drawn after
  `Check the remote`, at the split.

### not-handoff

- **goal:** `c-read-diagram`
- **cases:** not-handoff
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** both steps sit in the PROGRAM lane. The merge between them sits in AI AGENT,
  which is where choice 2 comes from; a gateway's lane gives no step to an actor. Choice 1 reads
  the label's verb as the agent's.

### handoff

- **goal:** `c-read-diagram`
- **cases:** handoff
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** `Submit Installation 1` is in HUMAN and `Install the editors` in AI AGENT; the
  merge between them doesn't break the pair. Choice 4 comes from the install-then-check pattern,
  where a program step follows.

### lane-step

- **goal:** `c-read-diagram`
- **cases:** lane-owner
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** `setup-repos` names a skill, not an actor; the lane is the only thing that says
  who does the step.

#### c

- **type:** mcq
- **answer:** 2

### split-after-remote

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** the diamond meant is `remote set up?`: one arrow in, `yes` to `Submit
  Installation 3` and `no` to the merge before `stopped at a checkpoint`. Choice 2 names the
  question of the split after `Check the editors`.

### merge-before-stop

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** five arrows come in, the `no` from each of `repos installed?`, `Address good?`,
  `receipt landed?`, `editors installed?` and `remote set up?`, and one goes out to `stopped at a
  checkpoint`. `first time` goes to `Record where things live`.

### after-branches

- **goal:** `c-read-diagram`
- **cases:** trace-branches
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** on `yes` the run reaches `Submit Installation 1` first; `Install the editors`
  comes after it.

#### b

- **type:** mcq
- **answer:** 1

#### c

- **type:** mcq
- **answer:** 1
- **tutor note:** the `no` arrow passes through the merge before the end circle.

### after-step

- **goal:** `c-read-diagram`
- **cases:** trace-steps
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the arrow from `Submit Installation 2` passes through a merge on the way to
  `Publish the repositories`. `Check the remote` is two steps on.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** the step is not the end; the circle after it is.
