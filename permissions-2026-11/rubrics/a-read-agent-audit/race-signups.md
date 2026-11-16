Hard. A running race sign-up watch with acquire, assess and extract steps, given as Keiko's agent's audit, one bullet per step, and three executors: the fetcher (a program) logs in to a calendar site any organizer can post to and downloads race listings, the race-picking agent judges each listing against Keiko's list and pulls out the sign-up deadlines, and the training agent plans her week from her own run log and schedule. The audit states each executor's reach; the learner compares it with what the step does, the bullet's first sentence. The fetcher is sandboxed, but the token it holds lets its holder change or delete Keiko's calendar account, which its step never does. The race-picking agent's sandbox plainly matches its step, yet it reads listings race organizers wrote. The training agent has nothing narrowing it, against a step that reads two files and writes one, and it reads only what Keiko wrote. So neither "sandboxed means No" nor "unlimited means untrusted input" gets a learner through. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `owner-only`). Each question asks about the step as described, not how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and network fit its step: the races folder, which it saves into ("Files: it can read and change the races folder"; "saves them in a folder called races"), no shell commands ("Shell commands: they are turned off"), and only the calendar site, which it downloads from ("Network: it can reach the race calendar's site"). But its token lets its holder do more than read listings ("which lets its holder read listings and also change your account's email address and password or delete the account"), and its step only downloads listings ("downloads the new race listings"). Follow-up's answer: changing the account's email address and password, and deleting the account. A learner who says no because it runs in a sandbox should be asked what its token lets its holder do.

### race-picking-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it its skill file, the races folder and Keiko's list to read, which its step follows and reads, and the shortlist file to change, which its step writes ("Files: it can read its skill file, the races folder and your list, and it can read and change the shortlist file"; "reads each new listing in the races folder and your list ... and writes each race that fits ... into a file called shortlist"). Shell commands and the network are off ("Shell commands: they are turned off"; "Network: it is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes. A learner who says yes because the listings are untrusted is answering the next question; ask what it can reach, not what it reads.

### race-picking-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Keiko's list, which she wrote ("Reads: the skill file and your list, which you wrote"); and each new listing, which a race organizer wrote ("the listings, which race organizers post on the race calendar site"; "the new race listings, which any race organizer can post"). The fetcher saves the listings as downloaded, so the agent reads the organizers' own words, and its sandbox does not change what it reads. Follow-up's answer: the race listings on the calendar site.

### training-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated). Its step reads the run log and the work schedule and writes the plan file ("reads your run log and your work schedule for the coming week, and writes a plan ... into a file called plan"). Its audit says it can also read and change the races folder, the shortlist file and her health insurance papers, and read the settings file with her race sign-up login ("Files: it can read and change your files; your home folder holds ... your health insurance papers and the settings file where your login for the race sign-up site is saved"), which lets its holder enter her in races and pay their fees ("Secrets: ... which lets its holder enter you in races and pay their fees with the card saved there"); it can run shell commands ("Shell commands: it can run them"), though its step runs no named program; and it can reach the internet ("Network: it can reach the internet"), though its step works on files already on the laptop. Follow-up's answer: the races folder, the shortlist file, the health insurance papers, the sign-up login and what it lets one do with her account and card, shell commands, and the internet.

### training-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads its skill file, which Keiko wrote ("Reads: the skill file, which you wrote"), and her run log and work schedule, which she types ("your run log and work schedule, which you type yourself"). It can reach the races folder, but its step never reads the listings or the shortlist file. Follow-up's answer, if asked: none reaches this agent. A learner who says yes may be mixing up what it can reach with what it reads; ask what the training agent reads.
