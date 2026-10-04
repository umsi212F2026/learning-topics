# Rubric: repository

### q-repository-vs-folder

- **type:** free
- **goal:** w-repository
- **move:** DISTINGUISH
- **answer:** an ordinary folder is only a place where files sit, holding their current contents
  and nothing more. A repository is a folder git is keeping track of: git keeps a record of the
  files inside it (the history of commits), so an earlier state of those files can be looked at or
  got back. In a folder that is not a repository, a file that is overwritten or deleted has no
  record to come back from.
- **credit:** full credit for saying that a repository comes with a record or history of what is
  inside it (or that git keeps track of changes to what is inside it), so earlier versions can be
  seen or got back. Also full credit for "git tracks the files in a repository" with no mention of a
  record, a history, or getting anything back; full credit also for "a repository has a hidden .git
  folder". Do not accept incidental differences: that a repository is on GitHub, that it holds code
  rather than documents, that it is shared, or that it is bigger.

### q-scratch-folder-tracked

- **type:** free
- **goal:** w-repository
- **move:** CATCH
- **answer:** the Desktop folder is outside the repository, and git only keeps track of what is
  inside a repository's boundary. Being a copy of a tracked file does not make the copy tracked:
  nothing done to it will be in the repository's commits or can be restored from them.
- **credit:** full credit for saying the copy is outside the repository (outside what git is keeping
  track of), so git is not tracking it. Half credit for "git doesn't track copies" with no reason
  given, because the reason is where the copy is, not that it is a copy. Do not accept a different
  quibble as the error: that they should have committed first, that copying files is bad practice,
  that they need to stage the file, or that the Desktop is a messy place to work.

### q-laptop-copy-folder

- **type:** free
- **goal:** w-repository
- **move:** CATCH
- **answer:** the copy on the laptop is itself a repository, not just a folder of files. It carries
  the history of commits, commits are made there in the first place, and earlier states can be
  restored from it without going to GitHub.
- **credit:** full credit for saying the laptop copy is a repository in its own right, with the
  commits (the history) in it. Full credit for "commits are made on your laptop first" without
  saying the laptop copy holds the history. Do not accept a different quibble as the error: that
  they should push more often, that GitHub is a backup, or that "real" is the wrong word. Do not
  accept "the GitHub one is the copy and the laptop one is the real one", which only reverses the
  mistake: both are repositories.

### q-outside-repo-report

- **type:** free
- **goal:** w-repository
- **move:** INTERPRET
- **answer:** ps1-notes.txt sits outside the boundary of what git is keeping track of for the
  assignments repository, so it cannot go into a commit and git has no record of it. That rules
  out getting an earlier version of ps1-notes.txt back from the repository's history, and rules
  out a restore of the repository protecting or bringing back that file.
- **credit:** full credit needs both halves: (a) the file is not inside the repository, so git has
  no record of it and cannot commit it; (b) one thing that not having it in the commit rules out, such as no earlier version of
  it can come back from the history, a restore will not touch or protect it, the changes cannot be
  pushed to GitHub, or the file is not shared with collaborators. Half credit for
  either half alone. No credit for reading "outside the repo" as the agent lacking permission, the
  file being broken, or the file having been deleted.
