Hard. A podcast's guest requests, given as Kenji's agent's audit, one bullet per step, with two executors and a step Kenji does by hand: the mail program reads each new email to the show's guest address and copies its sender name and subject line into a file, the sorting agent ranks the requests against Kenji's planned topics, and Kenji answers the ones he chooses, a step no question asks about. The audit states each executor's reach; the learner compares it with what the step does, the bullet's first sentence. Both executors are sandboxed. The mail program's files, commands and network fit its step, and the one unneeded thing is that its token also sends mail, for a step that only reads. The sorting agent's sandbox plainly matches its step, but the mail program hands it the senders' own subject lines, word for word. This scenario carries both reach cases (`excess`, `no-excess`) and one context case (`passed-through`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### mail-program-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and network fit its step: the pitches file, which it copies into ("Files: it can read and change the pitches file"; "copies each one's sender name and subject line into a file called pitches"), no shell commands ("Shell commands: they are turned off"), and only the email provider's site, where it reads the account's mail ("Network: it can reach your email provider's site"). But its token also lets its holder send mail from the account ("which lets its holder read the account's mail and send mail from it"), and its step only reads ("reads each new email sent to the show's guest address"). Follow-up's answer: sending mail from the podcast's account. A learner who says no because it runs in a sandbox should be asked what its token lets its holder do.

### sorting-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it its skill file, the pitches file and Kenji's list of topics to read, which its step follows and reads, and the ranking file to change, which its step writes ("Files: it can read its skill file, the pitches file and your list of topics, and it can read and change the ranking file"; "reads the pitches file and your list of the topics ... and writes the requests ... into a file called ranking"). Shell commands and the network are off ("Shell commands: they are turned off"; "Network: it is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes. A learner who says yes because the subject lines come from strangers is answering the next question; ask what it can reach, not what it reads.

### sorting-agent-context

- **goal:** `c-spot-injection`
- **cases:** passed-through
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Kenji's list of topics, which he wrote ("Reads: the skill file and your list of topics, which you wrote"); and the pitches file, where the mail program copies each request's sender name and subject line, which the sender wrote ("the pitches file, where the mail program copies each request's sender name and subject line, which the sender wrote"). The mail program reads the whole email and hands over only part of it, but that part is the sender's own words. Follow-up's answer: the sender names and subject lines of the guest requests, which anyone emailing the show writes. A learner who says no because a program handles the emails first should be asked whose words the subject lines are.
