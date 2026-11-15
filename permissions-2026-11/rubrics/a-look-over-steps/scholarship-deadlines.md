Medium. A scholarship deadlines tracker with acquire, assess and extract steps and three executors: the fetcher (a program) downloads university scholarship pages, the checking agent judges each page against Nadia's profile and pulls out the deadlines, and the essay agent plans her week from her own drafts and schedule. The fetcher's and the essay agent's sandboxes plainly match their steps; the checking agent has nothing narrowing it, against a step that reads one folder and one file and writes one file. The checking agent reads pages the universities' staff wrote; the essay agent reads only what Nadia wrote. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `owner-only`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the pages folder ("it allows access to only the pages folder"), which its step writes into ("saves them in a folder called pages"); the four universities' sites ("the network allowlist has the four universities' sites on it"), which its step downloads from ("downloads the scholarship pages from the four universities' websites"); no shell commands ("shell commands are turned off"), and its step runs no named program; and no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; the folder is where it saves and the sites are where it downloads from.

### checking-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Nadia can. Its step reads the new pages and her profile and writes the matches file ("reads each new page and her own profile ... and writes each scholarship she qualifies for, with its deadline, into a file called matches"). It can also read and change the essays folder and her financial aid forms, and read the settings file with her bank login, which would let it see her balance and move her money ("Her home folder holds ... a folder of her essay drafts, her financial aid forms and a settings file with her bank login"); it can run shell commands, though its step runs no named program; and it can reach the internet, though its step works on pages already saved on the laptop. Follow-up's answer: the essay drafts, the financial aid forms, the bank login and what it lets one do with her account, shell commands, and the internet.

### checking-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file, which Nadia wrote ("following a skill file Nadia wrote"); her profile, which she typed ("her own profile, which she typed"); and each new page, which a university's staff wrote ("the scholarship pages ... which each university's staff write and update"). The fetcher saves the pages as downloaded, so the agent reads the staff's own words. Follow-up's answer: the universities' scholarship pages.

### essay-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the essays folder and the class schedule, which its step reads, and the plan file, which its step writes, and only the plan file can be changed ("it allows access to its skill file, the essays folder, her class schedule and the plan file, all read-only except the plan file"; "reads the drafts in her essays folder, and her class schedule ... and writes a plan ... into a file called plan"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### essay-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads its skill file, which Nadia wrote ("also following a skill file Nadia wrote"); her essay drafts, which are her own ("the drafts in her essays folder"); and her class schedule, which she types ("which she types herself"). It never reads the pages or the matches file. Follow-up's answer, if asked: none reaches this agent. A learner who says yes may be thinking of the scholarship pages elsewhere in the workflow; ask which files the essay agent reads.
