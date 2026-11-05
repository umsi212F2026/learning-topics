I coordinate donation pickups for our neighborhood thrift store. People ask for a pickup through
the store's website at all hours, saying what they want to give and where they live. An AI agent
on my laptop reads each request, picks a pickup day that fits the truck's route, and emails the
donor that day, keeping no copy of the email. My laptop is on from about 9 a.m. to 5 p.m. on
weekdays and turned off the rest of the time. The website keeps every pickup request that comes in
while my laptop is off, with the time it came in, and can list them in that order. Requests come a
few an hour, well under the twenty a minute the agent's provider takes. Each donor is waiting to
hear their day, and a reply on my next working morning is soon enough. Our truck is a white box van
with the store's name painted on the side.

### q1

Where, if anywhere, should this workflow's work wait, and why?

1. In the website's list, asking it for requests since the last run, because a burst would arrive faster than the twenty a minute the provider takes.
2. In the website's list, asking it for requests since the last run, because requests sent while the laptop is off, each with a donor waiting, would never be handled.
3. In a list the workflow keeps, adding each request as it arrives, because requests sent while the laptop is off, each with a donor waiting, would never be handled.
4. In a list the workflow keeps, adding each request as it arrives, because a burst would arrive faster than the twenty a minute the provider takes.
