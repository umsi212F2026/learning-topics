Medium. A call-for-talks tracker with three executors, laid out as the agent's audit: the fetcher (a program) acquires calls from a listings site any organizer can post to, the rating agent assesses them, and the abstract agent drafts abstracts from what Rosa wrote. Rosa's own picking step gets no question. The fetcher's and the abstract agent's limits plainly match their steps; the rating agent runs with its harness's default settings in the home folder, against a step that uses one folder and two files. The rating agent reads the calls, which organizers wrote; the abstract agent reads only what Rosa wrote. Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No. The sandbox leaves it the calls folder, which it can read and change ("Files: it can read and change the calls folder"), and that is the folder its step saves into ("saves them in a folder called calls"). On the network it can reach the listings site, which is where its step downloads from ("Network: it can reach the listings site"). Shell commands are off and it holds no secrets, and its step runs no program and uses no account. If asked what it can reach that its step doesn't need, the answer is nothing: the site is where it fetches from and the folder is where it saves.

### rating-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for 2.
- **tutor note:** Yes. Its step reads the new calls and Rosa's list and writes the matches file ("reads each new call in the calls folder and your list ... and writes a rating and a one-line reason for each call into a file called matches"). Its harness's default settings set no limits, so it can do whatever Rosa can: read and change the files in her home folder, including her passport scan and the settings file with her bank login ("which hold ... a scan of your passport and the settings file where your bank login is saved"), use that login to see her balance and move money ("which would let it see your balance and move money"), run shell commands and reach the internet ("with no limit set"). A step that works on saved calls, fetches nothing, runs no program and uses no account needs none of those. Follow-up's answer: the passport scan, the bank login and what it lets one do, the other files in her home folder (the talk notes, the bio, the other skill file), shell commands, and the internet.

### rating-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for 2.
- **tutor note:** Yes. It reads three things: the skill file and the list, which Rosa wrote ("It reads its skill file and your list, which you wrote"), and the calls, which organizers posted on a site where any organizer can post ("the calls, which conference organizers posted on the listings site"; "where any organizer can post a call"). The fetcher saves the calls as downloaded, so the agent reads the organizers' own words. Follow-up's answer: the calls for talks, which any organizer can post on the listings site.

### abstract-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No. Its sandbox leaves it the skill file it follows and the three things its step reads (the to-write file, the talk notes folder and the bio), all read-only, and the drafts folder, which it can change and which its step writes into ("Files: it can read the skill file, the to-write file, the talk notes folder and your bio, and it can read and change the drafts folder"). Shell commands and the network are off and it holds no secrets, and its step runs no program, fetches nothing and uses no account. If asked what it can reach that its step doesn't need, the answer is nothing: every file it can get to is one it follows, reads or writes.

### abstract-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No. It reads the skill file, the to-write file, the talk notes and the bio, and Rosa wrote each of them ("It reads the skill file, the to-write file, your talk notes and your bio, which you wrote"; "type the title of each of your own talks"). It never reads the calls, the matches file, or anything copied from them. If asked where outside text comes from, the answer is that none reaches this agent. A learner who says yes may be thinking of the calls, or of the matches file the picks were made from; ask which files the abstract agent reads.
