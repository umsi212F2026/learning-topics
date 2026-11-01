diagram commit: eb7b655

The plane under `Set up the workspace` in `bootstrap.bpmn`, opened from the small arrow button at
the bottom-right corner of its box. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
start circle `setup-workspace skill invoked` (AI AGENT) leads to `Install tools; clone or update
the repositories` (AI AGENT), then `Check the repositories` (PROGRAM), then the split `repos
installed?`. Its `yes` goes to the split `how far did I get previously?`, with four branches:
`first time` to `Record where things live` (AI AGENT; its second line is `setup-addressing`, a
skill); `addressing done` to the merge before `Write the receipt`; `Installation 1 done` to the
merge before `Install the editors`; `Installation 2 done` to the merge before `Publish the
repositories`. `Record where things live` goes to `Check the addressing` (PROGRAM), then the split
`Address good?`, whose `yes` goes through the merge (AI AGENT, two arrows in, one out) to `Write
the receipt` (PROGRAM). A solid arrow joins `Write the receipt` directly to `Check the receipt
landed` (PROGRAM); then the split `receipt landed?`, whose `yes` goes to `Submit Installation 1`
(HUMAN), then through a merge to `Install the editors` (AI AGENT), `Check the editors` (PROGRAM)
and the split `editors installed?`, whose `yes` goes to `Submit Installation 2` (HUMAN). That goes
through a merge to `Publish the repositories` (AI AGENT), then `Check the remote` (PROGRAM) and the
split `remote set up?` (one arrow in), whose `yes` goes to `Submit Installation 3` (HUMAN), then
the end circle `set up, checked and submitted`. Every `no` goes to one unnamed merge and on to the
end circle `stopped at a checkpoint`. No step on this plane is drawn across lanes, and the plane
has no file. All gateways are exclusive.

Step pairs used here (step to step, gateways between ignored): `Check the addressing` to `Write
the receipt`, both PROGRAM, not a handoff; `Check the editors` (PROGRAM) to `Submit Installation
2` (HUMAN), a handoff.

Compound parts in this scenario: six, two True and four False.

### next-arrow

- **goal:** `c-read-diagram`
- **cases:** control-arrow
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** the arrow orders the two steps: the second runs once the first is done.

#### c

- **type:** mcq
- **answer:** 2
- **tutor note:** this plane has no file and no dotted line; a solid arrow says which step runs
  next, nothing about data.

### not-handoff

- **goal:** `c-read-diagram`
- **cases:** not-handoff
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** both steps sit in the PROGRAM lane. The merge between them sits in AI AGENT,
  which is where choice 1 comes from; a gateway's lane gives no step to an actor. A learner who
  picks 2 may be reading every arrow as a handoff.

### handoff

- **goal:** `c-read-diagram`
- **cases:** handoff
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the gateway between them is `editors installed?`, on its `yes` branch.

### lane-step

- **goal:** `c-read-diagram`
- **cases:** lane-owner
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** `setup-addressing` names a skill, not an actor; the lane is the only thing that
  says who does the step.

#### b

- **type:** mcq
- **answer:** 1

#### c

- **type:** mcq
- **answer:** 2

### split-after-remote

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** the diamond meant is `remote set up?`: one arrow in, `yes` to `Submit
  Installation 3` and `no` to the merge before `stopped at a checkpoint`.

### merge-before-receipt

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** two arrows come in (`yes` from `Address good?`, `addressing done` from `how far
  did I get previously?`) and one goes out to `Write the receipt`.

### after-step

- **goal:** `c-read-diagram`
- **cases:** trace-steps
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** the arrow from `Submit Installation 1` passes through a merge on the way to
  `Install the editors`.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
