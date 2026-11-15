Chen wants tickets to a few sold-out concerts at a fair price, and his workflow watches a ticket resale site for them. His workflow has two steps.

- Every hour the fetcher, a program, reads Chen's list of concerts and the most he will pay for each, which he typed, signs in to his account on a ticket resale site where ticket holders post the tickets they want to sell, downloads the listings for those concerts and saves them in a folder called listings. It then compares each listing's asking price with his list and writes into a file called counts how many listings for each concert are at or under his price. It runs in a sandbox with the following restrictions:
  - it allows access to only his concert list, the listings folder and the counts file, with the concert list read-only;
  - shell commands are turned off;
  - the network allowlist has the resale site on it;
  - it holds a token for his resale site account that reads listings and buys tickets with the card saved there.
- Then the alert agent, following a skill file Chen wrote, reads the counts file and his concert list, and writes a short note on which concerts are worth checking tonight into a file called alerts. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the counts file, his concert list and the alerts file, all read-only except the alerts file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### alert-agent-reach

Can the alert agent reach anything its step does not need?

1. Yes
2. No

### alert-agent-context

Does untrusted input end up in the alert agent's context while it does its step?

1. Yes
2. No
