# backup

Answer in two or three sentences, in your own words.

Plotkeep is a community garden's app where members sign up for a garden plot. Its server and its
database both run on a host called Brindlecloud, and its code is in a repository on GitHub. The
plot sign-ups are kept only in the database.

### q-catch-copy-in-same-database

Plotkeep's builder asked their agent to protect the sign-ups. Now, every night, the agent copies
every sign-up into a second table, called `plots_copy`, in the same database on Brindlecloud. The
builder writes in their notes:

"Plotkeep has a backup now. If Brindlecloud ever loses our database, we can put all the sign-ups
back from `plots_copy`."

What is wrong with that?

### q-backup-vs-rollback

At noon a deploy made Plotkeep's map of plots show up blank. The sign-ups in the database are all
still there, and members have added a dozen more since last night. The agent offers two ways out:
roll back to the last working deploy on Brindlecloud, or restore last night's database backup.
What is the difference between the two?

### q-backup-vs-git-history

Plotkeep's repository on GitHub holds every commit since the first one. What is the difference
between that git history and a backup of Plotkeep's database?
