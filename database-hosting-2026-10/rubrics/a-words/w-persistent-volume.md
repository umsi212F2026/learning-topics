# Rubric: persistent volume

What it names: file storage space attached to a server that outlasts the server being replaced.
Nearest confusable: database host; backup. Synonyms: volume, persistent disk.

### q-volume-vs-database-host

- **goal:** `w-persistent-volume`
- **move:** DISTINGUISH
- **answer:** a persistent volume is file storage attached to your backend's own server; the
  backend still opens the SQLite file itself, and the volume is just a place for that file that
  survives the server being replaced. A database host runs the database for you as a service of its
  own, and your backend connects to it; there is no database file on your server at all. Both keep
  the data through a redeploy, so that is not the difference.
- **credit:** full for the difference that matters: a volume is storage on your own server where
  your backend keeps its database file, while a database host runs the database separately and the
  backend connects to it. Half for one side right with the other missing or vague. Do not accept
  "only one of them survives a redeploy", which the question rules out, and do not accept a
  difference of price or of which company provides it.

### q-volume-vs-backup

- **goal:** `w-persistent-volume`
- **move:** DISTINGUISH
- **answer:** a persistent volume is where the live database file sits: the backend reads and
  writes it there as the app runs, and the volume keeps it through the server being replaced. So it
  holds the current state, whatever that is, a mistaken deletion included. A backup is a separate
  copy of the data as it was at some earlier moment, kept apart from the live file, so that an
  earlier state can be brought back after something is lost or broken. Some hosts can also take
  snapshots of a volume; a snapshot is a backup of the volume, a separate copy, not the volume
  itself.
- **credit:** full for the difference that matters: the volume is the place the one live copy is
  kept and changed, through server replacement, while a backup is a separate, earlier copy to
  restore from. Half for one side right with the other missing or vague (say, "a backup is a
  copy" with nothing about what the volume holds). Do not accept "a backup survives a redeploy and
  a volume doesn't", which is false, or a difference of price. Do not require the learner to say a
  volume can never have a copy anywhere: on hosts that snapshot volumes there may be one, and that
  copy is a backup.
- **tutor note:** if the learner says the host keeps copies of the volume, ask whether the volume
  itself or a separate snapshot of it is what holds the earlier copy.

### q-catch-volume-size

- **goal:** `w-persistent-volume`
- **move:** CATCH
- **answer:** a persistent volume is not about room. What makes it a persistent volume is that it
  outlasts the server being replaced, as on a redeploy, so files on it are still there afterwards.
  A few dozen sign-ups need that as much as a million do. Whether the app needs one turns on what
  the host does to the server's own disk when it replaces the server, not on how much data there
  is.
- **credit:** full for naming the actual error: a volume is storage that outlasts the server being
  replaced, and that, not space, is what it is for, so the size of the data does not decide whether
  one is needed. Half for "small apps need a volume too" or "it isn't about size" with nothing
  about what a volume keeps through. Do not accept a different quibble: "they will get more
  sign-ups later", "use Postgres instead", or a remark about where on the volume the file must go,
  none of which is what the sentence gets wrong.
