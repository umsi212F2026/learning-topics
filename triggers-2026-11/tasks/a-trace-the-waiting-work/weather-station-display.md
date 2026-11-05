I run the weather display in our school's front lobby. A weather station on the gym roof sends a
new reading of temperature, wind and rain every five minutes, day and night. A program on the
science room computer takes each reading and shows it on the lobby screen, where each new reading
replaces the last one. The science room computer is turned off over weekends and school vacations.
Readings come one every five minutes, well under the hundred a minute the program can handle. The
screen should show each reading as it comes in, so people walking in can see what it is like
outside right now. The weather station was a gift from last year's graduating class.

### q1

Where, if anywhere, should this workflow's work wait, and why?

1. In a list the workflow keeps as each reading arrives, because readings sent while the science room computer is off, each with someone waiting, would never be handled.
2. Nowhere, each reading going straight to the program as it arrives, because nothing needs to wait, as the program is always available and never overloaded.
3. Nowhere, each reading going straight to the program as it arrives, because nothing needs to wait, as losing some readings does no harm here.
4. In a list the workflow keeps as each reading arrives, because a burst would arrive faster than the hundred a minute the program handles.
