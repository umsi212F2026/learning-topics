diagram commit: 6b578e9

The top plane of `bootstrap.bpmn`. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
run starts at `opens the Day 1 page in Canvas` (HUMAN) and goes to `Get Codex running`, a
collapsed subprocess drawn across the HUMAN operator and AI AGENT lanes. Then the split `Codex
running?`: `success` goes to an unnamed merge and on to `Set up the workspace` (a collapsed
subprocess in AI AGENT); `stuck` goes to a second unnamed merge and on to `Report being stuck`
(HUMAN), then the end state `blocked`. After `Set up the workspace`, the split `Able to
complete?`: `yes` goes to `Check the install` (PROGRAM); `no` goes through the merge before
`Report being stuck`. After `Check the install`, the split `install correct?`: `success` goes to
`Submit each session's report` (HUMAN), then the end state `workspace ready`; `not yet` loops back
through the merge before `Set up the workspace`. The file `U-M API key` is not asked about.

Handoff pairs on this plane (step to step, gateways between ignored): `Set up the workspace` to
`Check the install`, `Set up the workspace` to `Report being stuck`, `Check the install` to
`Submit each session's report`, and `Check the install` back to `Set up the workspace`. No pair
includes `Get Codex running`, which is drawn across two lanes.

### start-state

- **goal:** `c-read-diagram`
- **cases:** states
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### end-state

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
- **answer:** 4
- **credit:** full for 4 only.

### gateway

- **goal:** `c-read-diagram`
- **cases:** gateway-shape
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.

### lane-step

- **goal:** `c-read-diagram`
- **cases:** lane-owner
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** `Check the install` sits in the PROGRAM lane. A learner who picks the human may
  be going by the word "check" rather than the lane. This is the weaker `lane-owner` form: on
  this plane the labels give the answer away (`Check the install`'s second line names
  `check-setup.mjs`, and the human steps say "on Canvas"). The stronger form is `lane-step` on
  `set-up-workspace`.

### lane-span

- **goal:** `c-read-diagram`
- **cases:** spans-lanes
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### handoff

- **goal:** `c-read-diagram`
- **cases:** handoff
- **answer:** any one of the four handoff pairs in the key above, for example `Check the install`
  to `Submit each session's report`.
- **credit:** full for one of the four accepted pairs; none otherwise. The two steps may be named
  in either order. A learner who names an arrow ending at a gateway is not marked wrong: credit it
  when the steps on either side of that gateway make an accepted pair, and otherwise ask which
  steps they mean. Credit a paraphrased step name when it is clear which step is meant; ask which only when it is not.
- **tutor note:** a pair with `Get Codex running` in it is not accepted, since that step is drawn
  across two lanes; say so and ask for another.

### after-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **answer:** if `yes`, `Check the install`; if `no`, `Report being stuck`.
- **credit:** full when both branches are there with their labels and the right step; half when
  one branch is missing, or one label or one destination is wrong; none when only one next step is
  given with no condition, or more than one part is wrong. Credit a paraphrased step name when
  it is clear which step is meant; ask which only when it is not.

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
- **cases:** trace-steps
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
