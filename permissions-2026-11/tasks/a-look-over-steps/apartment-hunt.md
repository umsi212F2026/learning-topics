Priya is looking for an apartment near her new job, and a workflow on her laptop helps her keep
up with new listings. Every morning the fetcher, a program, downloads the new listings from a
rentals site any landlord can post to and saves them in a folder called listings. It can change
only the listings folder and read nothing else, it can't run shell commands, it can reach only the
rentals site on the internet, and it uses no account. Next the rating agent, following a skill file
Priya wrote, reads each new listing and her own list of what she needs (the most rent she can pay,
two bedrooms, a landlord who allows cats), and writes a score and a one-line reason for each
listing into a file called shortlist. Priya started the rating agent with its default settings in
her home folder, so it can read and change every file there, run shell commands and reach the whole
internet. It has no account of its own, but that folder also holds her tax returns and a settings
file where her bank login is saved. Each evening Priya reads the shortlist, visits the places she
likes, and types her own notes on each visit into a file called visit notes. On Fridays the
comparing agent, also following a skill file Priya wrote, reads her visit notes and the monthly
budget she typed herself, and writes a ranked list of the apartments she has seen into a file
called ranking. It runs in a sandbox holding only its skill file, the visit notes, the budget and
the ranking file, where it can change only the ranking file; it can't run shell commands or reach
the internet, and it uses no account.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### rating-agent-reach

Can the rating agent reach anything its step does not need?

1. Yes
2. No

### rating-agent-context

Does untrusted input end up in the rating agent's context while it does its step?

1. Yes
2. No

### comparing-agent-reach

Can the comparing agent reach anything its step does not need?

1. Yes
2. No

### comparing-agent-context

Does untrusted input end up in the comparing agent's context while it does its step?

1. Yes
2. No
