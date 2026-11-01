This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler, at the top level of the diagram. Read this top level only, without opening the diagrams
underneath its boxes.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### end-circle

The agent's summary says several things about the circle `workspace ready`. Which one does the
diagram support?

1. It marks what starts a run of the workflow, its trigger.
2. It is a step: the human checks that the workspace is ready.
3. It marks an outcome a run ends in.
4. It is the last step the workflow does, in the human's lane.

### plain-step

The agent's summary says several things about the rounded box `Report being stuck`. Which one does
the diagram support?

1. It marks one step, work the workflow does.
2. It has a diagram of its own underneath it.
3. It marks an outcome a run ends in.
4. It marks what starts a run, its trigger.

### gateway

The agent's summary says several things about the diamond just before `Set up the workspace`.
Which one does the diagram support?

1. It is a step the AI agent does just before `Set up the workspace`.
2. It marks what starts a run of the workflow, its trigger.
3. It marks an outcome a run of the workflow ends in.
4. It is a gateway, where the flow splits or merges.

### subprocess

The agent's summary says several things about `Get Codex running`. Which one does the diagram
support?

1. It is a single step, one action with nothing more to it.
2. It is a step with a diagram of its own underneath it.
3. It marks what starts a run of the workflow, its trigger.
4. It is a gateway, where the flow splits or merges.

### lane-span

The agent's summary says these things about `Set up the workspace`. Is each sentence true or
false?

#### a

"Only the AI agent does it."

1. True
2. False

#### b

"The human takes part in it."

1. True
2. False

#### c

"A program has no part in it."

1. True
2. False

### one-split

The agent's summary says several things about the diamond just after `Set up the workspace`.
Which one does the diagram support?

1. Two paths come back together here, and one leaves it.
2. It is a step the AI agent does after `Set up the workspace`.
3. The flow splits here, one way or the other by its answer.
4. A run goes both ways from here at the same time.

### one-merge

The agent's summary says several things about the diamond just before `Report being stuck`. Which
one does the diagram support?

1. Paths come back together here, and one path goes on.
2. The flow splits here: a run goes one way or the other.
3. Here the human decides whether to report being stuck.
4. It is a step in which the human gives up on setup.

### after-loop

The agent's summary says these things about `Check the install`. Is each sentence
true or false?

#### a

"After `Check the install`, on `success`, the next step is `Submit each session's report`."

1. True
2. False

#### b

"After `Check the install`, on `not yet`, the run ends at `blocked`."

1. True
2. False

### after-last

The agent's summary says several things about `Submit each session's report`. Which
one does the diagram support?

1. After it, the run ends at `blocked`.
2. After it, the next step is `Check the install`.
3. After it, the flow goes back to `Set up the workspace`.
4. After it, the run ends at `workspace ready`.
