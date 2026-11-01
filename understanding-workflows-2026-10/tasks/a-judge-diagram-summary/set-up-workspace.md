This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Click the small arrow button at the bottom-right corner of the `Set up the workspace`
box to open the diagram underneath it, and read that diagram only.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### next-arrow

The agent's summary says these things about the solid arrow from the rounded box `Publish the
repositories` to the rounded box `Check the remote`. Is each sentence true or false of what the
diagram shows?

#### a

"After `Publish the repositories`, the run goes on to `Submit Installation 3`."

1. True
2. False

#### b

"After `Publish the repositories`, `Check the remote` runs next."

1. True
2. False

#### c

"`Check the remote` runs only if publishing the repositories succeeded."

1. True
2. False

### not-handoff

The agent's summary says several things about the run going from the rounded box `Check the
addressing` to the rounded box `Write the receipt`. Which one does the diagram support?

1. It is a handoff from a program to the AI agent, which writes the receipt.
2. It is not a handoff, since the AI agent does both steps.
3. It is a handoff, because a gateway sits between them.
4. It is not a handoff, since a program does both steps.

### handoff

The agent's summary says several things about the run going from the rounded box `Submit
Installation 1` to the rounded box `Install the editors`. Which one does the diagram support?

1. It is a handoff from the human to the AI agent.
2. It is not a handoff, because a gateway sits between them.
3. It is not a handoff, since the human does both steps.
4. It is a handoff from the human to a program.

### lane-step

The agent's summary says these things about the rounded box `Install tools`. Is each sentence true
or false of what the diagram shows?

#### a

"The AI agent does it."

1. True
2. False

#### b

"A program does it, since its label names `setup-repos`."

1. True
2. False

#### c

"The human does it, since the human installs the tools."

1. True
2. False

### split-after-remote

The agent's summary says several things about the diamond just after the rounded box `Check the
remote`. Which one does the diagram support?

1. Paths come back together here, and one path goes on.
2. The flow splits here, on whether the editors are installed.
3. The flow splits here: a run takes one path or the other.
4. The run takes both paths from here at the same time.

### merge-before-stop

The agent's summary says several things about the diamond just before the circle `stopped at a
checkpoint`. Which one does the diagram support?

1. Paths come back together here, and one path goes on.
2. It is a decision: the run goes one way or the other here.
3. Only one path arrives here, from the diamond after `Check the remote`.
4. The `first time` path meets the others here.

### after-branches

The agent's summary says these things about the rounded box `Check the receipt landed`. Is each
sentence true or false of what the diagram shows?

#### a

"After `Check the receipt landed`, on `yes`, the run goes straight to `Install the editors`."

1. True
2. False

#### b

"After `Check the receipt landed`, on `yes`, comes `Submit Installation 1`."

1. True
2. False

#### c

"After `Check the receipt landed`, on `no`, the run ends in the circle `stopped at a checkpoint`."

1. True
2. False

### after-step

The agent's summary says several things about the rounded box `Submit Installation 2`. Which one
does the diagram support?

1. After it, the next step is `Check the remote`.
2. After it, the next step is `Publish the repositories`.
3. After it, the next step is `Install the editors`.
4. After it, the next step is `Submit Installation 3`.

### after-last

The agent's summary says several things about the rounded box `Submit Installation 3`. Which one
does the diagram support?

1. The run ends at `Submit Installation 3` itself, with nothing after it.
2. After it, the run ends in the circle `stopped at a checkpoint`.
3. After it, the run ends in the circle `set up, checked and submitted`.
4. After it, the flow goes back to `Publish the repositories`.
