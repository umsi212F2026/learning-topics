# Rubric: .env file

What it names: a file of named values your app reads on your own machine. Nearest confusable: the
host's environment variables. Synonym: dotenv file; given as an answer, it names the thing again
and says nothing.

### q-env-file-vs-host-variables

- **goal:** `w-env-file`
- **move:** DISTINGUISH
- **answer:** The `.env` file is a file on your own machine that the backend reads when it runs
  there. The environment variables on Ropewalk's Settings page are what the deployed backend gets
  when it runs on Ropewalk. The `.env` file never reaches Ropewalk (it is kept out of the
  repository), so a value the deployed app needs has to be entered on Ropewalk as well.
- **credit:** full for the difference that matters: the `.env` file is where the app gets its
  values when it runs on your machine, the host's settings are where it gets them when deployed,
  and the file doesn't reach the host. Half for "one is local and one is on the host" with nothing
  on which running copy of the app each one feeds, or on the file not reaching the host. None for
  an incidental difference, such as that one is a file and the other a web page.

### q-catch-env-file-hides-secrets

- **goal:** `w-env-file`
- **move:** CATCH
- **answer:** A `.env` file is a plain file of named values; nothing about it hides or encrypts
  them. Once committed, the API key is in the repository, readable by anyone who can see it and
  kept in its history. A `.env` file is kept out of commits by listing it in `.gitignore`.
- **credit:** full for naming the actual error: a `.env` file hides nothing, so committing it puts
  the key in the repository, and it should be left out of commits. Half for "never commit a `.env`
  file" with nothing on the file itself hiding nothing. None for a different quibble, such as that
  the key should have a different name, or that the repository should be private.
