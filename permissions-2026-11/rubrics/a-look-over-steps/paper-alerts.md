Hard. A research paper alert digest with acquire, assess and extract steps and three executors: the fetcher (a program) downloads paper listings from two preprint sites and pulls out titles and keyword counts, the reading agent judges which titles bear on Amara's thesis, and the planning agent plans her reading hours from the counts and her own schedule. Each reach answer turns on one item among things the step does use: a site on the fetcher's allowlist that its step never fetches from, and the reading agent's harness letting shell commands run without asking beside file and network limits. The planning agent's sandbox plainly matches its step. The fetcher reads text any researcher wrote and hands the reading agent the titles word for word, and the planning agent only counts the fetcher worked out. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`passed-through`, `shielded`), and with `scholarship-deadlines` it makes a pair carrying all six. Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and secrets fit its step: the sandbox leaves it her keyword list, read-only, which its step reads, and the papers folder, the titles file and the counts file, which its step writes ("it allows access to only her keyword list, the papers folder, the titles file and the counts file, with the keyword list read-only"; "reads her keyword list ... saves them in a folder called papers ... into a file called titles ... into a file called counts"); no shell commands ("shell commands are turned off"), and its step runs no named program; no secrets ("it holds no logins, keys or tokens"), and its step uses no account. But its allowlist also has a file-sharing site on it ("the network allowlist has the two preprint sites and a file-sharing site on it"), and its step downloads from the two preprint sites alone ("downloads the new paper listings ... from two preprint sites"). Follow-up's answer: the file-sharing site. A learner who says no because it runs in a sandbox should be asked which sites its step downloads from.

### reading-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its step reads its skill file, the titles file and her list of questions, and writes the reading-list file ("reads the titles file and her list of the questions her thesis asks ... and writes the five papers she should read first into a file called reading-list"), and the harness's file setting matches that ("it allows reading its skill file, the titles file and her list of questions, and writing the reading-list file"). But the harness lets it run shell commands without asking ("shell commands run without asking"), and the harness checks only what the agent asks it to do, so a command it runs can do whatever Amara can, as the reading says. Through a command it can read and change her thesis drafts, the papers folder, the counts file, her keyword list, her weekly schedule and the plan file, read the settings file with her university login, which would let it sign in to her university account as her ("Her home folder holds ... her thesis drafts, her weekly schedule, the plan file and a settings file with her university login"), and reach the internet, though the harness refuses the network ("the network is refused"). Its step runs no named program and works on files already on the laptop. Follow-up's answer: through shell commands, her other files and folders, the university login and what it lets one do with her account, and the internet. A learner who says no because the harness limits files and the network should be asked what a shell command it runs can do.

### reading-agent-context

- **goal:** `c-spot-injection`
- **cases:** passed-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file, which Amara wrote ("following a skill file Amara wrote"); her list of questions, which she typed ("her list of the questions her thesis asks, which she typed"); and the titles file, into which the fetcher copies each matching paper's title ("writes the title of each paper whose abstract mentions one of her keywords into a file called titles"). The titles are written by the papers' authors on the preprint sites ("two preprint sites that researchers anywhere post to"), so the fetcher hands the agent part of the outside text word for word. Follow-up's answer: the paper titles, which the authors wrote on the preprint sites. A learner who says no because a program stands between the sites and the agent should be asked whether the titles are the program's own words.

### planning-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the counts file and her weekly schedule, which its step reads, and the plan file, which its step writes, and only the plan file can be changed ("it allows access to only its skill file, the counts file, her weekly schedule and the plan file, all read-only except the plan file"; "reads the counts file and her weekly schedule ... and writes a plan ... into a file called plan"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### planning-agent-context

- **goal:** `c-spot-injection`
- **cases:** shielded
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads three things: its skill file, which Amara wrote ("also following a skill file Amara wrote"); her weekly schedule, which she types ("which she types herself"); and the counts file, which holds how many new papers mention each of her keywords ("writes into a file called counts how many of the new papers mention each keyword"). The fetcher reads the researchers' abstracts, but what it hands this agent is a number it worked out itself beside her own keywords, so no researcher's words reach the planning agent. It never reads the papers folder or the titles file. Follow-up's answer, if asked: none reaches this agent; the researchers' text stops at the fetcher, which hands over only its counts. A learner who says yes may be thinking of the titles the reading agent reads; ask which files the planning agent reads.
