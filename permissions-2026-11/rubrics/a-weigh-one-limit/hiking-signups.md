Medium, `stops-work`. A hiking group's sign-up step: an agent Kofi starts himself, with nothing narrowing it, reads posts from a message board anyone with an account can post to and writes a roster into his hikes folder. The harm comes from untrusted input steering the agent into reach its step doesn't need (the photos folder). The proposed sandbox plainly closes that route, and just as plainly makes read-only the folder the step writes into.

### sandbox-read-only

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound
- **tutor note:** if asked afterward what would let the step work, the agent's to work out; one answer is the same sandbox with only the skill file read-only, which leaves the roster writable and the photos still out of reach.

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. For the harm to happen, the agent would have to change files in the photos folder, which sits in his home folder outside the hikes folder ("His home folder holds the skill files, the hikes folder, a photos folder with pictures from every hike he has led"), and it can today because nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Kofi can. The sandbox holds only the skill file and the hikes folder, and a sandbox covers every command the agent runs, so the photos folder is out of reach whatever a hidden line says.

#### b

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The step writes the roster into the hikes folder ("writes the names ... into a file called roster in his hikes folder"), and the proposal makes that folder read-only, so the agent can no longer write it. Everything else it uses stays: it can still read the skill file and fetch the posts, since the proposal leaves the network as it was.
