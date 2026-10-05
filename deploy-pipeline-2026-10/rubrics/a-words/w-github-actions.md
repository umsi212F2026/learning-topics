# Rubric: GitHub Actions

What it names: GitHub running jobs described in a file in the repository when something happens to
it. Nearest confusables: the course's skill file for updating course repos (the `update` skill);
auto-deploy.

### q-actions-vs-update-skill

- **goal:** `w-github-actions`
- **move:** DISTINGUISH
- **answer:** An Actions workflow is a script: GitHub runs its steps exactly as written, on its own
  machines, when something happens to the repository, such as a push, with nobody asking. The
  `update` skill is instructions in plain language that your agent reads and interprets, on your
  machine, when you ask it to. What differs is what kind of file each is, who runs it, where, and
  what sets it off.
- **credit:** full for either difference that matters: a workflow is a script that runs its steps
  exactly, while a skill is instructions an agent interprets; or a workflow is run by GitHub when
  something happens to the repository, while the skill is followed by your agent on your machine
  when you ask. Half for naming only where each runs, or only what sets each off. None for an
  incidental difference, such as the file's format or the folder it is kept in.

### q-actions-vs-auto-deploy

- **goal:** `w-github-actions`
- **move:** DISTINGUISH
- **answer:** Auto-deploy is the host redeploying the app by itself whenever the repository
  changes. GitHub Actions is GitHub running whatever jobs a workflow file in the repository
  describes when something happens to it: those jobs might run the tests, might deploy the app by
  running the host's deploy command, or might do neither. Auto-deploy is done by the host and only
  ever deploys; Actions is done by GitHub and does what the file says.
- **credit:** full for the difference that matters: auto-deploy is the host deploying on its own,
  while Actions is GitHub running the jobs a file in the repository describes, which need not
  deploy anything. Half for "one is done by the host and the other by GitHub" with nothing on
  Actions running whatever the file describes. None for "Actions is the same thing but on
  GitHub", or an incidental difference such as which one is free.

### q-catch-actions-is-a-switch

- **goal:** `w-github-actions`
- **move:** CATCH
- **answer:** Actions runs only the jobs described in a workflow file in the repository. With no
  such file, nothing runs on a push; GitHub doesn't know how to test the app until a file says
  what to run and when.
- **credit:** full for naming the actual error: the jobs, testing included, come from a file in the
  repository, so nothing is tested until a workflow file describes it. Half for "you need a
  workflow file" with nothing on that file being what decides what runs. None for a different
  quibble, such as that the tests might take a long time, or that Actions has a monthly limit.
- **tutor note:** a learner may say GitHub offers ready-made workflows to pick from. That is right,
  and picking one adds a file to the repository; ask where the steps it runs are written down.
