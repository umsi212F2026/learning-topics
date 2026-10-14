# Rubric: backup

If the learner misses a question here, set a DEFINE or INTERPRET move for backup live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A backup is a copy of the app's data, kept apart from it, that can be put back after the data is
lost. The confusables are a rollback, which puts an earlier deploy (code) back on the host and
leaves the data as it is; and git history, which holds every committed version of the code in the
repository but none of the data in the database, since that was never committed. "Snapshot" and
"database backup" are other names for a backup and are not confusables; "restore" is what putting
one back is called. Plotkeep and Brindlecloud are made up, and
appear nowhere else in this topic. The `plots_copy` table in the first question is only a name;
nothing turns on reading any database code.

### q-catch-copy-in-same-database

- **goal:** `w-backup`
- **move:** CATCH
- **answer:** The copy is kept in the same database as the sign-ups, not apart from it. If
  Brindlecloud loses the database, `plots_copy` is lost along with it, so there is nothing left to
  put back. A backup has to be kept somewhere the loss can't reach.
- **credit:** full for naming that the copy lives inside the very database it is meant to
  protect, so losing the database loses the copy too; "it's on the same host, where the same loss
  reaches it" makes the same point and also earns full. Half for "that isn't a real backup" or "it
  should be stored somewhere else" without saying why it matters here. None for a different
  quibble alone, such as that it has never been tried, that nightly is not often enough, or that
  it wastes space.
- **tutor note:** a learner who says the copy would help if a few sign-ups were deleted by
  mistake is right about that; ask what happens to `plots_copy` if the whole database is lost.

### q-backup-vs-rollback

- **goal:** `w-backup`
- **move:** DISTINGUISH
- **answer:** A rollback puts the earlier deploy's code back on Brindlecloud and leaves the data
  alone, so the map works again and today's dozen sign-ups stay. Restoring the backup replaces
  the data with last night's copy and leaves the code alone, so the map stays blank and today's
  sign-ups are lost.
- **credit:** full for naming what each one puts back: a rollback restores code and leaves the
  data, a backup restores data and leaves the code. Half for only one half, such as "a rollback
  goes back to the old code" with nothing on what the backup puts back. None for an incidental
  difference alone, such as which is quicker or which button the host shows.
- **tutor note:** the question asks for the difference, not which to choose; a learner who says
  only "roll back" is right about the choice and has not yet said what separates them, so ask
  what restoring the backup would do to the map and to today's sign-ups.

### q-backup-vs-git-history

- **goal:** `w-backup`
- **move:** DISTINGUISH
- **answer:** Git history holds every committed version of Plotkeep's code, so it can bring back
  earlier code. The sign-ups were never committed; they live only in the database on Brindlecloud,
  so git history has none of them. A backup is a copy of that data, kept apart from it, that can
  be put back if the data is lost.
- **credit:** full for naming that git history holds the code that was committed and not the
  app's data in the database, while a backup holds the data. Half for only one half, such as "git
  history is for code" with nothing on what a backup holds. None for an incidental difference
  alone, such as that GitHub is online, or that a backup is made on a schedule.
- **tutor note:** a learner who says you could commit a copy of the data to the repository has a
  point; ask whether Plotkeep's sign-ups are in the repository now.
