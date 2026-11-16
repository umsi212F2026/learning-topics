A seed swap forum watch, one step: the swap agent fetches posts anyone can write, reads them, and writes matching offers into the swaps file, running with nothing narrowing it. The harm comes from untrusted input steering the agent into using reach its step doesn't need: a hidden line in a post (untrusted input in its context: "reads each one"; "Anyone can post on the forum") makes it delete the planting records folder, which it can change, since nothing narrows it (no limit is stated) and by the reading's rule it can do whatever she can, but which its step never touches. The deletion would happen during the evening run, before anything reaches the morning program. The step uses its skill file, the wish list, the forum on the internet, and the swaps file it writes, with the wish-list seeds each matching post offers. Three proposals, one from each of the reading's groups: a sandbox (`sound-limit`, Medium), a person approving every trade offer (`no-effect`, Hard) and a split, an agent with no reach reading the posts and recording only wish-list seeds through a program (`sound-limit`, Hard).

### sandbox

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. To delete the records folder the agent has to be able to change it, which it can today because nothing narrows it (no limit is stated). The sandbox holds only the skill file, the wish list and the swaps file, so the records folder isn't in it, and a sandbox covers every command the agent runs, so no route reaches the folder. A hidden line can still steer the agent, but not into deleting what it can't get to.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The step follows its skill file, reads the wish list, fetches the posts from the forum and writes the swaps file ("following a skill file Hana wrote, fetches the new posts ... writes the ones offering seeds on her wish list ... into a file called swaps"). All three files are in the sandbox, and the proposal changes nothing about the network, so it still reaches the forum.

### morning-approval

- **goal:** `c-judge-limits`
- **cases:** no-effect
- **type:** compound
- **tutor note:** What the limit does do: Hana approves every trade offer before it is sent, so a post that steered the agent into listing a bad trade, or an offer to the wrong poster, would be caught. It is a sound check on the swaps file, just not on anything the agent does to other files during its run.

#### a

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The deletion would happen during the evening run ("Each evening the swap agent ... reads each one"), while the agent reads the post, with the reach it already has, since nothing narrows it (no limit is stated). Hana's check comes the next morning and looks only at the swaps file, which needn't show anything about the deletion. The check comes after the harm has happened.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The agent's run is unchanged: it still reads its skill file and the wish list, fetches the posts and writes the swaps file. Only the morning sending waits on Hana.

### reader-model

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound
- **tutor note:** if asked afterward what the split leaves open, a hidden line can still skew which wish-list seeds the reading agent records for a post, so a poor trade could reach the swaps file; that is a different harm from the deletion, and the morning approval would catch it.

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The harm needs a hidden line in a post to steer an agent that can delete the records folder. Today the swap agent reads the posts ("reads each one"), which anyone can write ("Anyone can post on the forum."), and nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Hana can. Under this limit the agent that reads the posts has no files but the post and the wish list, no shell commands, no network and no logins, so a steered reading agent has nothing to delete; and its only way to hand anything on is the program that accepts seeds from her wish list, so no poster's words reach the swap agent. The swap agent keeps its reach to the records folder, but nothing is left in its context to tell it to use it.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The step writes the posts offering seeds on her wish list into the swaps file, with the wish-list seeds each one offers ("writes the ones offering seeds on her wish list ... into a file called swaps, with the wish-list seeds each one offers"). The records say, for each post, which wish-list seeds it offers, which is everything the swaps file needs, and the program that fetches the posts takes over the fetching.
