This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Click the small arrow button at the bottom-right corner of the `Set up the workspace`
box to open the diagram underneath it, and read that diagram only.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### next-arrow

The agent's summary says these things about the solid arrow from `Write the receipt` to `Check
the receipt landed`. Is each sentence true or false?

#### a

"After `Write the receipt`, `Check the receipt landed` runs next."

1. True
2. False

#### b

"Both steps run at the same time."

1. True
2. False

#### c

"`Write the receipt` reads a file."

1. True
2. False

### not-handoff

The agent's summary says several things about the run going from `Check the addressing` to
`Write the receipt` (the gateways between them don't matter here). Which one does the diagram
support?

1. It is a handoff: a program does one step, the AI agent the other.
2. It is a handoff, since the run moves on from one step to another.
3. It is not a handoff: a program does both steps.
4. It is a handoff: a program does one step, the human the other.

### handoff

The agent's summary says several things about the run going from `Check the editors` to `Submit
Installation 2` (the gateway between them doesn't matter here). Which one does the diagram
support?

1. It is not a handoff: one actor does both steps.
2. It is a handoff: a program does the first step, the human the second.
3. It is a handoff: the AI agent does the first step, the human the second.
4. It is not a handoff: the human does both steps.

### lane-step

The agent's summary says these things about `Record where things live`. Is each sentence true or
false?

#### a

"A program does it, since its label names `setup-addressing`."

1. True
2. False

#### b

"The AI agent does it."

1. True
2. False

#### c

"The human does it."

1. True
2. False

### split-after-remote

The agent's summary says several things about the diamond just after `Check the remote`. Which
one does the diagram support?

1. Paths come back together here, and one path goes on.
2. It is a step a program does after `Check the remote`.
3. A run goes both ways from here at the same time.
4. The flow splits here: a run goes one way or the other.

### merge-before-receipt

The agent's summary says several things about the diamond just before `Write the receipt`. Which
one does the diagram support?

1. Paths come back together here, and one path goes on.
2. Here the AI agent decides whether to write the receipt.
3. The flow splits here: a run goes one way or the other.
4. It is a step the AI agent does before `Write the receipt`.

### after-step

The agent's summary says several things about `Submit Installation 1`. Which one does the diagram
support?

1. After it, the flow goes back to `Check the receipt landed`.
2. After it, the next step is `Publish the repositories`.
3. After it, the next step is `Install the editors`.
4. After it, the next step is `Check the editors`.

### after-last

The agent's summary says several things about `Submit Installation 3`. Which one does the diagram
support?

1. After it, the run ends at `stopped at a checkpoint`.
2. After it, the run ends at `set up, checked and submitted`.
3. After it, the next step is `Publish the repositories`.
4. After it, the flow goes back to `Check the remote`.
