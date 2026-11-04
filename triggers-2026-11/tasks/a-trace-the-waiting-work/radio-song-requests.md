I run the request line at our community radio station. Listeners text song requests to the
station's text line, which shows each request once and keeps nothing. Most of the week requests
trickle in, but when the host opens the Friday request hour, about four hundred arrive in the first
ten minutes. A program on the agent's computer takes in each request, at any hour, as it arrives.
The AI agent checks each request against the station's music library and texts the listener back
with whether we have the song and about when it will play, keeping no copy. The agent's provider
takes only twenty requests a minute. Listeners are happy to hear back within the hour. The station
broadcasts from a room above the old firehouse.

### q1

Which design, with its reason, fits this workflow?

1. The work should wait in the text line, asking it for the requests that came in since the last run, because otherwise a burst of requests would reach the agent faster than the twenty a minute its provider takes.
2. The work should wait in a list the workflow keeps, adding each request as it arrives, because otherwise requests arriving while the agent's computer is turned off, each with someone waiting on it, would never be handled.
3. The work should wait in the text line, asking it for the requests that came in since the last run, because otherwise requests arriving while the agent's computer is turned off, each with someone waiting on it, would never be handled.
4. The work should wait in a list the workflow keeps, adding each request as it arrives, because otherwise a burst of requests would reach the agent faster than the twenty a minute its provider takes.
