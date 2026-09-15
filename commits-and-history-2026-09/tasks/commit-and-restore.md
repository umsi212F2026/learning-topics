# Commit and restore

**Intended goal:** `c-commit-recovery-point`, making use of commits.

Answer each question in one to three sentences. Nobody is asking for a git command anywhere here:
write what you would say to your agent, or what you would do, in your own words. Where a question
quotes an AI coding agent, imagine it is working in your own assignments repository.

### q-ask-restore-commit

Last Thursday your agent made a commit in your assignments repository with the message "Add rating
filter to task 1". Since then several files have changed and one has been deleted, and you want to
go back to exactly where things stood at that commit. Write the request you would send your agent.

### q-ask-commit-open-edits

You have spent an hour editing task1.py in your editor with your agent's help, and the version you
are happy with is on your screen right now. Say what you would do, and write the request you would
send your agent, so that this exact version ends up in a commit.

### q-restore-reply-vague

You asked your agent: "Put every file back to how it was at Thursday's commit, 'Add rating filter
to task 1'." It replies: "Done! I reverted your recent changes, so task1.py is back to normal."
Does that reply show your request was carried out? Say why or why not, and what you would open to
check.

### q-commit-reply-staged

You asked your agent to commit your saved work. It replies: "I've staged your changes to task1.py
and notes.md, and they're ready to go." Has your request been carried out? Say why, and what you
would say to the agent next.

### q-lost-after-restore

Your agent is about to put every file in your repository back to how it was at Tuesday's commit.
Which of these will you not be able to get back from the repository afterward?

1. Changes to task1.py that you saved this morning and never committed.
2. The contents task1.py had at Tuesday's commit.
3. A file that Tuesday's commit contains, which you deleted on Wednesday.
4. The version of notes.md from a commit made before Tuesday.


### q-good-moment-commit

You have just got task 1 producing a correct top-ten list, and you have saved every file. Next you
plan to have your agent try a completely different approach to task 2, which may not work. Is now a
good moment to ask for a commit? Say why.


