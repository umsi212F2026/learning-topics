# Rubric: .gitignore

What it names: the list of files git leaves out of every commit. Nearest confusable: removing a
file from the repository.

### q-gitignore-vs-removing

- **goal:** `w-gitignore`
- **move:** DISTINGUISH
- **answer:** Listing a file in `.gitignore` stops git adding it to commits when it isn't already
  in the repository; it does nothing to a file that has already been committed, which stays in
  the repository. Removing a file from the repository takes an already committed file out of the
  commits from then on (its old commits still hold it). So `.gitignore` keeps a file from getting
  in, and removing takes out one that is already in.
- **credit:** full for the difference that matters: `.gitignore` only keeps a file out of commits
  it isn't in yet, and does nothing to one already committed, which has to be removed. Half for
  "`.gitignore` stops it being committed, removing deletes it" with nothing on `.gitignore` doing
  nothing to a file already in the repository. None for an incidental difference, such as that
  removing a file is a command and `.gitignore` is a file.
- **tutor note:** a learner may say removing a file deletes it from their disk too. That depends
  on how it is removed and is not the difference that matters; ask what `.gitignore` does to a
  `.env` file committed last week.

### q-catch-gitignore-hides-on-github

- **goal:** `w-gitignore`
- **move:** CATCH
- **answer:** `.gitignore` doesn't hide a file on GitHub; it keeps the file out of every commit, so
  it never reaches GitHub at all. The host deploys from the repository on GitHub, so it doesn't
  get the file either; values the deployed app needs have to be given to the host another way.
- **credit:** full for naming the actual error: an ignored file is left out of commits altogether,
  so it isn't on GitHub for anyone, the host included. Half for "it isn't on GitHub at all" with
  nothing on the host not getting it either, or the reverse. None for a different quibble, such as
  that a private repository would hide it.
