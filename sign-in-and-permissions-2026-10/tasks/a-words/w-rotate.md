# Rotate

Answer in two or three sentences, in your own words, with nothing open in front of you.

Pantry is a recipe box with sign-in through GitHub. Its Express backend runs on Rivetbox, a server
host, and reads Pantry's GitHub client secret from Rivetbox's settings. A student has found that
the client secret also went out in a commit pushed to Pantry's public repository.

### q2

The student says:

"I rotated the secret: I made a new client secret at GitHub and put it in Rivetbox's settings. The
old one is still listed at GitHub, but nothing of ours uses it any more, so that's fine."

What is wrong with that?

### q3

A second student, with the same leak, says:

"I rotated the secret: I made a new one at GitHub and deleted the old one there. Rivetbox still has
the old value in its settings, but that doesn't matter, because rotating happens at GitHub."

What is wrong with that?

### q1

What is the difference between rotating the client secret and deleting it from the repository?
