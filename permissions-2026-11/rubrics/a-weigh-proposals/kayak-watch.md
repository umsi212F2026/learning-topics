A used kayak watch, one step: the kayak agent runs a download program to fetch listings into the kayaks folder, reads them, writes picks and deletes old listings there, with nothing narrowing it (no limit is stated) and its harness set to let it run shell commands without asking. The harm follows from reach the step doesn't need: a command the agent runs while clearing out old listings deletes the photos folder, which the step never touches but which the agent can change, since by the reading's rule it can do whatever Zainab can. The step uses its skill file, the download program (and through it the marketplace on the internet), and the kayaks folder, which it both reads and changes. Three proposals: a harness file limit the step gets around (`no-effect`, Hard), a sandbox that leaves out the download program (`stops-work`, Hard) and a separate user (`sound-limit`, Medium).

### harness-files

- **goal:** `c-judge-limits`
- **cases:** no-effect
- **type:** compound
- **tutor note:** What the limit does do: file changes the agent asks the harness to make itself are kept to the kayaks folder, so a slip in one of its own edits can't touch the photos. It isn't useless, only not aimed at a harm that goes through a command.

#### a

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The harm goes through a command ("the agent runs a command that deletes her photos folder as well"), and Zainab has set the harness to let it run shell commands without asking ("Zainab has set its harness's permission settings to let it run shell commands without asking."). The harness checks only what the agent asks it to do; a command it lets run can do whatever Zainab could, by the reading's rule that an executor can do whatever its user can unless something narrows it, so the command can still delete the photos folder.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The step writes picks into the kayaks folder and deletes old listings from it ("writes the promising ones into a file called picks in the same folder, and deletes the listings more than a week old from the folder"), all inside the kayaks folder, and it still runs the download program, since shell commands still run without asking.

### sandbox

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound
- **tutor note:** if asked afterward what would let the step work, the agent's to work out; one answer is the same sandbox with the download program in it too.

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. For the harm to happen, a command the agent runs has to be able to change the photos folder, which it can today because nothing narrows it, so by the reading's rule it can do whatever Zainab can. The sandbox holds only the skill file and the kayaks folder, and a sandbox covers every command the agent runs, so no command it runs can reach the photos folder.

#### b

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The step fetches the listings by running the download program ("runs a download program she wrote to fetch the new listings"), which sits in her home folder ("Her home folder holds the skill file, the download program, the kayaks folder ..."). The sandbox leaves it out, so the agent can no longer fetch new listings.

### separate-user

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The harm needs a command the agent runs to change the photos folder, which it can today because nothing narrows it, so by the reading's rule it can do whatever Zainab can. A separate user given only the skill file, the download program and the kayaks folder has not been given the photos folder, and the operating system holds every command the agent runs to what that user can do, so no command it runs can delete the photos.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The step follows its skill file, runs the download program and reads, writes and deletes files in the kayaks folder ("following a skill file Zainab wrote, runs a download program she wrote ... into her kayaks folder ... writes ... picks in the same folder, and deletes the listings more than a week old"). The separate user has all three, and the proposal changes nothing about the network, so the download program still reaches the marketplace.
