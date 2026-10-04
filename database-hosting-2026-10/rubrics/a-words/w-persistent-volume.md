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

### q-interpret-persistent-disk

- **goal:** `w-persistent-volume`
- **move:** INTERPRET
- **answer:** that the SQLite file now sits in file storage attached to the backend's server which
  the host keeps when it replaces the server, as it does on a redeploy, so the file and what users
  have added to it are still there afterwards. It rules out the file being lost when the server is
  replaced, as it would be on the server's own disk. It also rules out the data having moved to a
  separate database service: the backend still opens the SQLite file itself.
- **credit:** full for recovering the claim (the file is now on storage attached to the server that
  outlasts the server being replaced) and at least one thing it rules out (the file being lost when
  the server is replaced, on a redeploy for instance, or the data now being in a separate database
  the backend connects to). Half for the claim with nothing it rules out, or for "the file is stored
  on a disk now" with nothing about its outlasting the server being replaced. Do not accept a reading
  that the data has become a Postgres database, or that the disk lasts only as long as the server
  does.
