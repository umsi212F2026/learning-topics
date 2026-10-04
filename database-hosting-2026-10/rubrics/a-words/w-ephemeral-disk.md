# Rubric: ephemeral disk

What it names: a server's file storage that starts empty again whenever the host replaces the
server. Nearest confusable: persistent volume. Synonyms: ephemeral filesystem, ephemeral storage.

### q-ephemeral-vs-volume

- **goal:** `w-ephemeral-disk`
- **move:** DISTINGUISH
- **answer:** what happens when the host replaces the server, as it does on a redeploy. The
  ephemeral disk starts empty again, so anything the backend wrote there is gone. The persistent
  volume outlasts the server being replaced, so what was written there is still there afterwards.
- **credit:** full for the difference that matters: whether the files outlast the server being
  replaced (on a redeploy, say), the ephemeral disk not and the volume yes. Half for "one keeps your
  files and one doesn't" with nothing about when the ephemeral one loses them. Do not accept a
  difference of size, speed or price, which may be true of a particular host and is not what
  separates them.

### q-catch-ephemeral-crash

- **goal:** `w-ephemeral-disk`
- **move:** CATCH
- **answer:** an ephemeral disk starts empty again whenever the host replaces the server, and a
  redeploy does exactly that. So the SQLite file is lost on every redeploy, not only after a crash;
  "even across redeploys" is the opposite of what an ephemeral disk does.
- **credit:** full for naming the actual error: a redeploy replaces the server, so the ephemeral
  disk starts empty and the file is gone, whatever the app was doing. Half for "the file isn't safe
  on an ephemeral disk" with nothing about the redeploy being what wipes it. Do not accept a
  different quibble as the error: "SQLite shouldn't be used in production", "use Postgres instead",
  or "crashes are rare", none of which is what the sentence gets wrong.
- **tutor note:** some hosts also wipe the disk on a plain restart. An answer that says so as well is
  fine; one that says only restarts and crashes matter has missed the redeploy.
