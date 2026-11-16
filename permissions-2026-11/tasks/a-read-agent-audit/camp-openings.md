Ines has two children, and her workflow watches for openings at summer day camps near her home and reminds her when to sign them up. She asked her agent to describe each step: what runs it, how it runs, what it can reach, and what each agent reads. This is its answer.

- **The fetcher**, a program, downloads the openings page from each of five camps' websites every morning, which each camp's staff write and update, and saves them in a folder called camps. It runs in a sandbox.
  - Files: it can read and change the camps folder.
  - Shell commands: they are turned off.
  - Network: it can reach the five camps' sites, which are on the sandbox's network allowlist.
  - Secrets: it holds none.
- **The camp-picking agent**, following your skill file, reads each page in the camps folder and your list of the weeks each child needs care and what each likes doing, and writes each camp week that fits into a file called picks, and into a file called count a number from 0 to 5: how many of the five camps have a week that fits. It runs in a sandbox.
  - Files: it can read its skill file, the camps folder, your list, the folder of your children's medical forms and the count file, and it can read and change the picks file.
  - Shell commands: the only one it can run is a recorder you wrote, which writes a number from 0 to 5 into the count file and refuses anything else.
  - Network: it is turned off.
  - Secrets: it holds none.
  - Reads: the skill file and your list, which you wrote, and the camp pages, which each camp's staff write.
- **The reminder agent**, following your skill file, reads the count file and your work schedule every Monday, and writes which evening this week to sit down and sign up into a file called reminder.
  - Files: it can read and change your files; your home folder holds the skill files, the camps folder, the count file, your list, the picks file, the folder of your children's medical forms, your work schedule, the reminder file and the settings file where your bank login is saved.
  - Shell commands: it can run them, with no limit set.
  - Network: it can reach the internet, with no limit set.
  - Secrets: it holds none of its own, but it can read your bank login in that settings file, which lets its holder see your accounts and move money out of them.
  - Reads: the skill file, which you wrote, your work schedule, which you type yourself, and the count file, where the camp-picking agent writes a number from 0 to 5 for how many of the five camps have a week that fits.

### fetcher-reach

Can the fetcher reach anything its step does not need?

1. Yes
2. No

### camp-picking-agent-reach

Can the camp-picking agent reach anything its step does not need?

1. Yes
2. No

### camp-picking-agent-context

Could untrusted input end up in the camp-picking agent's context, where it could be taken as instructions?

1. Yes
2. No

### reminder-agent-reach

Can the reminder agent reach anything its step does not need?

1. Yes
2. No

### reminder-agent-context

Could untrusted input end up in the reminder agent's context, where it could be taken as instructions?

1. Yes
2. No
