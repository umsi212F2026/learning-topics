Medium. A running race sign-up watch with acquire, assess and extract steps, given as Keiko's agent's audit, one block per step, and three executors: the fetcher (a program) downloads race listings from a calendar site any organizer can post to, the race-picking agent judges each listing against Keiko's list and pulls out the sign-up deadlines, and the training agent plans her week from her own run log and schedule. The audit states each executor's reach; the learner compares it with what the step does, the block's first sentence. The fetcher's and the training agent's sandboxes plainly match their steps; Keiko starts the race-picking agent herself with nothing narrowing it, against a step that reads one folder and one file and writes one file. The race-picking agent reads listings race organizers wrote; the training agent reads only what Keiko wrote. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `owner-only`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the races folder ("Files: it can read and change the races folder"), which its step saves into ("saves them in a folder called races"); the race calendar's site ("Network: it can reach the race calendar's site"), which its step downloads from ("downloads the new race listings from a regional race calendar site"); no shell commands ("Shell commands: they are turned off"), and its step runs no named program; and no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; the folder is where it saves and the site is where it downloads from.

### race-picking-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it ("You start it yourself", with no limits listed). Its step reads the new listings and Keiko's list and writes the shortlist file ("Reads each new listing in the races folder and your list ... and writes each race that fits, with its sign-up deadline, into a file called shortlist"). Its audit says it can also read and change her run log, her work schedule and her health insurance papers, and read the settings file with her race sign-up login ("Files: it can read and change your files; your home folder holds ... your run log, your work schedule, your health insurance papers and the settings file where your login for the race sign-up site is saved"), which would let it enter her in races and pay their fees ("Secrets: ... which would let it enter you in races and pay their fees with the card saved there"); it can run shell commands ("Shell commands: it can run them"), though its step runs no named program; and it can reach the internet ("Network: it can reach the internet"), though its step works on listings already saved on the laptop. Follow-up's answer: the run log, the work schedule, the health insurance papers, the sign-up login and what it lets one do with her account and card, shell commands, and the internet.

### race-picking-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Keiko's list, which she wrote ("It reads the skill file and your list, which you wrote"); and each new listing, which a race organizer wrote ("the listings, which race organizers post on the race calendar site"; "a regional race calendar site, where any race organizer can post"). The fetcher saves the listings as downloaded, so the agent reads the organizers' own words. Follow-up's answer: the race listings on the calendar site.

### training-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the run log and the work schedule, read-only, which its step follows and reads, and the plan file, which its step writes, and only the plan file can be changed ("Files: it can read its skill file, your run log and your work schedule, and it can read and change the plan file"; "reads your run log and your work schedule for the coming week and writes a plan ... into a file called plan"). Shell commands and the network are off ("Shell commands: they are turned off"; "Network: it is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### training-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads its skill file, which Keiko wrote ("the skill file, which you wrote"), and her run log and work schedule, which she types ("your run log and work schedule, which you type yourself"). It never reads the listings or the shortlist file. Follow-up's answer, if asked: none reaches this agent. A learner who says yes may be thinking of the race listings elsewhere in the workflow; ask what the training agent reads.
