Medium. A thrift store furniture watch with acquire, assess and extract steps, given as Lucia's agent's audit, one bullet per step, and two executors: the fetcher (a program) downloads the store's new listings, and the furniture agent judges each listing against Lucia's measurements and budget and pulls out the price of each item worth a look. The audit states each executor's reach; the learner compares it with what the step does, the bullet's first sentence. Both sandboxes plainly match their steps, so both reach answers are No, yet the furniture agent reads listings the store's staff wrote, so "sandboxed means No" fails on the context question. This scenario carries one reach case (`no-excess`) and one context case (`outside-text`). Each question asks about the step as described, not how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it the listings folder to change, which its step saves into ("Files: it can read and change the listings folder"; "saves them in a folder called listings"), and the thrift store's site, which its step downloads from ("Network: it can reach the thrift store's site"; "downloads the new furniture listings twice a day from the thrift store's website"). Shell commands are off ("Shell commands: they are turned off"), and its step runs no program; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it writes or downloads from.

### furniture-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox leaves it its skill file, the listings folder and Lucia's list to read, which its step follows and reads, and the finds file to change, which its step writes ("Files: it can read its skill file, the listings folder and your list, and it can read and change the finds file"; "reads each new listing in the listings folder and your list ... and writes each item worth a look ... into a file called finds"). Shell commands and the network are off ("Shell commands: they are turned off"; "Network: it is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("Secrets: it holds none"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes. A learner who says yes because the listings are untrusted is answering the next question; ask what it can reach, not what it reads.

### furniture-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file and Lucia's list, which she wrote ("Reads: the skill file and your list, which you wrote"); and each new listing, which the store's staff wrote ("the listings, which the thrift store's staff write"; "where the store's staff post each donated item with a description"). The fetcher saves the listings as downloaded, so the agent reads the staff's own words, and its sandbox does not change what it reads. Follow-up's answer: the thrift store's listings, written by its staff. A learner who says no because it runs in a sandbox should be asked who wrote the listings it reads.
