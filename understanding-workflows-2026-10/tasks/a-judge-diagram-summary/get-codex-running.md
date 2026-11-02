This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Click the small arrow button at the bottom-right corner of the `Get Codex running` box
to open the diagram underneath it, and read that diagram only.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### one-split

An AI agent's summary of this plane says several things about the diamond just after the rounded box
`Do the next step on the checklist`. Which one does the diagram support?

1. Paths come back together here, and one path goes on.
2. The flow splits here, on `stuck?`.
3. The run takes both paths from here at the same time.
4. The flow splits here, on `checklist done?`.

### branch-label

An AI agent's summary of this plane says several things about the diamond reached on `no` from the
diamond just after the rounded box `Do the next step on the checklist`. Which one does the diagram
support?

1. On its `yes` arrow, the run goes back to `Do the next step on the checklist`.
2. On its `no` arrow, the run goes straight to `Provide explanations and suggestions`.
3. On its `no` arrow, the run goes back to `Do the next step on the checklist`.
4. On its `no` arrow, the run ends in the circle `Codex answers with the U-M key`.

### file-line

An AI agent's summary of this plane says several things about the dotted line between the file
`bootstrap-prompt.md` and the rounded box `Open U-M GPT`. Which one does the diagram support?

1. `Open U-M GPT` reads the file.
2. `Open U-M GPT` writes the file.
3. `Do the next step on the checklist` reads the file.
4. After `Open U-M GPT`, the run moves on to the file.

### one-merge

An AI agent's summary of this plane says several things about the diamond just before the rounded
box `Do the next step on the checklist`. Which one does the diagram support?

1. It is a decision: the run goes one way or the other here.
2. Only one path arrives here, the one from `Open U-M GPT`.
3. The `yes` path from `stuck?` meets the others here.
4. The paths from `Open U-M GPT` and `checklist done?` come back together here.

### after-loop

An AI agent's summary of this plane says these things about the rounded box `Provide explanations
and suggestions`. Is each sentence true or false of what the diagram shows?

#### a

"After `Provide explanations and suggestions`, on `try suggestion`, the next step is `Do the next
step on the checklist`."

1. True
2. False

#### b

"After `Provide explanations and suggestions`, on `give up`, the next step is `Open U-M GPT`."

1. True
2. False

### after-last

An AI agent's summary of this plane says several things about the rounded box `Write a status report
on where it stalled`. Which one does the diagram support?

1. After it, the run ends in the circle `stuck`.
2. The run ends at `Write a status report` itself, with nothing after it.
3. After it, the run ends in the circle `Codex answers with the U-M key`.
4. After it, the next step is `Do the next step on the checklist`.
