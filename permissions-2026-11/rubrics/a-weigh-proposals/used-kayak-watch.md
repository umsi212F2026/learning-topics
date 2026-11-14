The harm follows from untrusted input steering the agent into using reach its step doesn't need.
Its route: a hidden line in a listing reaches the agent's context (it reads each listing, and
anyone can post one); the agent can read the settings file holding her email login (it can read
every file in her home folder); and it can send the login out (it can reach the internet and run
shell commands). All of this would happen during the evening run, before anyone sees the kayak
list. What the step uses: the skill file and the listings it reads, the internet to fetch the
listings, the kayaks folder to write the kayak list, and the sellers' own words about each kayak's
condition, which its notes report. It uses no account and needs nothing else in her home folder.

Cases in this scenario, in file order: `sound-limit` (Medium), `no-effect` (Medium), `stops-work`
(Hard).

### sandbox-folder

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **tutor note:** the settings file with the login is outside the kayaks folder, and the sandbox
  covers every command the agent runs, so it can't read the login and can't send what it can't
  read, whatever a listing says.

#### b

- **type:** mcq
- **answer:** 1
- **tutor note:** the skill file and the kayak list are both in the kayaks folder, and the proposal
  changes nothing about the internet, so it still fetches and reads the listings and writes the
  list with its notes.

### read-only-home

- **goal:** `c-judge-limits`
- **cases:** no-effect
- **type:** compound
- **tutor note:** afterward, say what this limit does do: a steered or mistaken agent could no
  longer change or delete files elsewhere in her home folder. It just isn't aimed at sending the
  login, which needs only reading and the internet.

#### a

- **type:** mcq
- **answer:** 2
- **tutor note:** read-only still lets the agent read the settings file, and the internet is
  unchanged, so a hidden line could still make it send the login. The harm never changes a file.

#### b

- **type:** mcq
- **answer:** 1
- **tutor note:** it still reads the skill file, fetches the listings and writes the kayak list in
  the kayaks folder, which stays changeable.

### numbers-only

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **tutor note:** the agent would read only three numbers the program worked out, never a seller's
  words, so no hidden line reaches its context to steer it into sending the login. Its reach is
  unchanged, but nothing in what it reads can tell it to use that reach.

#### b

- **type:** mcq
- **answer:** 2
- **tutor note:** its note on each kayak says what the seller wrote about its condition, and it
  would never see those words. It could still pick kayaks by length and price, but not write the
  notes the step exists to write.
