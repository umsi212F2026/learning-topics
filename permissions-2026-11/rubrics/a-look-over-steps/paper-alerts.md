Hard. A research paper alert digest with acquire, assess and extract steps and three executors: the fetcher (a program) downloads paper listings from two preprint sites and pulls out titles, the reading agent judges which titles bear on Amara's thesis and rates each of her questions none, some or many, and the planning agent plans her reading hours from those ratings and her own schedule. Each reach answer turns on one item among things the step does use: a site on the fetcher's allowlist that its step never fetches from, and the reading agent's harness letting shell commands run without asking beside file and network limits. The planning agent's sandbox plainly matches its step. The fetcher reads text any researcher wrote and hands the reading agent the titles word for word. The reading agent is meant to hand the planning agent only one-word ratings through a recorder, which looks like a sound split, but the same shell commands that give it excess reach let a steered reading agent write anything into the levels file, the titles included, so the split doesn't hold: the reading's point that harness limits don't cover a shell command it lets run, seen from the context side. This scenario carries both reach cases (`excess`, `no-excess`) and one context case (`passed-through`, twice), and with `concert-tickets` and `scholarship-deadlines` it makes a trio carrying all six. Each question asks about the step as described, not how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and secrets fit its step: the sandbox leaves it her keyword list, read-only, which its step reads, and the papers folder and the titles file, which its step writes ("it allows access to only her keyword list, the papers folder and the titles file, with the keyword list read-only"; "reads her keyword list ... saves them in a folder called papers ... into a file called titles"); no shell commands ("shell commands are turned off"), and its step runs no named program; no secrets ("it holds no logins, keys or tokens"), and its step uses no account. But its allowlist also has a file-sharing site on it ("the network allowlist has the two preprint sites and a file-sharing site on it"), and its step downloads from the two preprint sites alone ("downloads the new paper listings ... from two preprint sites"). Follow-up's answer: the file-sharing site. A learner who says no because it runs in a sandbox should be asked which sites its step downloads from.

### reading-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its step reads its skill file, the titles file and her list of questions, writes the reading-list file, and records into the levels file by running the recorder ("reads the titles file and her list of the questions her thesis asks ... and writes the five papers she should read first into a file called reading-list. It also records into a file called levels ... by running a recorder Amara wrote"), and the harness's file setting matches that ("it allows reading its skill file, the titles file, her list of questions and the levels file, and writing the reading-list file"). But the harness lets it run any shell command without asking, not only the recorder ("shell commands run without asking"), and the harness checks only what the agent asks it to do, so a command it runs can do whatever Amara can, as the reading says. Through a command it can read and change her thesis drafts, the papers folder, her keyword list, her weekly schedule, the plan file and the levels file, read the settings file with her university login, which would let it sign in to her university account as her ("Her home folder holds ... her thesis drafts, her weekly schedule, the plan file and a settings file with her university login"), and reach the internet, though the harness refuses the network ("the network is refused"). Its step runs no program but the recorder and works on files already on the laptop. Follow-up's answer: through shell commands other than the recorder, her other files and folders, change access to the levels file, the university login and what it lets one do with her account, and the internet. A learner who says no because the harness limits files and the network should be asked what a shell command it runs can do.

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
- **tutor note:** Key: No. The sandbox allows its skill file, the levels file and her weekly schedule, which its step reads, and the plan file, which its step writes, and only the plan file can be changed ("it allows access to only its skill file, the levels file, her weekly schedule and the plan file, all read-only except the plan file"; "reads the levels file and her weekly schedule ... and writes a plan ... into a file called plan"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### planning-agent-context

- **goal:** `c-spot-injection`
- **cases:** passed-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: its skill file, which Amara wrote ("also following a skill file Amara wrote"); her weekly schedule, which she types ("which she types herself"); and the levels file, which the reading agent is meant to fill through the recorder with one word per question ("records into a file called levels ... by running a recorder Amara wrote, which writes one of the three words for a question into the levels file and refuses anything else"). But the reading agent reads the researchers' titles, and its harness lets it run any shell command without asking ("shell commands run without asking"). A hidden line in a title could steer it to run a command that writes into the levels file directly, past both the recorder and the harness's file setting, and put the titles' words, or any words, in front of the planning agent. The recorder holds the fixed form only if it is the reading agent's only way to write there. Follow-up's answer: the paper titles, which researchers wrote, carried through the reading agent by a shell command. A learner who says no because the recorder accepts only three words should be asked what else the reading agent's harness lets it run.
