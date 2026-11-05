I run the partner matching for our city's language exchange, which pairs people who want to
practice each other's languages. People join through the exchange's sign-up page, which passes each
sign-up on once and keeps nothing. When the city newsletter goes out on the first of the month,
about five hundred people sign up in the first fifteen minutes. The program on the agent's computer
saves each sign-up into the exchange's folder as it arrives, at any hour. The AI agent reads each
sign-up, finds a partner for it among earlier sign-ups, emails both people, and then writes a line
in a log naming the sign-up it matched. The agent's provider takes only twenty requests a minute. A
match within a day or two of signing up is soon enough. Most of our pairs meet at the cafe across
from the central library.

### q1

Where, if anywhere, should this workflow's work wait, and why?

1. In the sign-up page, asking it for new sign-ups each run, because sign-ups sent while the agent's computer is off, each with someone waiting, would never be handled.
2. In the folder, finding sign-ups not yet in the log, because sign-ups sent while the agent's computer is off, each with someone waiting, would never be handled.
3. In the folder, finding sign-ups not yet in the log, because a burst would arrive faster than the twenty a minute the provider takes.
4. In the sign-up page, asking it for new sign-ups each run, because a burst would arrive faster than the twenty a minute the provider takes.
