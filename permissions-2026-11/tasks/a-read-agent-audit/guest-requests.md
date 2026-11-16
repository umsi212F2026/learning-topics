Kenji hosts a weekly podcast about home cooking, and his workflow sorts the emails people send offering to be a guest, so he can answer the most promising ones first. He asked his agent to describe each step: what runs it, how it runs, what it can reach, and what each agent reads. This is its answer.

- **The mail program**, a program, logs in to your podcast's email account with your token every hour, reads each new email sent to the show's guest address, and copies each one's sender name and subject line into a file called pitches. It runs in a sandbox.
  - Files: it can read and change the pitches file.
  - Shell commands: they are turned off.
  - Network: it can reach your email provider's site, which is on the sandbox's network allowlist.
  - Secrets: it holds your token for the podcast's email account, which lets its holder read the account's mail and send mail from it.
- **The sorting agent**, following your skill file, reads the pitches file and your list of the topics you plan for this season, and writes the requests, in the order you should answer them, into a file called ranking. It runs in a sandbox.
  - Files: it can read its skill file, the pitches file and your list of topics, and it can read and change the ranking file.
  - Shell commands: they are turned off.
  - Network: it is turned off.
  - Secrets: it holds none.
  - Reads: the skill file and your list of topics, which you wrote, and the pitches file, where the mail program copies each request's sender name and subject line, which the sender wrote.
- **You** read the ranking each Friday and answer the requests you choose.

### mail-program-reach

Can the mail program reach anything its step does not need?

1. Yes
2. No

### sorting-agent-reach

Can the sorting agent reach anything its step does not need?

1. Yes
2. No

### sorting-agent-context

Could untrusted input end up in the sorting agent's context, where it could be taken as instructions?

1. Yes
2. No
