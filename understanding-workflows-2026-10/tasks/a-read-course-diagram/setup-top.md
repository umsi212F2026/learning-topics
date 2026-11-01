This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler, at the top level of the diagram. Each question below is about this plane of the diagram
alone.

### start-state

Which of these is the state a run of this workflow starts in?

1. `blocked`
2. `Get Codex running`
3. `opens the Day 1 page in Canvas`
4. the diamond just after `Get Codex running`

### end-state

What does the circle `workspace ready` mark?

1. a state a run starts in
2. a state a run ends in
3. one step, an action someone takes
4. a gateway

### plain-step

What does the rounded box `Report being stuck` mark?

1. a state a run starts or ends in
2. one step, an action someone takes
3. a gateway, where the flow splits or comes back together
4. a step with a diagram of its own underneath it

### subprocess

Which of these steps has a diagram of its own underneath it?

1. `Check the install`
2. `Report being stuck`
3. `Submit each session's report`
4. `Set up the workspace`

### gateway

What kind of shape is the diamond just before `Set up the workspace`?

1. a gateway
2. a state
3. a step
4. a file

### lane-step

Who does `Check the install`?

1. the AI agent
2. the human
3. more than one of them
4. a program

### lane-span

Who does `Get Codex running`?

1. the human only
2. the AI agent only
3. the human and the AI agent both take part
4. the human, the AI agent and a program all take part

### handoff

Name one handoff in this plane: a place where the run goes from a step done by one actor to the
next step, done by a different actor (gateways between them don't matter). Name the two steps.

### one-split

Name one place where the flow splits. Point to it by the steps or gateways just before and after
it.

### one-merge

Name one place where paths come back together. Point to it by the steps or gateways just before
and after it.

### after-loop

What happens after `Check the install`?

### after-last

What happens after `Submit each session's report`?

1. `workspace ready`
2. `Report being stuck`
3. `blocked`
4. `Check the install`
