diagram commit: eb7b655

The top plane of `bootstrap.bpmn`. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
start circle `opens the Day 1 page in Canvas` (HUMAN) marks what starts a run, its trigger, a
person's action. It leads to `Get Codex running`, a collapsed subprocess drawn across the HUMAN
operator and AI AGENT lanes and not reaching PROGRAM. Then the split `Codex running?` (HUMAN):
`success` goes to an unnamed merge (AI AGENT) and on to `Set up the workspace`, a collapsed
subprocess drawn across all three lanes (declared in AI AGENT); `stuck` goes to a second unnamed
merge (HUMAN, two arrows in, one out) and on to `Report being stuck` (HUMAN), then the end circle
`blocked` (its label goes on past the first word). After `Set up the workspace`, the split `Able
to complete?` (AI AGENT): `yes` goes to `Check the install` (PROGRAM); `no` goes through the merge
before `Report being stuck`. After `Check the install`, the split `install correct?` (PROGRAM):
`success` goes to `Submit each session's report` (HUMAN), then the end circle `workspace ready`;
`not yet` loops back through the merge before `Set up the workspace`. All gateways are exclusive,
so a run takes one path out of a split. The file `U-M API key` is not asked about, and no question
here asks about a handoff.

Compound parts in this scenario: five, three True and two False.

### start-circle

- **goal:** `c-read-diagram`
- **cases:** states
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** choice 1 reads the trigger as a step because its label is an action; choice 2
  confuses the circle with the box beside it.

### plain-step

- **goal:** `c-read-diagram`
- **cases:** step-box
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** choice 1 confuses the box with the end circle `workspace ready` after it; choice 3
  comes from the label naming several reports. The box has no plus.

### gateway

- **goal:** `c-read-diagram`
- **cases:** gateway-shape
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** this diamond is the unnamed merge before `Report being stuck`, in the HUMAN lane;
  a gateway's lane does not make it a step. Don't confirm or deny whether it splits or merges.

### subprocess

- **goal:** `c-read-diagram`
- **cases:** subprocess-box
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** the box carries a plus and the small arrow button; the diagram under it is its
  own, with its own steps, not the one under `Get Codex running`.

### lane-span

- **goal:** `c-read-diagram`
- **cases:** spans-lanes
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** the box stops at the bottom of the AI AGENT lane. The program step on this plane
  is `Check the install`, a separate box.

#### c

- **type:** mcq
- **answer:** 1
- **tutor note:** the box is declared in the HUMAN lane but drawn down into AI AGENT; the drawing
  is what says who takes part.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** the diamond meant is `Able to complete?`: one arrow in, `yes` to `Check the
  install` and `no` to the merge before `Report being stuck`. Choice 3 names the question of the
  diamond after `Check the install`.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** two arrows come in (`success` from the split after `Get Codex running`, `not yet`
  from the split after `Check the install`) and one goes out to `Set up the workspace`. The `stuck`
  path goes to the other merge, before `Report being stuck`.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-loop
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** on `success` the run goes to `Submit each session's report`; the labels are
  swapped in this sentence.

#### b

- **type:** mcq
- **answer:** 1
- **tutor note:** `not yet` loops back through the merge to `Set up the workspace`.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** the step is not the end; the circle after it is. `workspace ready` is the other
  outcome, reached only after `Submit each session's report`.
