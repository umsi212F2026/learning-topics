This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Click the small arrow button at the bottom-right corner of the `Get Codex running` box
to open the diagram underneath it, and read that diagram only.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### one-split

The agent's summary says several things about the diamond just before the circle `Codex answers
with the U-M key`. Which one does the diagram support?

1. Paths come back together here, and one path goes on.
2. The flow splits here: a run goes one way or the other.
3. It is a step the human does before the run ends.
4. A run goes both ways from here at the same time.

### branch-label

The agent's summary says these things about the label `no` on the arrow leaving the diamond just
after `Do the next step on the checklist`. Is each sentence true or false?

#### a

"A run goes this way when the answer at the diamond is `no`."

1. True
2. False

#### b

"A step called `no` runs next."

1. True
2. False

#### c

"The run ends here, with the outcome `no`."

1. True
2. False

### file-line

The agent's summary says these things about the dotted line between the file
`bootstrap-prompt.md` and `Open U-M GPT`. Is each sentence true or false?

#### a

"After `Open U-M GPT`, the run moves on to the file."

1. True
2. False

#### b

"`Open U-M GPT` reads the file."

1. True
2. False

#### c

"The file is the next step after `Open U-M GPT`."

1. True
2. False

### one-merge

The agent's summary says several things about the diamond just before `Do the next step on the
checklist`. Which one does the diagram support?

1. The flow splits here: a run goes one way or the other.
2. Here the human decides whether to go on with the checklist.
3. It is a step the human does after `Open U-M GPT`.
4. Paths come back together here, and one path goes on.

### after-loop

The agent's summary says these things about `Provide explanations and suggestions`. Is each
sentence true or false?

#### a

"After `Provide explanations and suggestions`, on `try suggestion`, the flow goes back to `Do the
next step on the checklist`."

1. True
2. False

#### b

"After `Provide explanations and suggestions`, on `give up`, the next step is `Write a status
report on where it stalled`."

1. True
2. False

### after-last

The agent's summary says several things about `Write a status report on where it stalled`. Which
one does the diagram support?

1. After it, the run ends at `stuck`.
2. After it, the next step is `Provide explanations and suggestions`.
3. After it, the flow goes back to `Do the next step on the checklist`.
4. After it, the run ends at `Codex answers with the U-M key`.
