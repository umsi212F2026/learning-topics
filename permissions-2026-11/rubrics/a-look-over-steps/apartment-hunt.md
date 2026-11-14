Medium. An apartment tracker with three executors: the fetcher (a program) acquires listings from
a rentals site any landlord can post to, the rating agent assesses them, and the comparing agent
ranks the places Priya has visited. Priya's own visit step gets no question. The fetcher's and the
comparing agent's reach plainly match their steps; the rating agent runs with its default settings
in the home folder, against a step that uses one folder and two files. The rating agent reads the
listings, which landlords wrote; the comparing agent reads only what Priya typed. Each question
asks what the step does as described, not what could go wrong next or how to fix it.

### fetcher-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No, because it can reach only the rentals site, which it downloads from ("downloads the
  new listings from a rentals site"), and can change only the listings folder, which it writes
  into ("saves them in a folder called listings"). It reads no other file, runs no shell commands
  and uses no account ("It can change only the listings folder and read nothing else, it can't run
  shell commands, it can reach only the rentals site on the internet, and it uses no account").
  If asked what it can reach that its step doesn't need, the answer is nothing:
  the site is where it fetches from and the folder is where it saves.

### rating-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for 2.
- **tutor note:** Yes, because its step reads the new listings and Priya's list of needs and writes the
  shortlist ("reads each new listing and her own list of what she needs ... and writes a score and
  a one-line reason for each listing into a file called shortlist"). But it can read and change
  every file in her home folder, including her tax returns and the settings file with her bank
  login, run shell commands and reach the whole internet ("so it can read and change every file
  there, run shell commands and reach the whole internet"; "that folder also holds her tax returns
  and a settings file where her bank login is saved"). None of those is used by a step that works
  on saved listings, fetches nothing and runs no program.
  Follow-up's answer: every other file in her home folder (above all the tax
  returns and the bank login in the settings file), shell commands, and the internet.

### rating-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for 2.
- **tutor note:** Yes, because it reads three things: the skill file and the list of needs, which Priya
  wrote ("following a skill file Priya wrote"; "her own list of what she needs"), and each new
  listing, which a landlord wrote on a site any landlord can post to ("a rentals site any landlord
  can post to"). The fetcher saves the listings without changing them, so the agent reads the
  landlords' own words.
  Follow-up's answer: the listings, which any landlord can post to the rentals
  site.

### comparing-agent-reach

- **goal:** `c-spot-excess`
- **cases:** no-excess
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No, because its sandbox holds only the skill file it follows, the two files it reads (the
  visit notes and the budget) and the ranking file it writes, and it can change only the ranking
  file ("It runs in a sandbox holding only its skill file, the visit notes, the budget and the
  ranking file, where it can change only the ranking file"). Its step fetches nothing and runs no
  program, and it can't run shell commands, can't reach the internet and uses no account.
  If asked what it can reach that its step doesn't need, the answer is nothing:
  every file in the sandbox is one it follows, reads or writes.

### comparing-agent-context

- **goal:** `c-spot-injection`
- **cases:** owner-only
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for 1.
- **tutor note:** No, because it reads its skill file, the visit notes and the budget, and Priya wrote all
  three ("also following a skill file Priya wrote"; "types her own notes on each visit"; "the
  monthly budget she typed herself"). It never reads the listings, the shortlist, or anything copied
  from them.
  If asked where outside text comes from, the answer is that none reaches this
  agent. A learner who says yes may be thinking of the listings; ask which files the comparing agent
  reads.
