Hard. A concert ticket watch with acquire, assess and extract steps and two executors: the fetcher (a program) downloads resale listings and works out how many are at or under Chen's price, and the alert agent judges from those counts which concerts to check. Both run in sandboxes; the fetcher's leaves it one thing its step never uses, a token that also buys tickets, among files, a site and a token its step does use. The fetcher reads a great deal of text that sellers wrote and hands the agent only counts it worked out itself. This scenario carries both reach cases (`excess`, `no-excess`) and one context case (`shielded`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and network fit its step: the sandbox leaves it his concert list, read-only, which its step reads, and the listings folder and the counts file, which its step writes ("it allows access to only his concert list, the listings folder and the counts file, with the concert list read-only"; "reads Chen's list of concerts ... saves them in a folder called listings ... writes into a file called counts"); no shell commands ("shell commands are turned off"), and its step runs no named program; and the resale site, which it downloads from ("the network allowlist has the resale site on it"; "signs in to his account on a ticket resale site ... downloads the listings"). But its token lets its holder buy tickets with his saved card as well as read listings ("it holds a token for his resale site account that reads listings and buys tickets with the card saved there"), and its step only reads listings. Follow-up's answer: buying tickets with the card saved on his account. A learner who says no because it runs in a sandbox should be asked what its token lets its holder do.

### alert-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the counts file and his concert list, which its step reads, and the alerts file, which its step writes, and only the alerts file can be changed ("it allows access to only its skill file, the counts file, his concert list and the alerts file, all read-only except the alerts file"; "reads the counts file and his concert list, and writes a short note ... into a file called alerts"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### alert-agent-context

- **goal:** `c-spot-injection`
- **cases:** shielded
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads three things: its skill file, which Chen wrote ("following a skill file Chen wrote"); his concert list, which he typed ("Chen's list of concerts and the most he will pay for each, which he typed"); and the counts file, which holds, for each concert, how many listings are at or under his price ("compares each listing's asking price with his list and writes into a file called counts how many listings for each concert are at or under his price"). The fetcher reads the sellers' listings, but what it hands the agent is a number it worked out by its own rule, beside concert names from his own list, so no seller's words reach the agent. It never reads the listings folder. Follow-up's answer, if asked: none reaches this agent; the sellers' text stops at the fetcher, which hands over only its counts. A learner who says yes because the counts come from the listings should be asked whether any words a seller wrote are in the counts file.
