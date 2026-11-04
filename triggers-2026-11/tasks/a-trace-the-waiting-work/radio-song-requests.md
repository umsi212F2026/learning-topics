I run the request line at our community radio station. Listeners text song requests to the
station's text line, which shows each request once and keeps nothing. Most of the week requests
trickle in, but when the host opens the Friday request hour, about four hundred arrive in the first
ten minutes. A program on the agent's computer takes in each request, at any hour, as it arrives.
The AI agent checks each request against the station's music library and texts the listener back
with whether we have the song and about when it will play, keeping no copy. The agent's provider
takes only twenty requests a minute. Listeners are happy to hear back within the hour. The station
broadcasts from a room above the old firehouse.

### q1

Where, if anywhere, should this workflow's work wait, and why?

1. In the text line, asking it for new requests each run, because a burst would arrive faster than the twenty a minute the provider takes.
2. In a list the workflow keeps as each request arrives, because requests sent while the agent's computer is off, each with a listener waiting, would never be handled.
3. In the text line, asking it for new requests each run, because requests sent while the agent's computer is off, each with a listener waiting, would never be handled.
4. In a list the workflow keeps as each request arrives, because a burst would arrive faster than the twenty a minute the provider takes.
