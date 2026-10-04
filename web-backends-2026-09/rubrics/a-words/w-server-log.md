# Rubric: server log

### q-define-server-log

- **type:** free
- **goal:** w-server-log
- **move:** DEFINE
- **answer:** what the server prints as it runs: a line or so for each request that arrives, saying
  what was asked and how it was answered, along with whatever else it reports while working. While
  you are developing it usually appears in the terminal the server was started in; a deployed server
  more often writes it to a file. Either way it is the server's own account of what it did, and it is
  out of the browser's sight.
- **credit:** full credit for saying it is what the server prints while it runs, as a record of the
  requests it handled and what happened, whether the answer places it in a terminal, a file or
  neither. Half credit for "a record of errors",
  which is only part of what it prints. Do not accept "server output" or "the logs", which name it
  again, and do not accept "what my app prints in the browser", which is the console.

### q-server-log-vs-console

- **type:** free
- **goal:** w-server-log
- **move:** DISTINGUISH
- **answer:** the console shows what the page printed and what went wrong inside the browser. It
  belongs to one tab, and it has no idea what the server did. The server log is what the server
  printed in its own terminal, away from the browser: which requests arrived, how they were answered,
  what it asked the database. Each one sees a half of the app that the other cannot.
- **credit:** full credit for placing both: the console is the browser's side, what the page printed
  in that tab, and the server log is the server's side, in its terminal or a log file, the requests it
  received and what it did with them. Half credit for one placed clearly and the other left vague. Do not accept "one is
  for errors and one is for everything", and do not accept an answer in which the console also shows
  what the server printed.

### q-console-empty-so-no-request

- **type:** free
- **goal:** w-server-log
- **move:** CATCH
- **answer:** the console shows what the page printed, not what the server did. A server that
  received the request prints its line in its own terminal, which the console never shows, so an
  empty console is no evidence either way. The server log, or the Network panel, is what would tell
  them.
- **credit:** full credit for saying the server prints where the console cannot see it, so an empty
  console says nothing about whether the request arrived. Naming the server's terminal or the Network
  panel as where to look instead is a good addition and is not required. Do not accept a different
  quibble as the error: that the console was filtered or needed clearing, that they should have
  reloaded first, or that they should just ask the agent.
