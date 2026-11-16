Chen wants tickets to a few sold-out concerts at a good price, and his workflow watches a ticket resale site for them. His workflow has three steps.

- Every hour the fetcher, a program, reads Chen's list of concerts and the most he will pay for each, which he typed, signs in to his account on a ticket resale site where ticket holders post the tickets they want to sell, downloads the listings for those concerts and saves them in a folder called listings. It runs in a sandbox with the following restrictions:
  - it allows access to only his concert list and the listings folder, with the concert list read-only;
  - shell commands are turned off;
  - the network allowlist has the resale site on it;
  - it holds a token for his resale site account that reads listings and buys tickets with the card saved there.
- Then the pricing agent, following a skill file Chen wrote, reads each new listing, in which the seller describes the seats and the asking price in their own words, and his concert list, and writes into a file called ratings, for each concert, one word from a list in its skill file (none; few; plenty), saying how many listings offer real seats at or under his price. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the listings folder, his concert list and the ratings file, all read-only;
  - the only command it may run is a recorder Chen wrote, which writes one of the three words for a concert into the ratings file and refuses anything else;
  - the network is turned off;
  - it holds no logins, keys or tokens.
- Then the alert agent, following a skill file Chen wrote, reads the ratings file and his concert list, and writes a short note on which concerts are worth checking tonight into a file called alerts. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the ratings file, his concert list and the alerts file, all read-only except the alerts file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### pricing-agent-reach

Can the pricing agent reach anything its step does not need?

1. Yes
2. No

### pricing-agent-context

Could untrusted input end up in the pricing agent's context, where it could be taken as instructions?

1. Yes
2. No

### alert-agent-reach

Can the alert agent reach anything its step does not need?

1. Yes
2. No

### alert-agent-context

Could untrusted input end up in the alert agent's context, where it could be taken as instructions?

1. Yes
2. No
