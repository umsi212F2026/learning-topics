# Data retention

### vs-training

Two model companies publish policies for what happens to the prompts sent to their APIs. Company X keeps each prompt for 3 days and then deletes it, and may use prompts to train its models during that time. Company Y keeps each prompt for 30 days and then deletes it, and never uses prompts to train its models.

Which company has the shorter data retention?

1. Company X
2. Company Y
3. About the same

### catch-pick

A notes service sends each user's notes to a model company's API. The company's policy says it keeps what is sent to its API for 7 days and then deletes it, and that it does not train its models on it.

Which of these uses the term data retention correctly?

1. With 7-day data retention, the service can ask the company for a lost note back within a week.
2. With 7-day data retention, the company trains its models on the notes for a week.
3. With 7-day data retention, the company holds on to the notes for a week before deleting them.
4. With retention as short as 7 days, the company never really sees the users' notes.

### vs-backup

A notes service sends each user's notes to a model company's API to make summaries. The model company keeps whatever is sent to its API for 30 days and then deletes it. Separately, each night the service copies every user's notes to a storage company, so it can restore them if its own database fails.

Which of these states the difference between the model company's data retention and the service's backup?

1. Retention is the service's copy for restoring notes; the backup is how long the company keeps them.
2. Both are copies kept so the notes can be restored if the service's database fails.
3. One is held by a model company, one by a storage company, but both are for restoring notes.
4. The backup is kept to restore notes; retention is how long the company keeps them before deleting.

### catch-free

Sam pastes a long document into a model company's chat app and, twenty messages later, asks about its first page. The model's answer gets the first page wrong. Sam says: "This company must have short data retention: the model has already forgotten what I sent."

What is wrong with how Sam uses the term data retention? Answer in one or two sentences.
