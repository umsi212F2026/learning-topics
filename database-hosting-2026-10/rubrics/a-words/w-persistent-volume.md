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
