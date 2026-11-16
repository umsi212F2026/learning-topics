Gustavo gives talks on urban beekeeping, and his workflow watches for conferences calling for talks he could give and works out how many he can afford to apply to. He asked his agent to describe each step: what runs it, how it runs, what it can reach, and what each agent reads. This is its answer.

- **The fetcher**, a program, downloads the new calls for talks every night from two conference listing sites, where any conference organizer can post a call, and saves them in a folder called calls; it also copies each new call's title and topic description into a file called topics, and writes into a file called counts how many of the new calls offer speakers a travel grant. It runs in a sandbox.
  - Files: it can read and change the calls folder, the topics file and the counts file.
  - Shell commands: they are turned off.
  - Network: it can reach the two conference listing sites, which are on the sandbox's network allowlist.
  - Secrets: it holds none.
- **The matching agent**, following your skill file, reads the topics file and your list of the talks you can give, and writes each call that fits one of your talks into a file called shortlist. Its harness's permission settings limit it.
  - Files: it can read its skill file, the topics file and your list of talks, and it can read and change the shortlist file.
  - Shell commands: its harness refuses them.
  - Network: its harness refuses it.
  - Secrets: it holds none.
  - Reads: the skill file and your list of talks, which you wrote, and the topics file, where the fetcher copies each call's title and topic description, which the conference's organizers wrote.
- **The budget agent**, following your skill file, reads the counts file and your travel budget for the year on the first of each month, and writes how many conferences you can afford to apply to that month into a file called trips. It runs in a sandbox.
  - Files: it can read and change its skill file, the counts file, your travel budget and the trips file.
  - Shell commands: they are turned off.
  - Network: it is turned off.
  - Secrets: it holds none.
  - Reads: the skill file, which you wrote, your travel budget, which you type yourself, and the counts file, where the fetcher writes how many of the new calls offer a travel grant.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### matching-agent-reach

Can the matching agent reach anything its step does not need?

1. Yes
2. No

### matching-agent-context

Does untrusted input end up in the matching agent's context, where it could be taken as instructions?

1. Yes
2. No

### budget-agent-reach

Can the budget agent reach anything its step does not need?

1. Yes
2. No

### budget-agent-context

Does untrusted input end up in the budget agent's context, where it could be taken as instructions?

1. Yes
2. No
