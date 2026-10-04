# ephemeral disk

Answer in two or three sentences, with nothing open in front of you.

### q-catch-ephemeral-crash

Your agent writes: "This host's servers have an ephemeral disk, but that only matters if the server
crashes. As long as the app keeps running, your SQLite file is safe there, even across redeploys."
What is wrong with what the agent said?

### q-ephemeral-vs-volume

A host offers two places your backend can write files: the server's ephemeral disk, and a
persistent volume attached to the server. Both are disk space, and the backend writes to either one
the same way. What is the difference between them?

### q-interpret-ephemeral-filesystem

A host's documentation says: "Each server has an ephemeral filesystem. Use it for scratch files and
caches, never for anything you need to keep." What is this claiming about files your backend writes
there, and what does it rule out?
