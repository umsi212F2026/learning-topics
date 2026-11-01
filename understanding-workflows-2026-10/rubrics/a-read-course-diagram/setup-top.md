diagram commit: eb7b655

The top plane of `bootstrap.bpmn`. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
run starts at `opens the Day 1 page in Canvas` (HUMAN) and goes to `Get Codex running`, a
collapsed subprocess drawn across the HUMAN operator and AI AGENT lanes. Then the split `Codex
running?`: `success` goes to an unnamed merge and on to `Set up the workspace` (a collapsed
subprocess drawn across all three lanes, HUMAN operator, AI AGENT and PROGRAM); `stuck` goes to a
second unnamed merge and on to `Report being stuck` (HUMAN), then the end circle `blocked`. After
`Set up the workspace`, the split `Able to complete?`: `yes` goes to `Check the install`
(PROGRAM, to the right of `Set up the workspace`); `no` goes through the merge before `Report
being stuck`. After `Check the install`, the split `install correct?` (also in PROGRAM, to its
right): `success` goes to `Submit each session's report` (HUMAN), then the end circle `workspace
ready`; `not yet` loops back through the merge before `Set up the workspace`. The file `U-M API
key` is not asked about.

The plane carries no handoff question: with the two boxes drawn across lanes left out, its only
step-to-step pair is `Check the install` to `Submit each session's report`.

### start-circle

- **goal:** `c-read-diagram`
- **cases:** states
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### end-circle

- **goal:** `c-read-diagram`
- **cases:** states
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.

### plain-step

- **goal:** `c-read-diagram`
- **cases:** step-box
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.

### subprocess

- **goal:** `c-read-diagram`
- **cases:** subprocess-box
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### gateway

- **goal:** `c-read-diagram`
- **cases:** gateway-shape
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.

### lane-span

- **goal:** `c-read-diagram`
- **cases:** spans-lanes
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** the box runs from the HUMAN operator lane down into PROGRAM, and the plane
  under it has steps in all three lanes.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **answer:** any one of the three named gateways: `Codex running?` (just after `Get Codex
  running`, before the merge before `Set up the workspace` and the merge before `Report being
  stuck`); `Able to complete?` (just after `Set up the workspace`, before `Check the install` and
  the merge before `Report being stuck`); `install correct?` (just after `Check the install`,
  before `Submit each session's report` and the merge before `Set up the workspace`).
- **credit:** full for any one of the three named gateways, pointed at by its neighbors or named
  by its label; none for an unnamed merge or a step. Credit a paraphrased step or gateway name
  when it is clear which element is meant; ask which only when it is not.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **answer:** either unnamed gateway: the one just before `Set up the workspace` (after `Codex
  running?` and `install correct?`), or the one just before `Report being stuck` (after `Codex
  running?` and `Able to complete?`).
- **credit:** full for either unnamed gateway; none for a named gateway or a step. Credit a
  paraphrased step or gateway name when it is clear which element is meant; ask which only when
  it is not.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-loop
- **answer:** if `success`, `Submit each session's report`; if `not yet`, back to `Set up the
  workspace`.
- **credit:** full when both branches are there with their labels and the right step; half when
  one branch is missing, or one label or one destination is wrong; none when only one next step is
  given with no condition, or more than one part is wrong. Credit a paraphrased step name when
  it is clear which step is meant; ask which only when it is not.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
