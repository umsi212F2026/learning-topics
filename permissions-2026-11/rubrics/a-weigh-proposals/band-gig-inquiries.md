The harm's route: for the login to be sent, the booking agent has to read the settings file in
Rosa's home folder, where the login is saved, and reach the internet to send it to a web address.
Both happen during the morning run, before Rosa reads any draft. The agent can do both, because it
runs as Rosa and can read every file there and reach the internet (fifth sentence), and it reads
messages anyone can write through the contact form (second and third sentences). Rosa's reading of
every draft comes after the run (fourth sentence), so it does not stop a login sent during it.

What the step uses: the skill file, the download program, which fetches the messages from the band's
website over the internet and saves them in the inquiries folder (second sentence), the messages
there, the calendar file it checks dates against, and the replies file it writes into (third
sentence). The step never uses the email login: Rosa sends the replies herself.

q1 (harness permission settings, `no-effect`, Hard). Part a, No: the harness checks only what the
agent asks it to do, and the harness lets the agent run shell commands without asking (sixth
sentence). A command the agent runs can still read the settings file and reach the internet, so the
route is as it was. Part b, Yes: the step never reads the settings file, so it still runs the
download program, reads the inquiries and the calendar, and writes the replies.

q2 (sandbox, `stops-work`, Medium). Part a, Yes: with the network off, the agent and every command
it runs can send nothing to any web address, which cuts the route. Part b, No: the download program
fetches the messages from the band's website (second sentence), and in the sandbox it can't reach
the internet, so there are no new messages to answer.

q3 (separate user, `sound-limit`, Medium). Part a, Yes: the operating system lets the separate user
reach only what it has been given, so neither the agent nor any command it runs can read the
settings file with the login, and the agent can't send what it can't read. Part b, Yes: the agent
still has the skill file, the download program, the inquiries folder, the calendar and the replies
file, and the internet stays as the paragraph describes it, so the download program still fetches
the messages.

### q1

- **goal:** `c-judge-limits`
- **cases:** no-effect
- **type:** compound
- **tutor note:** afterward, say the limit isn't useless: it keeps the agent itself from asking the
  harness to open the settings file, so a hidden line that steers the agent only that far gets
  refused. It just doesn't stop a shell command, which the harness lets run without asking.

#### a

- **type:** mcq
- **answer:** 2

#### b

- **type:** mcq
- **answer:** 1

### q2

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2

### q3

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 1
