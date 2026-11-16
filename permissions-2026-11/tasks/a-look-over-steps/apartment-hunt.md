Bilal is moving to a new city for work, and he wants to find an apartment to rent and plan his weekend viewings. His workflow has four steps.

- Every morning the fetcher, a program, downloads the new listings from a rentals site that landlords post to and saves them in a folder called listings.
  - His home folder holds the skill files, the listings folder, his list of must-haves, the ratings file, his list of booked viewings, his work schedule, the route file, his tax returns and a settings file with his bank login.
  - It is given no login, key or token, since reading the rentals site doesn't require one.
- Then the rating agent, following a skill file Bilal wrote, reads each new listing and his list of must-haves, which he typed, and writes a score out of ten for each listing into a file called ratings. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the listings folder, his list of must-haves and the ratings file, all read-only except the ratings file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.
- Bilal reads the ratings, phones the landlords of the apartments he likes, and books viewings.
- On Friday evenings the route agent, also following a skill file Bilal wrote, reads his list of booked viewings and his work schedule, both of which he types himself, and writes the order in which to visit the apartments on Saturday into a file called route. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, his list of booked viewings, his work schedule and the route file, all read-only except the route file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### rating-agent-reach

Can the rating agent reach anything its step does not need?

1. Yes
2. No

### rating-agent-context

Does untrusted input end up in the rating agent's context, where it could be taken as instructions?

1. Yes
2. No

### route-agent-reach

Can the route agent reach anything its step does not need?

1. Yes
2. No

### route-agent-context

Does untrusted input end up in the route agent's context, where it could be taken as instructions?

1. Yes
2. No
