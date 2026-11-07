Omar hikes most weekends and keeps a conditions record of what other hikers report about the
trails near him. A program saves new posts from a hiking forum into a folder; the conditions
agent, following a skill file Omar wrote, turns each trail report into an entry; Omar checks the
new entries; and a planning program helps him choose a weekend hike.

About this workflow: Every hour from 6 a.m. to 10 p.m., a program saves the new posts from a
hiking forum into a folder, and then the conditions agent reads each new post. For each post that
reports on a trail's conditions, the conditions agent adds an entry to the conditions record with
the trail's name, the date and what the hiker found, such as mud, snow or fallen trees. The
conditions agent never changes an entry already in the record. A run of the conditions agent
takes about ten minutes. Most evenings, often while a run is going, Omar looks over that day's new
entries at the end of the record and fixes any trail name the agent got wrong. Every Friday
evening the planning program picks out only the past two weeks' entries for the trails on Omar's
weekend shortlist and makes him a summary of each trail. The planning program changes nothing in
the record and adds nothing to it. The record now holds about thirty thousand entries, from six
years of posts.

### conditions-agent

What kind of access to the conditions record does the conditions agent need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### omar

What kind of access to the conditions record does Omar need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### planning-program

What kind of access to the conditions record does the planning program need?

1. Read it through
2. Query it
3. Edit it
4. Append-only writes

### race

Which pair of executors, if any, is in danger of a race condition on the conditions record?

1. None
2. Omar and the planning program
3. Omar and the conditions agent's runs
4. One run of the conditions agent and the next
