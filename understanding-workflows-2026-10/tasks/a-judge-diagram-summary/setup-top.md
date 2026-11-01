This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Read this top level only, without opening the diagram under any box that has one.

## Framing

An AI agent was asked to say in plain words what this plane of the diagram claims. Each question
below gives sentences from its summary about one element of the plane.

### start-circle

The agent's summary says several things about the circle `opens the Day 1 page in Canvas`. Which
one does the diagram support?

1. It is the first step: the human opens the Day 1 page.
2. It marks the outcome of `Get Codex running`.
3. It marks what starts a run of the workflow, its trigger.
4. It marks a gateway, where the flow splits or merges.

### plain-step

The agent's summary says several things about the rounded box `Submit each session's report`.
Which one does the diagram support?

1. It marks the outcome a run of the workflow ends in.
2. It marks one step, work the workflow does.
3. It is a subprocess, with the reports drawn underneath it.
4. It marks where a run of the workflow starts.

### gateway

The agent's summary says several things about the diamond just before the rounded box `Report
being stuck`. Which one does the diagram support?

1. It is a step where the human checks how setup went.
2. It is an end circle, for a run that cannot go on.
3. It marks a file that the workflow uses.
4. It marks a gateway in the flow of the run.

### subprocess

The agent's summary says several things about the rounded box `Set up the workspace`. Which one
does the diagram support?

1. It is a step with a diagram of its own underneath it.
2. It is a single step, one the AI agent does.
3. The diagram underneath it is the one for `Get Codex running`.
4. It marks where a run of the workflow begins.

### file

The agent's summary says several things about the shape `U-M API key`. Which one does the diagram
support?

1. It marks a file, data that a step uses.
2. It is a step: the human gets the U-M API key.
3. It marks an outcome: the run ends with the key.
4. It marks a gateway, where the flow splits or merges.

### lane-span

The agent's summary says these things about the rounded box `Get Codex running`. Is each sentence
true or false of what the diagram shows?

#### a

"The human takes part in it."

1. True
2. False

#### b

"A program takes part in it."

1. True
2. False

#### c

"The AI agent takes part in it."

1. True
2. False

### one-split

The agent's summary says several things about the diamond just after the rounded box `Set up the
workspace`. Which one does the diagram support?

1. Paths come back together here, and one path goes on.
2. The run takes both paths from here at the same time.
3. The flow splits here, on `install correct?`.
4. The flow splits here, on `Able to complete?`.

### one-merge

The agent's summary says several things about the diamond just before the rounded box `Set up the
workspace`. Which one does the diagram support?

1. It is a decision: the run goes one way or the other here.
2. The paths from `Codex running?` and `install correct?` come back together here.
3. Only one path arrives here, and one path goes on.
4. The `stuck` path meets the others here.

### after-loop

The agent's summary says these things about the rounded box `Check the install`. Is each sentence
true or false of what the diagram shows?

#### a

"After `Check the install`, on `success`, the next step is `Report being stuck`."

1. True
2. False

#### b

"After `Check the install`, on `not yet`, the next step is `Set up the workspace`."

1. True
2. False

### after-last

The agent's summary says several things about the rounded box `Report being stuck`. Which one does
the diagram support?

1. The run ends at `Report being stuck` itself, with nothing after it.
2. After it, the run ends in the circle `workspace ready`.
3. After it, the run ends in the circle `blocked`.
4. After it, the next step is `Get Codex running`.
