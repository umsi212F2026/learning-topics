diagram commit: eb7b655

The plane under `Get Codex running` in `bootstrap.bpmn`, opened from the small arrow button at the
bottom-right corner of its box. Lanes, top to bottom: HUMAN operator, AI AGENT. The start circle
`Day 1 page opened` (HUMAN) leads to `Open U-M GPT; paste the bootstrap prompt` (HUMAN), which
reads the file `bootstrap-prompt.md` (a dotted line from the file to the step; the step's second
label line names the file's path). Then an unnamed merge (HUMAN, three arrows in, one out) and on
to `Do the next step on the checklist` (HUMAN). Then the split `stuck?` (HUMAN): `yes` goes down
to `Provide explanations and suggestions` (AI AGENT); `no` stays in HUMAN and goes to the split
`checklist done?`, whose `yes` goes to the end circle `Codex answers with the U-M key` and whose
`no` loops back through the merge to `Do the next step on the checklist`. After `Provide
explanations and suggestions`, the split `worth trying?`: `try suggestion` loops back through the
merge to `Do the next step on the checklist`; `give up` goes to `Write a status report on where it
stalled` (AI AGENT), then the end circle `stuck` (its label goes on past the first word). All
gateways are exclusive, so a run takes one path out of a split. No question here asks about a
handoff or a shape's kind.

Compound parts in this scenario: two, one True and one False.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the diamond meant is `stuck?`: one arrow in, `yes` to `Provide explanations and
  suggestions` and `no` to `checklist done?`. Choice 4 is half right: it names the question of
  the next diamond.

### branch-label

- **goal:** `c-read-diagram`
- **cases:** branch-label
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** the diamond meant is `checklist done?`. Its `no` arrow reaches the merge just
  before `Do the next step on the checklist`, so the run goes back to that step; its `yes` arrow
  ends the run in `Codex answers with the U-M key`. Choices 1 and 4 swap the labels; choice 2
  names the step on the `yes` branch of `stuck?`.

### file-line

- **goal:** `c-read-diagram`
- **cases:** data-line
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** the line runs from the file to `Open U-M GPT`, and touches no other step; no
  step on this plane writes a file. A dotted line is data, not the run moving to the file. The
  step's own second line names the file's path, so this is easier than it looks.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** three arrows come in, among them the one from `Open U-M GPT` and the `no` from
  `checklist done?`, and one goes out to `Do the next step on the checklist`. The `yes` path from
  `stuck?` goes to `Provide explanations and suggestions`, not here.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-loop
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **tutor note:** the merge the `try suggestion` arrow reaches sits just after `Open U-M GPT`, but
  the step it leads on to is `Do the next step on the checklist`.

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** on `give up` the next step is `Write a status report on where it stalled`; the
  run does not start over.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** the step is not the end; the circle after it is. `Codex answers with the U-M key`
  is the other outcome, reached from `checklist done?`. Choice 4 reads a loop in where none is
  drawn.
