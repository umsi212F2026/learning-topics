Amara is a graduate student in ecology, and she wants a short weekly list of the new papers in her field that are worth her time. Her workflow has three steps.

- Every night the fetcher, a program, reads her keyword list, which she typed, downloads the new paper listings, each with its title, authors and abstract, from two preprint sites that researchers anywhere post to, and saves them in a folder called papers. It also writes the title of each paper whose abstract mentions one of her keywords into a file called titles, and writes into a file called counts how many of the new papers mention each keyword. It runs in a sandbox with the following restrictions:
  - it allows access to only her keyword list, the papers folder, the titles file and the counts file, with the keyword list read-only;
  - shell commands are turned off;
  - the network allowlist has the two preprint sites and a file-sharing site on it;
  - it holds no logins, keys or tokens.
- Then the reading agent, following a skill file Amara wrote, reads the titles file and her list of the questions her thesis asks, which she typed, and writes the five papers she should read first into a file called reading-list. Its harness's permission settings set the following restrictions:
  - it allows reading its skill file, the titles file and her list of questions, and writing the reading-list file;
  - shell commands run without asking;
  - the network is refused.
  - Her home folder holds the skill files, her keyword list, the papers folder, the titles file, the counts file, her list of questions, the reading-list file, her thesis drafts, her weekly schedule, the plan file and a settings file with her university login.
- On Sunday evenings the planning agent, also following a skill file Amara wrote, reads the counts file and her weekly schedule, which she types herself, and writes a plan for how many hours to set aside for reading each day into a file called plan. It runs in a sandbox with the following restrictions:
  - it allows access to only its skill file, the counts file, her weekly schedule and the plan file, all read-only except the plan file;
  - shell commands are turned off;
  - the network is turned off;
  - it holds no logins, keys or tokens.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### reading-agent-reach

Can the reading agent reach anything its step does not need?

1. Yes
2. No

### reading-agent-context

Does untrusted input end up in the reading agent's context while it does its step?

1. Yes
2. No

### planning-agent-reach

Can the planning agent reach anything its step does not need?

1. Yes
2. No

### planning-agent-context

Does untrusted input end up in the planning agent's context while it does its step?

1. Yes
2. No
