# Rubric: persistent volume

What it names: file storage space attached to a server that outlasts the server being replaced.
Nearest confusable: database host. Synonyms: volume, persistent disk.

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

### q-catch-volume-backup

- **goal:** `w-persistent-volume`
- **move:** CATCH
- **answer:** a persistent volume is storage that outlasts the server being replaced; it is not a
  copy or a backup. The database is on the volume once, and deleting a recipe deletes it there.
  What the volume protects against is a redeploy wiping the file, not a mistake made through the
  app.
- **credit:** full for naming the actual error: a volume keeps the one file through server
  replacement and holds no earlier copy, so a deletion is just as permanent. Half for "a volume
  isn't a backup" with nothing about what it does keep the file through. Do not accept a different
  quibble: "they should use Postgres", or "volumes cost money".

### q-define-volume

- **goal:** `w-persistent-volume`
- **move:** DEFINE
- **answer:** storage space for files, attached to a server, that the host keeps when it replaces
  the server, as it does on a redeploy. Files written there are still there afterwards, unlike files
  on the server's own disk.
- **credit:** full for file storage attached to a server that outlasts the server being replaced.
  Half for "extra storage for the server" with nothing about its outlasting the server being
  replaced, or for "storage where files are kept" with nothing about what it is attached to or what
  it outlasts. Do not accept "a volume" or "a persistent disk" alone, which name it again, or "a
  backup" or "a database", which it is not.
