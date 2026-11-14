Medium. Three executors: the fetcher (a program), the rating agent and the planning agent. The
fetcher's reach matches its step exactly; the rating agent runs with default settings in Maya's
home folder against a step that uses one folder, one notes file and one output file; the planning
agent runs in a sandbox holding exactly what it reads and writes. The rating agent reads openings
that any camp can post; the planning agent reads only the skill file and two lists Maya types
herself. Booking is Maya's own step and gets no question. Each question asks what the step does as
described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 (No); none for 1. The step ("Downloads the new openings each morning
  from a camp listings site ... and saves them in the openings folder") uses everything the
  fetcher can reach: changing the openings folder, where it saves the openings, and the camp
  listings site, which it downloads from. It can read nothing else, run no shell commands and use
  no account.

### rating-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 (Yes); none for 2. Its step reads the openings folder and Maya's notes
  and writes the shortlist file ("Reads each new opening ... and writes a one-line verdict on each
  opening into the shortlist file"). But "it can read and change every file in your home folder,
  including your photos, your tax papers and the settings file where your email login is saved",
  which its step never uses; "it can reach the whole internet", though it works only on files
  already saved; and "it can run any" shell commands, though its step runs no named program.
- **tutor note:** follow-up answer: the photos, the tax papers, the settings file with the email
  login (and so the login itself), every other file in the home folder, the internet, and shell
  commands.

### rating-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 (Yes); none for 2. It reads the skill file and the notes, which Maya
  wrote, and "the openings, which camps put on the listings site", a site "where any camp can
  post". The openings reach it word for word, as the fetcher saved them.
- **tutor note:** follow-up answer: from the camp listings site, where any camp can post.

### planning-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 (No); none for 1. Its sandbox holds "only the skill file, the booked list,
  the trips list and the summer plan file": it reads the skill file and the two lists, and changes
  only the summer plan file, which it writes. It can't run shell commands, reach the internet or
  use an account.
- **tutor note:** a learner answering Yes may be counting the booked camps as having come from the
  listings site; that bears on context, not reach, and the step does read the booked list.

### planning-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 (No); none for 1. "It reads the skill file, the booked list and the trips
  list, all of which you wrote and only you can change." Maya types the booked list herself during
  Booking; the planning agent never reads the openings or the shortlist.
- **tutor note:** if they answer Yes because the camps first appeared on the listings site, ask
  who typed the booked list and whether anyone else can change it.
