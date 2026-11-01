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

Compound parts in this scenario: nine, five True and four False.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the diamond meant is `stuck?`: one arrow in, `yes` to `Provide explanations and
  suggestions` and `no` to `checklist done?`. Choice 4 names the question of the next diamond.

### branch-label

- **goal:** `c-read-diagram`
- **cases:** branch-label
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** the labels are swapped: `yes` ends the run, `no` goes back.

#### b

- **type:** mcq
- **answer:** 1
- **tutor note:** the `no` arrow reaches the merge just before `Do the next step on the
  checklist`, so the run goes back to that step.

#### c

- **type:** mcq
- **answer:** 1

### file-line

- **goal:** `c-read-diagram`
- **cases:** data-line
- **type:** compound

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** the line runs from the file to the step, and no step on this plane writes a
  file.

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** `Open U-M GPT` sits in the HUMAN lane, and the dotted line touches only that
  step; U-M GPT being an AI does not put the step in the AI agent's lane.

#### c

- **type:** mcq
- **answer:** 1
- **tutor note:** the step's own second line names the file's path, so this part is easier than
  it looks.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** three arrows come in (from `Open U-M GPT`, `no` from `checklist done?`, `try
  suggestion` from `worth trying?`) and one goes out to `Do the next step on the checklist`. The
  `give up` path goes to `Write a status report on where it stalled`.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-loop
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** the merge the `try suggestion` arrow reaches sits just after `Open U-M GPT`, but
  the step it leads on to is `Do the next step on the checklist`.

#### c

- **type:** mcq
- **answer:** 1

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** the step is not the end; the circle after it is. `Codex answers with the U-M key`
  is the other outcome, reached from `checklist done?`.
