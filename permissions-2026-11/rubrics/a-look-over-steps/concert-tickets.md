Hard. A concert ticket watch with acquire, assess and extract steps and three executors: the fetcher (a program) downloads resale listings, the pricing agent reads them and rates each concert none, few or plenty, and the alert agent judges from those ratings which concerts to check. All three run in sandboxes; the fetcher's leaves it one thing its step never uses, a token that also buys tickets, among files, a site and a token its step does use, and the pricing agent's leaves it nothing beyond its step, the no-reach reader the reading recommends. The pricing agent reads a great deal of text that sellers wrote and hands the alert agent only one word per concert from a fixed list. This scenario carries both reach cases (`excess`, `no-excess`) and two context cases (`outside-text`, `shielded`). Each question asks about the step as described, not how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Its files, shell commands and network fit its step: the sandbox leaves it his concert list, read-only, which its step reads, and the listings folder, which its step writes ("it allows access to only his concert list and the listings folder, with the concert list read-only"; "reads Chen's list of concerts ... saves them in a folder called listings"); no shell commands ("shell commands are turned off"), and its step runs no named program; and the resale site, which it downloads from ("the network allowlist has the resale site on it"; "signs in to his account on a ticket resale site ... downloads the listings"). But its token lets its holder buy tickets with his saved card as well as read listings ("it holds a token for his resale site account that reads listings and buys tickets with the card saved there"), and its step only reads listings. Follow-up's answer: buying tickets with the card saved on his account. A learner who says no because it runs in a sandbox should be asked what its token lets its holder do.

### pricing-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the listings folder and his concert list, which its step reads, all read-only, and the ratings file, which its step writes only through the recorder ("it allows access to only its skill file, the listings folder, his concert list and the ratings file, all read-only"; "the only command it may run is a recorder Chen wrote, which writes one of the three words for a concert into the ratings file"; "reads each new listing ... and his concert list, and writes into a file called ratings"). The recorder is the one command it may run, and its step uses it; the network is off ("the network is turned off"), and its step fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes. A learner who says yes because it reads the sellers' listings is answering the context question; ask what it could touch if one of them steered it.

### pricing-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads three things: its skill file, which Chen wrote ("following a skill file Chen wrote"); his concert list, which he typed ("Chen's list of concerts and the most he will pay for each, which he typed"); and the listings, which sellers wrote ("in which the seller describes the seats and the asking price in their own words"; "a ticket resale site where ticket holders post the tickets they want to sell"). Follow-up's answer: the listings, which ticket holders post on the resale site. A learner who says no because its sandbox is tight should be asked who wrote the listings it reads.

### alert-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The sandbox allows its skill file, the ratings file and his concert list, which its step reads, and the alerts file, which its step writes, and only the alerts file can be changed ("it allows access to only its skill file, the ratings file, his concert list and the alerts file, all read-only except the alerts file"; "reads the ratings file and his concert list, and writes a short note ... into a file called alerts"). Shell commands and the network are off ("shell commands are turned off"; "the network is turned off"), and its step runs no program and fetches nothing; it holds no secrets ("it holds no logins, keys or tokens"), and its step uses no account. Follow-up's answer, if asked: nothing; each thing in the sandbox is one it follows, reads or writes.

### alert-agent-context

- **goal:** `c-spot-injection`
- **cases:** shielded
- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. It reads three things: its skill file, which Chen wrote ("following a skill file Chen wrote"); his concert list, which he typed ("Chen's list of concerts and the most he will pay for each, which he typed"); and the ratings file, which holds one word for each concert, none, few or plenty, from a list in the pricing agent's skill file ("writes into a file called ratings, for each concert, one word from a list in its skill file (none; few; plenty)"). The pricing agent reads the sellers' listings, and a hidden line in one could skew which word it picks, but it can put nothing else in the ratings file: the file is read-only to it, and its only way to write there is the recorder, which refuses anything but one of the three words ("the only command it may run is a recorder Chen wrote, which writes one of the three words for a concert into the ratings file and refuses anything else"). A word from that fixed list carries none of the sellers' words and can't be taken as instructions. It never reads the listings folder. Follow-up's answer, if asked: none reaches this agent; the sellers' text stops at the pricing agent, which hands over only its one-word ratings. A learner who says yes because the ratings come from the listings should be asked whether any words a seller wrote are in the ratings file.
