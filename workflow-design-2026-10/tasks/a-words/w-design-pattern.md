# Design pattern

### catch-must-save

The owner of a small catering company is planning a workflow for its event orders: an AI agent
reads each customer's typed request and drafts a menu and a price, the owner reviews the draft, and
a program sends the customer the approved quote. Her assistant has been reading about workflow
design and says:

"Checkpoints is a design pattern, so we have to save every step's output in this workflow. Leaving
one out would be bad design."

What is wrong with that? Answer in two or three sentences, in your own words.

### catch-pick

A neighborhood tool library lends drills, ladders and saws to about 80 members. Each week an AI
agent reads the members' typed requests and writes down a loan schedule. The coordinator reads the
schedule and approves it, changing it where she needs to. Then a program updates the inventory
record from the approved schedule, sends each member a reminder, and flags any tool more than a
week overdue.

Which of these statements uses the term "design pattern" correctly?

1. Since maker-checker is a design pattern, the library must add a check after every step, even the program's.
2. Having a program, rather than the agent, send each member's reminder is a design pattern.
3. The agent writing down the schedule and a program applying it once approved is a design pattern.
4. Failing loudly, so that someone hears about overdue tools, is a design pattern the library uses.
