Hard. A conference call-for-talks tracker with acquire, assess and extract steps, given as Gustavo's agent's audit, one bullet per step, and three executors: the fetcher (a program) downloads calls from two listing sites any organizer can post to, copies each call's title and topic description into one file and writes a count of travel grants into another, the matching agent judges the copied titles and descriptions against Gustavo's list of talks, and the budget agent works out how many conferences he can afford from the count and his own budget. The audit states each executor's reach; the learner compares it with what the step does, the bullet's first sentence. The fetcher's sandbox holds several files, each of which its step writes, and the matching agent's harness plainly matches its step, so both are No; the budget agent's sandbox looks just as tight but lets it change three files its step only reads. The fetcher reads a great deal of organizers' text, hands the matching agent part of it word for word, and hands the budget agent only a count it worked out itself. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`passed-through`, `shielded`), and with `race-signups` it makes a pair carrying all six. Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the calls folder, the topics file and the counts file to change, and its step writes all three ("Files: it can read and change the calls folder, the topics file and the counts file"; "saves them in a folder called calls; it also copies ... into a file called topics, and writes into a file called counts"). Its network reaches the two listing sites, which its step downloads from ("Network: it can reach the two conference listing sites"; "downloads the new calls for talks every night from two conference listing sites"). Shell commands are off ("Shell commands: they are turned off"), and its step runs no program; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it writes or downloads from. A learner who says yes because the sandbox holds three places should be asked which of them its step does not write.

### matching-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The harness leaves it its skill file, the topics file and Gustavo's list of talks to read, which its step follows and reads, and the shortlist file to change, which its step writes ("Files: it can read its skill file, the topics file and your list of talks, and it can read and change the shortlist file"; "reads the topics file and your list of the talks you can give, and writes each call that fits ... into a file called shortlist"). The harness refuses shell commands, so no command can get around its file limit, and refuses the network ("Shell commands: its harness refuses them"; "Network: its harness refuses it"); its step runs no program and fetches nothing. It holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing. A learner who says yes because the topics file holds organizers' words is answering the next question; ask what it can reach, not what it reads.

### matching-agent-context

- **goal:** `c-spot-injection`
- **cases:** passed-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Gustavo's list of talks, which he wrote ("Reads: the skill file and your list of talks, which you wrote"); and the topics file, where the fetcher copies each call's title and topic description, which the conference's organizers wrote ("the topics file, where the fetcher copies each call's title and topic description, which the conference's organizers wrote"; "where any conference organizer can post a call"). The fetcher stands between the sites and the agent, but it hands over part of the organizers' text word for word. Follow-up's answer: the calls' titles and topic descriptions, which organizers post on the listing sites. A learner who says no because a program handles the calls first should be asked whose words the titles and descriptions are.

### budget-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its shell commands, network and secrets fit its step: shell commands and the network are off ("Shell commands: they are turned off"; "Network: it is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Its files are the ones its step uses, but it can change all four ("Files: it can read and change its skill file, the counts file, your travel budget and the trips file"), and its step only reads the skill file, the counts file and the budget and writes only the trips file ("reads the counts file and your travel budget ... and writes how many conferences ... into a file called trips"). Follow-up's answer: change access to the skill file, the counts file and the travel budget. A learner who says no because the sandbox holds only the files its step uses should be asked which of those files its step changes.

### budget-agent-context

- **goal:** `c-spot-injection`
- **cases:** shielded
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads three things: its skill file, which Gustavo wrote, and his travel budget, which he types ("Reads: the skill file, which you wrote, your travel budget, which you type yourself"); and the counts file, which holds how many of the new calls offer a travel grant ("the counts file, where the fetcher writes how many of the new calls offer a travel grant"). The fetcher reads the organizers' calls, but what it hands this agent is a number it worked out itself, so no organizer's words reach the budget agent. It never reads the calls folder or the topics file. Follow-up's answer, if asked: none reaches this agent; the organizers' text stops at the fetcher, which hands over only its count. A learner who says yes may be thinking of the topics file the matching agent reads; ask which files the budget agent reads.
