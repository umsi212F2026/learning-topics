Keiko runs on weekends, and her workflow watches for local races she might enter and plans her runs each week. She asked her agent to describe each step, and this is its answer.

**The fetcher.** Every morning, downloads the new race listings from a regional race calendar site, where any race organizer can post, and saves them in a folder called races. A program. It runs in a sandbox that allows access to only the races folder, with shell commands turned off, a network allowlist with the race calendar's site on it, and no logins, keys or tokens. Files: it can read and change the races folder. Shell commands: they are turned off. Network: it can reach the race calendar's site, which is on the sandbox's network allowlist. Secrets: it holds none.

**The race-picking agent.** Reads each new listing in the races folder and your list of the distances you want to run and the weekends you are free, and writes each race that fits, with its sign-up deadline, into a file called shortlist. An agent following your skill file. You start it yourself. Files: it can read and change your files; your home folder holds the skill files, the races folder, your list, the shortlist file, your run log, your work schedule, your health insurance papers and the settings file where your login for the race sign-up site is saved. Shell commands: it can run them, with no limit set. Network: it can reach the internet, with no limit set. Secrets: it holds none of its own, but it can read your race sign-up login in that settings file, which would let it enter you in races and pay their fees with the card saved there. It reads the skill file and your list, which you wrote, and the listings, which race organizers post on the race calendar site.

**The training agent.** On Sunday evenings, reads your run log and your work schedule for the coming week and writes a plan for which days to run and how far into a file called plan. An agent following your skill file. It runs in a sandbox that allows access to only its skill file, your run log, your work schedule and the plan file, all read-only except the plan file, with shell commands turned off, the network turned off, and no logins, keys or tokens. Files: it can read its skill file, your run log and your work schedule, and it can read and change the plan file. Shell commands: they are turned off. Network: it is turned off. Secrets: it holds none. It reads the skill file, which you wrote, and your run log and work schedule, which you type yourself.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### race-picking-agent-reach

Can the race-picking agent reach anything its step does not need?

1. Yes
2. No

### race-picking-agent-context

Does untrusted input end up in the race-picking agent's context while it does its step?

1. Yes
2. No

### training-agent-reach

Can the training agent reach anything its step does not need?

1. Yes
2. No

### training-agent-context

Does untrusted input end up in the training agent's context while it does its step?

1. Yes
2. No
