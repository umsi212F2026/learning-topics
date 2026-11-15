A seed swap forum watch, one step: the swap agent fetches posts anyone can write, reads them, and writes matching offers into the swaps file, running with nothing narrowing it. The harm comes from untrusted input steering the agent into using reach its step doesn't need: a hidden line in a post (untrusted input in its context, "a seed swap forum where anyone can post, reads each one") makes it delete the planting records folder, which it can change ("it can read and change all her files") but its step never touches. The deletion would happen during the evening run, before anything reaches the morning program. The step uses its skill file, the wish list, the forum on the internet, and the swaps file it writes, including a note on what each poster wants in return. Three proposals, one from each of the reading's groups: a sandbox (`sound-limit`, Medium), a person approving every trade offer (`no-effect`, Hard) and a program handling the posts (`stops-work`, Hard).

### sandbox

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. To delete the records folder the agent has to be able to change it ("it can read and change all her files"). The sandbox holds only the skill file, the wish list and the swaps file, so the records folder isn't in it, and a sandbox covers every command the agent runs, so no route reaches the folder. A hidden line can still steer the agent, but not into deleting what it can't get to.

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
- **tutor note:** Key: No. The deletion would happen during the evening run ("Each evening the swap agent ... reads each one"), while the agent reads the post, with the reach it already has ("it can read and change all her files"). Hana's check comes the next morning and looks only at the swaps file, which needn't show anything about the deletion. The check comes after the harm has happened.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The agent's run is unchanged: it still reads its skill file and the wish list, fetches the posts and writes the swaps file. Only the morning sending waits on Hana.

### seed-list-program

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The harm needs a hidden line in a post to reach the agent's context ("reads each one"). Under this limit the program fetches the posts and the agent sees only the program's own list of wish-list seeds, so no poster's words reach the agent and nothing in them can steer it. Its reach to the records folder is unchanged, but nothing is left to tell it to use it.

#### b

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The step writes, for each matching post, "a note on what each poster wants in return", which comes from what the poster wrote. A list of the seeds each post offers leaves that out, so the agent can no longer write the notes.
