# Data retention

### vs-training

A model company's policy for its API says two things: it keeps each prompt for 3 days and then deletes it, and it may use prompts to train its models during that time.

Which part of the policy describes its data retention?

1. Keeping each prompt for 3 days, then deleting it
2. Using prompts to train its models
3. Both
4. Neither

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

### catch-pick-2

Sam pastes a long document into a model company's chat app and, twenty messages later, asks about its first page. The model's answer gets the first page wrong. The company's policy says it keeps what is sent to it for 30 days and then deletes it, and that it does not train its models on it.

Which of these uses the term data retention correctly?

1. The model got the first page wrong because the company's data retention ran out.
2. With 30-day data retention, the company keeps Sam's document a month, then deletes it.
3. With 30-day data retention, Sam can get the document back from the company if he loses it.
4. With 30-day data retention, the company may use Sam's chat session to improve its models during those 30 days.
