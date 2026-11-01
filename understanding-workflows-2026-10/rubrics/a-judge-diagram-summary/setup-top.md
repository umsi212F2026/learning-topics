diagram commit: eb7b655

The top plane of `bootstrap.bpmn`. Lanes, top to bottom: HUMAN operator, AI AGENT, PROGRAM. The
start circle `opens the Day 1 page in Canvas` (HUMAN) marks what starts a run, its trigger, a
person's action. It leads to `Get Codex running`, a collapsed subprocess drawn across the HUMAN
operator and AI AGENT lanes. Then the split `Codex running?` (HUMAN): `success` goes to an unnamed
merge (AI AGENT) and on to `Set up the workspace`, a collapsed subprocess drawn across all three
lanes; `stuck` goes to a second unnamed merge (HUMAN, two arrows in, one out) and on to `Report
being stuck` (HUMAN), then the end circle `blocked`. After `Set up the workspace`, the split `Able
to complete?` (AI AGENT): `yes` goes to `Check the install` (PROGRAM); `no` goes through the merge
before `Report being stuck`. After `Check the install`, the split `install correct?` (PROGRAM):
`success` goes to `Submit each session's report` (HUMAN), then the end circle `workspace ready`;
`not yet` loops back through the merge before `Set up the workspace`. All gateways are exclusive,
so a run takes one path out of a split. The file `U-M API key` is not asked about, and no question
here asks about a handoff.

Compound parts in this scenario: five, two True and three False.

### end-circle

- **goal:** `c-read-diagram`
- **cases:** states
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### plain-step

- **goal:** `c-read-diagram`
- **cases:** step-box
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.

### gateway

- **goal:** `c-read-diagram`
- **cases:** gateway-shape
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** this diamond is the merge before `Set up the workspace`; don't confirm or deny
  whether it splits or merges, which a later question asks about another diamond.

### subprocess

- **goal:** `c-read-diagram`
- **cases:** subprocess-box
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.

### lane-span

- **goal:** `c-read-diagram`
- **cases:** spans-lanes
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** the box is drawn across all three lanes; its own plane has steps in each.

#### b

- **type:** mcq
- **answer:** 1

#### c

- **type:** mcq
- **answer:** 2
- **tutor note:** the box reaches down into the PROGRAM lane; that is easy to miss when it sits
  mostly in AI AGENT.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** two arrows come in (`stuck` from the split after `Get Codex running`, `no` from
  the split after `Set up the workspace`) and one goes out to `Report being stuck`.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-steps
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** `not yet` loops back through the merge to `Set up the workspace`; `blocked` is
  reached only through `Report being stuck`.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
