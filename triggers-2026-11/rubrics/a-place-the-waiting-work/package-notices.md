Shape `burst`, case `spread-out`, natural kind `kept`, Medium.

The natural place is a list the office program keeps: as each notice arrives, the program adds it to
its own list, and it hands notices from that list to the agent no faster than about five a minute.
The two facts behind it: where the items are held, nowhere but in the program as each arrives
("the scanner sends out a notice naming the resident, once, and keeps no copy"; "A small program on
the building's office computer receives each notice as the scanner sends it"); and what says which
are done, nothing ("The agent sends each text and keeps no copy of it"). So neither the scanner,
nor files, nor a log could hold the notices, and the program receiving each one is the only thing
that can.

The defining facts: the burst ("the afternoon truck scans in about 150 packages in ten minutes")
and the worker's limit ("the agent's provider takes only about five requests a minute"). At five a
minute the 150 texts take about half an hour, inside "a text within an hour or so of the drop-off
is fine."

Other places:

- The scanner's own record of notices: not workable. The scanner sends each notice once and keeps
  no copy.
- A list worked out from files or a log: not workable as the place the notices wait. Nothing saves
  a notice anywhere, so a log of texts sent would have nothing to be read against. An answer that
  has the program save each notice as a file, and the agent mark each one done, is a list the
  program keeps in another form, and is workable.
- Nowhere: not workable. The program would hand all 150 notices to the agent within ten minutes,
  far past five a minute, and the notices the provider refuses would be gone, since nothing keeps
  a copy.

The consequence without a queue, resting on the burst and the provider's limit: most of the
afternoon's notices would hit the provider at once and be refused, and those residents ("A resident
who never gets a text may not know a package is there") would never hear.

Irrelevant detail: "The mailroom is just inside the lobby door."

Generic reasons that fail: "work might get lost", "a queue is safer", "it's good to keep a record".

True facts with no bearing on where the work waits, which also fail: the text says which shelf the
package is on; the notice names the resident.

Examples of each kind of tied reason, for a list the program keeps:

- What makes that place good here: "the program already receives every notice as it is scanned,
  so it can add each to its own list and pass them on at five a minute."
- What would go wrong here without it: "150 notices in ten minutes would overrun a provider that
  takes five a minute, and the refused ones would be lost."
- What would make a specific other place worse: "the scanner keeps no copy, so it can't hold the
  notices until the agent is ready"; or "doing nothing would send 150 requests at once to a
  provider that takes five a minute."

### q1

- **goal:** `c-when-to-queue`
- **cases:** spread-out
- **answer:** In a list the office program keeps: it adds each notice to its own list as the
  scanner sends it and passes them to the agent at about five a minute. The scanner and the agent
  keep no copies, so only the program that receives each notice can hold it. Without that, the 150
  notices that arrive in ten minutes would overrun a provider that takes five a minute, and the
  refused ones would be lost.
- **credit:** full when the answer names a workable place, said concretely for this workflow (a
  list the office program keeps as each notice arrives, in whatever form, such as a file it saves
  per notice), and gives a reason tied to this workflow of any of the three kinds: what makes that
  place good here, what would go wrong here without it, or what would make a specific other place
  worse. A fact with no bearing on where the work waits, one resting on where the mailroom is, or
  one the facts contradict is not a tied reason. A place named only generically ("put them in a
  queue") is ruled as a list the workflow keeps, which is workable here. Half when the place is
  workable but the reason is generic, untied or missing, or when the reason is tied but the place
  is unworkable (the scanner's record, "because 150 come in ten minutes"). None when the place is
  unworkable and the reason is generic, untied or missing, or when the answer says no place is
  needed.
- **tutor note:** if the answer names the scanner, ask what the scanner keeps once a notice is
  sent. If it says no place is needed, ask what happens to the hundredth notice of the afternoon.
