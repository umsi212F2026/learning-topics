diagram commit: eb7b655

The plane under `Get Codex running` in `bootstrap.bpmn`. Lanes, top to bottom: HUMAN operator, AI
AGENT. The run starts at `Day 1 page opened` (HUMAN) and goes to `Open U-M GPT; paste the
bootstrap prompt` (HUMAN), which reads the file `bootstrap-prompt.md` (a dotted line from the file
to the step; the step's second line also gives the file's path). Then an unnamed merge, with
three arrows in, and on to `Do the next step on the checklist` (HUMAN). Then the split `stuck?`:
`yes` goes to `Provide explanations and suggestions` (AI AGENT); `no` goes to the split
`checklist done?`, whose `yes` goes to the end circle `Codex answers with the U-M key` and whose
`no` loops back through the merge to `Do the next step on the checklist`. After `Provide
explanations and suggestions`, the split `worth trying?`: `try suggestion` loops back through the
merge to `Do the next step on the checklist`; `give up` goes to `Write a status report on where it
stalled` (AI AGENT), then the end circle `stuck` (its label goes on after a long dash).

Three named splits (`stuck?`, `worth trying?`, `checklist done?`), one unnamed merge (between
`Open U-M GPT; paste the bootstrap prompt` and `Do the next step on the checklist`), two end
circles. No subprocess and no step drawn across two lanes.

### one-split

- **goal:** `c-read-diagram`
- **cases:** splits
- **answer:** any one of the three named gateways: `stuck?` (just after `Do the next step on the
  checklist`, before `Provide explanations and suggestions` and `checklist done?`); `worth
  trying?` (just after `Provide explanations and suggestions`, before `Write a status report on
  where it stalled` and the arrow back to the merge); `checklist done?` (after the `no` branch of
  `stuck?`, before the end circle `Codex answers with the U-M key` and the arrow back to the merge).
- **credit:** full for any one of the three named gateways, pointed at by its neighbors or named
  by its label; none for the unnamed merge or a step. Credit a paraphrased step or gateway name
  when it is clear which element is meant; ask which only when it is not.

### branch-label

- **goal:** `c-read-diagram`
- **cases:** branch-label
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** the `no` arrow leads to another diamond in the same HUMAN lane, so choice 4 is
  wrong on the drawing as well as on what a label means.

### file-line

- **goal:** `c-read-diagram`
- **cases:** data-line
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** the step's own label names the file, so a right answer here is easier than it
  looks. A learner who adds that the line is a handoff is not marked down for it.

### one-merge

- **goal:** `c-read-diagram`
- **cases:** merges
- **answer:** the one unnamed gateway, between `Open U-M GPT; paste the bootstrap prompt` and `Do
  the next step on the checklist`.
- **credit:** full for that gateway; none for a named gateway or a step. Credit a paraphrased step
  name when it is clear which element is meant; ask which only when it is not.
- **tutor note:** a learner who points at it by one of the arrows coming in (from `checklist
  done?` or `worth trying?`) and the step after it has found it.

### after-loop

- **goal:** `c-read-diagram`
- **cases:** trace-loop
- **answer:** if `try suggestion`, back to `Do the next step on the checklist`; if `give up`,
  `Write a status report on where it stalled`.
- **credit:** full when both branches are there with their labels and the right step; half when
  one branch is missing, or one label or one destination is wrong; none when only one next step is
  given with no condition, or more than one part is wrong. Credit a paraphrased step name when it
  is clear which step is meant; ask which only when it is not.
- **tutor note:** the `try suggestion` arrow passes through the merge; naming the merge on the way
  is fine, but the step it reaches is `Do the next step on the checklist`, not `Open U-M GPT;
  paste the bootstrap prompt`.

### after-last

- **goal:** `c-read-diagram`
- **cases:** trace-end
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
