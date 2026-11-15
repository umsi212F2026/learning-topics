Hard. A summer camp openings watch with acquire, assess and extract steps, given as Ines's agent's audit, one bullet per step, and three executors: the fetcher (a program) downloads five camps' openings pages and writes a count of the pages with open spots, the camp-picking agent judges each page against Ines's list and pulls out the weeks that fit, and the reminder agent picks an evening to sign up from the count and her own work schedule. The audit states each executor's reach; the learner compares it with what the step does, the bullet's first sentence. The fetcher's sandbox plainly matches its step. The camp-picking agent is sandboxed, but its sandbox also holds the folder of medical forms, which its step never uses, and it reads pages the camps' staff wrote. The reminder agent has nothing narrowing it, and reads only a count the fetcher worked out beside Ines's own schedule. So neither "sandboxed means No" nor "unlimited means untrusted input" gets a learner through. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `shielded`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the camps folder and the count file to change, and its step writes both ("Files: it can read and change the camps folder and the count file"; "saves them in a folder called camps; it also writes into a file called count"). Its network reaches the five camps' sites, which its step downloads from ("Network: it can reach the five camps' sites"; "downloads the openings page from each of five camps' websites"). Shell commands are off ("Shell commands: they are turned off"), and its step runs no program; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it writes or downloads from.

### camp-picking-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Most of its reach fits its step: it reads its skill file, the camps folder and Ines's list and changes the picks file ("Files: it can read its skill file, the camps folder, your list ... and it can read and change the picks file"; "reads each page in the camps folder and your list ... and writes each camp week that fits into a file called picks"), with shell commands and the network off and no secrets ("Shell commands: they are turned off"; "Network: it is turned off"; "Secrets: it holds none"). But it can also read the folder of her children's medical forms ("the folder of your children's medical forms"), which its step never reads. Follow-up's answer: the folder of medical forms. A learner who says no because it runs in a sandbox should be asked which of the files in its sandbox its step reads.

### camp-picking-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Ines's list, which she wrote ("Reads: the skill file and your list, which you wrote"); and each camp's openings page, which that camp's staff wrote ("the camp pages, which each camp's staff write"; "which each camp's staff write and update"). The fetcher saves the pages as downloaded, so the agent reads the staff's own words, and its sandbox does not change what it reads. Follow-up's answer: the five camps' openings pages, written by each camp's staff.

### reminder-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated). Its step reads the count file and the work schedule and writes the reminder file ("reads the count file and your work schedule every Monday, and writes ... into a file called reminder"). Its audit says it can also read and change the camps folder, the picks file and the folder of medical forms, and read the settings file with her bank login ("Files: it can read and change your files; your home folder holds ... the folder of your children's medical forms ... and the settings file where your bank login is saved"), which lets its holder see her accounts and move money ("Secrets: ... which lets its holder see your accounts and move money out of them"); it can run shell commands ("Shell commands: it can run them"), though its step runs no named program; and it can reach the internet ("Network: it can reach the internet"), though its step works on files already on the laptop. Follow-up's answer: the camps folder, the picks file, the medical forms, the bank login and what it lets one do with her accounts, shell commands, and the internet.

### reminder-agent-context

- **goal:** `c-spot-injection`
- **cases:** shielded
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads three things: its skill file, which Ines wrote, and her work schedule, which she types ("Reads: the skill file, which you wrote, your work schedule, which you type yourself"); and the count file, which holds how many of the five pages list a week with open spots ("the count file, where the fetcher writes how many of the five camp pages list a week with open spots"). The fetcher reads the staff's pages, but what it hands this agent is a number it worked out itself, so no staff member's words reach the reminder agent. It can reach the camps folder, but its step never reads the pages or the picks file. Follow-up's answer, if asked: none reaches this agent; the camps' text stops at the fetcher, which hands over only its count. A learner who says yes may be mixing up what it can reach with what it reads; ask which files the reminder agent reads.
