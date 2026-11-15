Rosa's workflow keeps track of conferences asking for talks, so she can propose talks to the ones that fit her. She asked her agent to describe each step: what it does, what runs it, how it runs, what it can read, change, run and reach, what its secrets let it do, and what each agent step reads. This is its answer.

> **The fetcher.** Every Monday it downloads the new calls for talks from a conference listings site, where any organizer can post a call, and saves them in a folder called calls. A program. You start it, and it runs as you in a sandbox holding the calls folder, with shell commands turned off and the listings site on the sandbox's network allowlist. Files: it can read and change the calls folder. Shell commands: they are turned off. Network: it can reach the listings site, which is on the sandbox's network allowlist. Secrets: it holds no logins, keys or tokens.
>
> **The rating agent.** It reads each new call in the calls folder and your list of the topics you speak on and the weeks you can travel, and writes a rating and a one-line reason for each call into a file called matches. An agent following your skill file. You start it in your home folder with its harness's default settings, which set no limits. Files: it can read and change the files in your home folder, which hold your two skill files, the calls folder, your list, the matches file, the talk notes folder, your bio, a scan of your passport and the settings file where your bank login is saved. Shell commands: it can run them, with no limit set. Network: it can reach the internet, with no limit set. Secrets: it holds none of its own, but it can read your bank login in that settings file, which would let it see your balance and move money. It reads its skill file and your list, which you wrote, and the calls, which conference organizers posted on the listings site.
>
> **Your picks.** You read the matches file and type the title of each of your own talks that you want to propose into a file called to-write.
>
> **The abstract agent.** It reads the to-write file, your notes on each of your talks in the talk notes folder, and your speaker bio, and writes a draft abstract for each talk named in to-write into a folder called drafts. An agent following your skill file. You start it, and it runs as you in a sandbox holding its skill file, the to-write file, the talk notes folder, your bio and the drafts folder, where the skill file, the to-write file, the talk notes folder and your bio are read-only to it, with shell commands and the network turned off. Files: it can read the skill file, the to-write file, the talk notes folder and your bio, and it can read and change the drafts folder. Shell commands: they are turned off. Network: it is turned off. Secrets: it holds no logins, keys or tokens. It reads the skill file, the to-write file, your talk notes and your bio, which you wrote.

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

### abstract-agent-reach

Can the abstract agent reach anything its step does not need?

1. Yes
2. No

### abstract-agent-context

Does untrusted input end up in the abstract agent's context while it does its step?

1. Yes
2. No
