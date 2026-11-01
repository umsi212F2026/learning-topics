# Control flow

### vs-step

A veterinary clinic has drawn its workflow for a walk-in visit. A vet tech does "Weigh the pet",
which has a solid arrow to "Take the history". From there a solid arrow leads to the vet's
"Examine the pet", and another to "Prescribe treatment".

In this diagram, what is the difference between control flow and a workflow step? Answer in two
or three sentences, in your own words.

### catch-carries

A small law firm has drawn its workflow for a new contract. A paralegal does "Draft the contract",
which has a dotted line to a "Contract draft" file and a solid arrow to the lawyer's "Review the
contract". "Review the contract" has a dotted line from the "Contract draft" file. A new hire,
describing the diagram, says:

"The control flow is the solid arrow from 'Draft the contract' to 'Review the contract': that is
the arrow that carries the draft over to the lawyer."

What is wrong with that? Answer in two or three sentences, in your own words.

### catch-pick

A bike repair shop has drawn its workflow for a repair. Every step is in one lane, Mechanic.
"Inspect the bike" has a dotted line to a "Repair notes" file and a solid arrow to a diamond,
"Parts in stock?". On "yes", a solid arrow leads to "Fit the parts"; on "no", one leads to "Order
the parts", which has a solid arrow on to "Fit the parts". "Fit the parts" has a dotted line from
the "Repair notes" file.

Which of these statements uses the term "control flow" correctly?

1. "Fit the parts" is control flow, since it is what the run moves on to after the diamond.
2. On "no", the control flow out of the diamond says "Order the parts" runs next.
3. The dotted line from "Repair notes" to "Fit the parts" is control flow, sending the run there.
4. This diagram has no control flow, since the mechanic does every step and nothing changes hands.
