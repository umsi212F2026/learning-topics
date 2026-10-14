# rate limit

Answer in two or three sentences, in your own words, with nothing open in front of you.

Ringbell is a neighborhood app where neighbors lend each other tools: a ladder, a drill, a
lawnmower. Its page, its server and its database all run on a host called Marrowlight. A visitor
who looks at a page or two of Ringbell makes a handful of requests to its server.

### q-catch-limit-on-everyone

Ringbell's builder asked their agent to protect the server, and the agent added a rate limit of
thirty requests a minute. The builder writes in their notes:

"Ringbell has a rate limit now. If more than thirty neighbors open Ringbell in the same minute,
the thirty-first will be turned away until the minute is over."

What is wrong with that?

### q-catch-refusal-is-permanent

One evening a neighbor, waiting for a drill to show as available, clicks refresh over and over.
Ringbell's rate limit kicks in and she sees "Too Many Requests". She messages the builder, who
replies:

"Sorry, the rate limit has blocked your account. I'll have to go into Marrowlight and unblock you
by hand."

What is wrong with that?

### q-rate-limit-vs-overage

Ringbell's plan on Marrowlight includes a million requests a month, and the plan page lists an
overage for anything past that. Ringbell also has a rate limit of thirty requests a minute. What
is the difference between the overage and the rate limit?
