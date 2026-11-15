Medium. An apartment hunt with acquire, assess and extract steps, three executors and a step Bilal does by hand: the fetcher (a program) downloads listings from a rentals site, the rating agent scores each one against his must-haves, Bilal books viewings by phone, and the route agent orders the viewings from his own lists. The fetcher has nothing narrowing it, against a step that writes one folder and fetches from one site; both agents' sandboxes plainly match their steps. The rating agent reads listings landlords wrote, though it is sandboxed; the route agent reads only what Bilal typed. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `owner-only`). No question is asked about Bilal's own step. Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Bilal can. Its step downloads listings from the rentals site and writes them into the listings folder ("downloads the new listings from a rentals site that landlords post to and saves them in a folder called listings"). It can also read and change his other files, among them his tax returns, and read the settings file with his bank login, which would let it see his balance and move his money ("His home folder holds ... his tax returns and a settings file with his bank login"); it can run shell commands, though its step runs no named program; and it can reach the whole internet, though its step fetches from the rentals site alone. Follow-up's answer: his other files and folders, the tax returns, the bank login and what it lets one do with his account, shell commands, and sites beyond the rentals site.

### rating-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the listings folder and his list of must-haves, which its step reads, and the ratings file, which its step writes, and only the ratings file can be changed ("it allows access to only its skill file, the listings folder, his list of must-haves and the ratings file, all read-only except the ratings file"; "reads each new listing and his list of must-haves ... and writes a score out of ten for each listing into a file called ratings"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and works on listings already saved; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### rating-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: the skill file, which Bilal wrote ("following a skill file Bilal wrote"); his list of must-haves, which he typed ("his list of must-haves, which he typed"); and each new listing, which a landlord wrote ("a rentals site that landlords post to"). The fetcher saves the listings as downloaded, so the agent reads the landlords' own words, and its sandbox limits what it reaches, not what it reads. Follow-up's answer: the listings on the rentals site. A learner who says no because the agent runs in a sandbox should be asked who wrote the listings it reads.

### route-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, his list of booked viewings and his work schedule, which its step reads, and the route file, which its step writes, and only the route file can be changed ("it allows access to only its skill file, his list of booked viewings, his work schedule and the route file, all read-only except the route file"; "reads his list of booked viewings and his work schedule ... and writes the order in which to visit the apartments on Saturday into a file called route"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### route-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads its skill file, which Bilal wrote ("also following a skill file Bilal wrote"), and his list of booked viewings and his work schedule, which he types ("both of which he types himself"). It never reads the listings or the ratings file. Follow-up's answer, if asked: none reaches this agent. A learner who says yes may be thinking of the listings elsewhere in the workflow, or of the landlords Bilal phoned; ask which files the route agent reads and who typed them.
