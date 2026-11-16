Dalia runs a neighborhood book club, and she wants a shortlist of books for each month's vote from the suggestions the club's inbox receives. Her workflow has two steps.

- Every Sunday the sorter, a program, signs in to the club's email account, reads each new message in its inbox, which members and anyone else who has the address from the club's flyers send, copies each message's subject line into a file called suggestions, and moves the message into a folder called seen. It runs in a sandbox with the following restrictions:
  - it allows access to only the suggestions file;
  - shell commands are turned off;
  - the network allowlist has the club's email site on it;
  - it holds a scoped token for the club's email account that reads messages and moves them between folders.
- Then the picking agent, following a skill file Dalia wrote, reads the suggestions file and her list of the books the club has already read, which she typed, and writes a shortlist of five books for the next vote into a file called shortlist.
  - Her home folder holds the skill files, the suggestions file, her list of books, the shortlist file, her tax returns, her household budget and a settings file with her email login.
  - The picking agent is given no login, key or token of its own.

### sorter-reach

Can the sorter reach anything its step does not need?

1. Yes
2. No

### picking-agent-reach

Can the picking agent reach anything its step does not need?

1. Yes
2. No

### picking-agent-context

Could untrusted input end up in the picking agent's context, where it could be taken as instructions?

1. Yes
2. No
