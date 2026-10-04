# Rubric: environment variable

If the learner misses a question here, set a DEFINE or INTERPRET move for environment variable
live, as help (it is recorded as helped and doesn't count), then come back to a production
question.

An environment variable is a named value handed to the running program from outside its code: the
host's settings page, or a `.env` file the program loads when it starts, and the code only reads
it by name (`process.env.FRONTEND_URL`). Its other name is env var, and that, given as an answer,
says nothing. The confusable is a setting written into the code, such as
`const frontendUrl = "http://localhost:5173";`, which is part of the source and is the same
wherever the code goes.

### q1

- **goal:** `w-env-var`
- **move:** DISTINGUISH
- **answer:** An environment variable's value comes from outside the code, handed to the program
  by wherever it runs, so the same code can get `http://localhost:5173` on a laptop and the real
  address on the host. A setting written into the code is part of the source: it is the same
  everywhere the code goes, and changing it means editing the code.
- **credit:** full for naming that the environment variable's value is handed in from outside the
  code (by the place it runs), while the written-in setting is part of the code itself. Half for
  a consequence without its cause, such as "the environment variable can be different in each
  place" or "it's easier to change", with nothing on where its value comes from. None for an
  incidental difference, such as capital letters, the `process.env` syntax, or that one is
  "hidden".

### q2

- **goal:** `w-env-var`
- **move:** CATCH
- **answer:** That line isn't an environment variable. It is a setting written into the code, in
  `server.js` itself; an environment variable's value comes from outside the code, and the code
  would only read it, as `process.env.DB_PASSWORD`.
- **credit:** full for naming that the value is written into the code, so it is not an environment
  variable, which would come from outside the code. Half for saying it isn't an environment
  variable without saying why. None for a different quibble on its own, such as that a password
  shouldn't be in the code or that `hunter2` is a weak password: true, but not what's wrong with
  the use of the word.
- **tutor note:** if they say only "never put a password in your code", ask whether the line, as
  written, is an environment variable.

### q3

- **goal:** `w-env-var`
- **move:** CATCH
- **answer:** An environment variable is handed to the program from outside its code, so changing
  it on the host needs no edit to the code and no push. The program has to be restarted or
  redeployed to pick up the new value, but the code stays as it is.
- **credit:** full for naming that the value lives outside the code, so changing it needs no code
  edit (a restart or redeploy is fine to mention). Half for saying no code edit is needed without
  saying why. None for a different quibble, such as how to push, or that a redeploy happens
  automatically.
- **tutor note:** a React frontend built with Vite reads its environment variables when it is
  built, so it needs a rebuild to see a change; if they raise that, it is still no code edit.
