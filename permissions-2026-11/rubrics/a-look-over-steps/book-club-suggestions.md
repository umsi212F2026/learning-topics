Hard. A book club's suggestion inbox with two executors: the sorter (a program) reads the club's new email and copies each subject line into a file, and the picking agent judges those suggestions against Dalia's list and writes a shortlist. The sorter's sandbox and token look broad but leave only what its step uses: its token moves messages, and its step moves them. The picking agent has nothing narrowing it, against a step that reads two files and writes one. The sorter hands the agent the senders' subject lines word for word. This scenario carries both reach cases (`excess`, `no-excess`) and one context case (`passed-through`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### sorter-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the suggestions file ("it allows access to only the suggestions file"), which its step writes ("copies each message's subject line into a file called suggestions"); the club's email site ("the network allowlist has the club's email site on it"), which its step signs in to ("signs in to the club's email account"); no shell commands ("shell commands are turned off"), and its step runs no named program; and a token that reads messages and moves them between folders ("it holds a scoped token for the club's email account that reads messages and moves them between folders"), both of which its step does ("reads each new message in its inbox ... and moves the message into a folder called seen"). Follow-up's answer, if asked: nothing; the file is where it writes, the site is where the inbox is, and the token does the two things its step does. A learner who says yes because the token moves messages should be asked what the step does with each message after copying its subject line.

### picking-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Dalia can. Its step reads the suggestions file and her list of books and writes the shortlist file ("reads the suggestions file and her list of the books the club has already read ... and writes a shortlist of five books for the next vote into a file called shortlist"). It can also read and change her tax returns and her household budget, and read the settings file with her email login, which would let it read her mail and send mail as her ("Her home folder holds ... her tax returns, her household budget and a settings file with her email login"); it can run shell commands, though its step runs no named program; and it can reach the internet, though its step works on files already on the laptop. Follow-up's answer: the tax returns, the household budget, the email login and what it lets one do with her account, shell commands, and the internet.

### picking-agent-context

- **goal:** `c-spot-injection`
- **cases:** passed-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file, which Dalia wrote ("following a skill file Dalia wrote"); her list of books, which she typed ("her list of the books the club has already read, which she typed"); and the suggestions file, into which the sorter copies each message's subject line ("copies each message's subject line into a file called suggestions"). The messages are sent by members and anyone else with the address ("which members and anyone else who has the address from the club's flyers send"), so the sorter hands the agent part of each sender's text word for word. Follow-up's answer: the subject lines of the messages people send the club's inbox. A learner who says no because a program stands between the inbox and the agent should be asked who wrote the subject lines.
