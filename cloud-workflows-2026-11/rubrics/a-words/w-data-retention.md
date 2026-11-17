# Rubric: Data retention

If the learner misses a question here, set a DEFINE or INTERPRET move for data retention live, as help (it is recorded as helped and doesn't count), then come back to a production question.

Data retention is how long a company keeps the prompts and other data sent to it before deleting them. A retention policy says how long. It is a separate question from training on user data, which is whether the company may use what was sent to train its models: a company can keep data briefly and train on it, or keep it long and never train on it. Nor is retention a backup: a backup is a copy kept so data can be restored, while retained prompts are kept for the company's own purposes and are not there to be handed back. And short retention still means the company saw the data; it only limits how long it keeps it.

### vs-training

- **goal:** `w-data-retention`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. Company X keeps prompts 3 days and Company Y keeps them 30, so X's retention is shorter, whatever each does about training. Choice 2 reads data retention as whether the company trains on prompts, which is where Y does better. Choice 3 treats the two policies as even because each is better on one thing.
- **tutor note:** a learner who picks 2 or 3 is weighing training into retention; ask how long each company keeps a prompt before deleting it.

### catch-pick

- **goal:** `w-data-retention`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. A 7-day retention policy means the company keeps what was sent for 7 days and then deletes it. Choice 1 reads retention as a backup: retained prompts are not kept for users to get back, and the service would keep its own copy for that. Choice 2 reads retention as training on user data, and the policy says the company does not train on what is sent. Choice 4 stretches the term: retention says how long the company keeps the notes, and a company that keeps them a week has still seen them.

### vs-backup

- **goal:** `w-data-retention`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only. The nightly copy is a backup, kept so the service can restore the notes. The 30 days is the model company's data retention: how long it keeps what was sent before deleting it, for its own purposes, not to hand back. Choice 1 swaps the two. Choice 2 reads retention as a backup. Choice 3 names an incidental difference, who holds each copy, and keeps the backup reading of retention.
- **tutor note:** a learner who picks 2 or 3 may think retained prompts are there for the user's benefit; ask whether the service could get a lost note back from the model company.

### catch-pick-2

- **goal:** `w-data-retention`
- **move:** CATCH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. A 30-day retention policy means the company keeps what was sent for 30 days and then deletes it. Choice 1 reads retention as what the model remembers during a conversation: the company still has Sam's document stored, so the wrong answer says nothing about its retention. Choice 3 reads retention as a backup: retained prompts are kept for the company's own purposes, not to be handed back. Choice 4 reads retention as training on user data, and the policy says the company does not train on what is sent.
- **tutor note:** a learner who picks 1 may be reading retention as remembering; ask where the document is kept and for how long, apart from whatever the model does with it.
