A newsletter digest from Sofia's subscriptions, one step done by a program: the collector signs in to her email account with a token that can read, send and delete mail, and saves copies of the week's newsletters into a folder. The harm follows from reach the step doesn't need: the step only reads mail, but its token also deletes, so a mistake in its code can delete her inbox. The deletion happens in her email account, which the collector reaches over the internet. The step uses the token's permission to read mail, the network to reach her email account, and the newsletters folder it writes. Two proposals: a scoped token (`sound-limit`, Medium) and a sandbox with the network off (`stops-work`, Medium). The scenario carries no `no-effect` question.

### scoped-token

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. To delete her mail the collector has to use a secret that lets its holder delete, and the one it holds does ("lets its holder read, send and delete her mail"). A scoped token that only reads mail can't be used to delete anything, whatever its code does, and the scenario gives it no other email secret.

#### b

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. The step signs in, finds the newsletters and saves copies of them ("signs in to her email account, finds the week's newsletters, and saves a copy of each into a folder called newsletters"), which needs only reading her mail, and the token still reads it.

### sandbox-no-network

- **goal:** `c-judge-limits`
- **cases:** stops-work
- **type:** compound
- **tutor note:** if asked afterward what would let the step work, the agent's to work out; one answer is the same sandbox with only her email provider's site on its network allowlist, beside the scoped token.

#### a

- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Her mail is in her email account, which the collector reaches over the internet ("signs in to her email account"); today nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Sofia can, including reaching the internet. With the network turned off in a sandbox, which covers everything the program runs, it can't reach the account, so it can't delete anything there.

#### b

- **type:** mcq
- **answer:** 2
- **credit:** full for 2; none for 1.
- **tutor note:** Key: No. The step signs in to her email account to find the newsletters ("signs in to her email account, finds the week's newsletters"), which needs the network. With the network off it can't reach the account, so it can't copy any newsletters.
