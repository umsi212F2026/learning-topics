# Race condition

### vs-merge-conflict

Two things went wrong for a community garden that keeps its list of plot holders in a file.

On Monday, Dana opened the plot list on the shared drive and spent an hour fixing phone numbers.
While she worked, a script opened the same file, added the weekend's new sign-ups, and saved the
whole file back. Dana saved after the script did. The weekend's sign-ups were gone, and nobody saw
any warning.

On Tuesday, Luis and Mei each changed the holder of the same plot in the file, on two different
Git branches. When Mei merged the branches, Git stopped, showed both versions of that line, and
asked her which to keep.

#### a

Which term best describes what happened on Monday?

1. A race condition
2. A merge conflict
3. Neither

#### b

Which term best describes what happened on Tuesday?

1. A race condition
2. A merge conflict
3. Neither

### catch-pick

A book club keeps a sheet of each member's pages read this month. Every hour a script opens the
sheet, adds in the entries members sent through a form, and saves the whole sheet back. On busy
days a run takes more than an hour, so the next run starts while the last one is still going.

Which of these uses the term race condition correctly?

1. Because both runs are the same script, a race condition can't happen here.
2. There is a danger of a race condition, since each run saves its whole copy.
3. A race condition here would make the runs stop and ask which totals to keep.
4. The race condition is that a run sometimes takes more than an hour.

### catch-nightly

A chess club keeps its member list in a file. Each night at 2 a.m., a program is supposed to copy
the list into a backup folder, and nothing else runs at that hour. After a volunteer changed the
program's settings, it began copying the other way: each night it copied the old backup over the
current list. On Monday morning, the members added over the weekend are gone. A volunteer says:

"We have a race condition. The backup wiped out the weekend's sign-ups."

What is wrong with that? Answer in two or three sentences, in your own words.
