Nadia is a high school senior who has applied to four universities, and she wants to keep track of the scholarships they offer and when each is due. Her workflow has three steps.

- Every Monday the fetcher, a program, downloads the scholarship pages from the four universities' websites, which each university's staff write and update, and saves them in a folder called pages. It runs in a sandbox with the following restrictions:
  - it allows access to only the pages folder;
  - shell commands are turned off;
  - the network allowlist has the four universities' sites on it;
  - it holds no logins, keys or tokens.
- Then the checking agent, following a skill file Nadia wrote, reads each new page and her own profile, which she typed, with her grades, her planned major and her activities, and writes each scholarship she qualifies for, with its deadline, into a file called matches.
  - Her home folder holds the skill files, the pages folder, her profile, the matches file, a folder of her essay drafts, her financial aid forms and a settings file with her bank login.
  - The checking agent is given no login, key or token of its own.
- On Sunday evenings the essay agent, also following a skill file Nadia wrote, reads the drafts in her essays folder, and her class schedule, which she types herself, and writes a plan for which draft to work on each evening into a file called plan. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the essays folder, her class schedule and the plan file, all read-only except the plan file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### checking-agent-reach

Can the checking agent reach anything its step does not need?

1. Yes
2. No

### checking-agent-context

Does untrusted input end up in the checking agent's context, where it could be taken as instructions?

1. Yes
2. No

### essay-agent-reach

Can the essay agent reach anything its step does not need?

1. Yes
2. No

### essay-agent-context

Does untrusted input end up in the essay agent's context, where it could be taken as instructions?

1. Yes
2. No
