I look after the 3D printers at our makerspace. Members send print requests at any hour by
uploading their model to the makerspace's shared folder, and each request is saved there as its own
file. An AI agent on the shop laptop opens each model, checks that it will print, and saves a print
plan file beside each request it has finished, naming the printer, the material and how long the
print will take. The shop laptop is on from about 10 a.m. to 9 p.m. while the space is open and
turned off the rest of the time. The shared folder keeps every model uploaded while the laptop is
off. Requests come a few an hour, well under the twenty a minute the agent's provider takes. Each
member who uploads is waiting on a plan, and a plan by the time the space next opens is soon enough.
Our largest printer is nicknamed Big Bertha.

### q1

Where, if anywhere, should this workflow's work wait, and why?

1. In the shared folder, finding requests with no print plan file yet, because requests sent while the laptop is off, each with a member waiting, would never be handled.
2. In a list the workflow keeps, adding each request as it arrives, because a burst would arrive faster than the twenty a minute the provider takes.
3. In the shared folder, finding requests with no print plan file yet, because a burst would arrive faster than the twenty a minute the provider takes.
4. In a list the workflow keeps, adding each request as it arrives, because requests sent while the laptop is off, each with a member waiting, would never be handled.
