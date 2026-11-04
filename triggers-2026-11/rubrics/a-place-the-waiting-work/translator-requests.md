Shape `unavailable`, case `worker-unavailable`, natural kind `source`, Medium.

The natural place is the website's own record of requests: each run, the agent asks it for the
requests that came in since its last run. The two facts behind it: where the items are held, "The
website keeps a list of every request, with the time it came in"; and
that nothing the workflow leaves behind says which are done, "The agent emails each match and keeps
no copy of it." So no file or log could tell what is still waiting, and the website's list is the
simplest place that loses nothing.

The defining facts: the laptop's off hours ("on from about 9 a.m. to 5 p.m. on weekdays and turned
off the rest of the time"), that requests arrive during them ("A few requests come in a day, at all
hours"), and that the result can wait until the laptop is next on ("a reply on my next working
morning is soon enough").

Other places:

- A log or a file the workflow would newly start writing for each matched request, with the waiting
  work being every request on the website not yet in it: workable, since the website holds the
  requests, though more than the website's own list needs.
- A list the workflow keeps, adding each request as it arrives: not workable. The laptop is turned
  off evenings, nights and weekends, when many requests arrive, and nothing in the scenario is on
  then to add them. An answer that invents such a machine earns nothing for the place.
- Nowhere: not workable. Every request that comes in while the laptop is off would never be
  matched.

The consequence without a queue, resting on the laptop's hours and "A few requests come in a day,
at all hours": requests sent in the evening, overnight or at the weekend never get a volunteer, and
the people who sent them ("Everyone who writes is waiting on a translation") never hear back.

Irrelevant detail: "Between them, our volunteers speak fourteen languages."

Generic reasons that fail: "work might get lost", "a queue is safer", "it's good to keep a record".

True facts with no bearing on where the work waits, which also fail: the agent picks a volunteer
who knows the language; the people asking need a letter or a form translated.

Examples of each kind of tied reason, for the website's list:

- What makes that place good here: "the website keeps a list of every request, with its time, so
  each morning the agent can ask for the ones since its last run."
- What would go wrong here without it: "requests sent overnight or at the weekend would never get a
  volunteer."
- What would make a specific other place worse: "a list the agent keeps would miss the night's
  requests, since nothing is on overnight to add them"; or "doing nothing would lose every request
  that comes in while the laptop is off."

### q1

- **goal:** `c-when-to-queue`
- **cases:** worker-unavailable
- **answer:** On the website: each time it runs, the agent asks the website for the requests that
  came in since its last run. The website keeps a list of every request, with its time, and the agent keeps no copy of its emails, so nothing else could say which are
  done. Without that, requests sent in the evening, overnight or at the weekend would never be
  matched.
- **credit:** full when the answer names a workable place, said concretely for this workflow (the
  website's list of requests since the last run, or a log or file the workflow would newly start
  writing for each matched request), and gives a reason tied to this workflow of any of the three
  kinds: what makes that place good here, what would go wrong here without it, or what would make a
  specific other place worse. A fact with no bearing on where the work waits, one resting on the
  fourteen languages, or one the facts contradict is not a tied reason. A place named only
  generically ("put them in a queue") is ruled as a list the workflow keeps, which is not workable
  here. Half when the place is workable but the reason is generic, untied or missing, or when the
  reason is tied but the place is unworkable (a list the agent keeps, "because requests come in
  while the laptop is off"). None when the place is unworkable and the reason is generic, untied or
  missing, or when the answer says no place is needed.
- **tutor note:** if the answer proposes a list the agent keeps, ask what adds a request sent at
  2 a.m. to that list. If it relies on the laptop catching up when it wakes, the laptop is turned
  off, not asleep, so that reason rests on a fact the scenario contradicts.
