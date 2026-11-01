This is the course's setup workflow, as drawn for Installations 1 to 3. Open
`workflows/bootstrap/bootstrap.bpmn` in your `course-materials` folder. It opens in Camunda
Modeler. Click the small arrow button at the bottom-right corner of the `Set up the workspace`
box to open the diagram underneath it. Each question below is about this plane of the diagram
alone.

### next-arrow

What does the solid arrow from `Write the receipt` to `Check the receipt landed` tell you?

1. both steps run at the same time
2. `Write the receipt` reads a file
3. `Check the receipt landed` runs next
4. the run ends here

### not-handoff

When a run goes from `Write the receipt` to `Check the receipt landed`, is that a handoff?

1. yes
2. no

### handoff

Name one handoff in this plane: a place where the run goes from a step done by one actor to the
next step, done by a different actor (gateways between them don't matter). Name the two steps.

### lane-step

Who does `Record where things live`?

1. a program
2. the AI agent
3. the human
4. more than one of them

### split-after-editors

At the diamond just after `Check the editors`, does the flow split, or do paths come back
together?

1. it splits
2. paths come back together

### merge-after-submit-2

At the diamond just after `Submit Installation 2`, does the flow split, or do paths come back
together?

1. it splits
2. paths come back together

### split-after-receipt

At the diamond just after `Check the receipt landed`, does the flow split, or do paths come back
together?

1. it splits
2. paths come back together

### after-step

What happens after `Submit Installation 1`?

### after-last

What happens after `Submit Installation 3`?

1. `set up, checked and submitted`
2. `stopped at a checkpoint`
3. `Publish the repositories`
4. `Check the remote`
