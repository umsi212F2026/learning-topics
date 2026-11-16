Tom built a workflow on his laptop for his swim team: an agent, following his skill file, reads a swimmer's own recent times and the next meet's event list and picks which events they should enter.

The team has about sixty swimmers, and each would run it before each of the season's eight meets. When Tom tried a small open-weight model of the kind that runs in a web browser on last season's times, about one entry list in three broke the meet's rules, where the model he uses now got nearly all right.

Each swimmer's times are kept in the team's private results sheet. The team would run the service.

Plan A: The team runs the workflow as a web service, BYOK: each swimmer gives it their own API key, and the agent step's model calls are billed to that key.

Plan B: The team runs the workflow as a web page, with the agent step done by an open-weight model that runs in each swimmer's web browser, on their own device.

### first

On correctness of the entry lists, which plan does better?

1. Plan A
2. Plan B
3. They do about as well on correctness

### second

Now suppose one thing is different: each swimmer's times are posted on the league's public results page. Everything else is as before.

On correctness of the entry lists, which plan does better?

1. Plan A
2. Plan B
3. They do about as well on correctness
