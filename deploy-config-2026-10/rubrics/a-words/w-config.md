# Rubric: config

If the learner misses a question here, set a DEFINE or INTERPRET move for config live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

Config is the values that differ depending on where the app runs: on localhost the frontend calls
`http://localhost:3000` and the backend reaches a local database, while deployed they use the
hosts' addresses and the database host's connection string. The code is the same in both places;
the config is what changes. Its other names are configuration and settings, and neither, given as
an answer, says what it is. The confusable is code: the logic of the app, which doesn't change
with where it runs.

### q1

- **goal:** `w-config`
- **move:** DISTINGUISH
- **answer:** The code is the app's logic, and it is the same wherever the app runs. The config is
  the values that change depending on where it runs, such as the backend's address or the
  database's connection details, so the same code can run on a laptop and on a host.
- **credit:** full for naming that config is what differs from one place the app runs to another,
  while the code stays the same across them. Half for a difference that points the right way but
  leaves out where the app runs, such as "config is values, code is instructions" or "config is
  what you can change without editing the code". None for an incidental difference, such as the
  file it lives in, its format, or that config is shorter.
- **tutor note:** if they say "config is the stuff you change often", ask what a value would have
  to change with to count as config.

### q2

- **goal:** `w-config`
- **move:** CATCH
- **answer:** The app has config on the laptop too: its values there are the localhost ones (the
  backend at `http://localhost:3000`, a local database). Config is the values that differ by
  where the app runs, so every place it runs has its own, and deploying swaps the laptop's values
  for the host's.
- **credit:** full for naming that the laptop has config of its own, its localhost values, because
  config is what differs between the places the app runs. Half for saying the app has config on
  the laptop without saying what it is there or why. None for a different quibble, such as that
  config matters more once deployed, or that secrets only appear in production.

### q3

- **goal:** `w-config`
- **move:** CATCH
- **answer:** Changing over time doesn't make something config. Config is the values that differ
  depending on where the app runs; formatting a date is logic, the same on a laptop and on the
  host, so it is code, even if the team changes it later.
- **credit:** full for naming that config is defined by differing with where the app runs, not by
  being likely to change, so the date formatting, which is the same everywhere, is code. Half for
  saying it is code, not config, without saying what would make something config. None for a
  different quibble, such as that a function can't go in a config file, or that the team should
  decide the format now.
- **tutor note:** if they say "a function can't be config", ask whether a single value, such as a
  date format string the same in every place, would be config.
