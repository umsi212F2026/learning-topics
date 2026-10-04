# Rubric: browser console

### q-define-browser-console

- **type:** free
- **goal:** w-browser-console
- **move:** DEFINE
- **answer:** the browser console is a panel in the browser's developer tools, belonging to one
  tab, where the page reports what happened inside it: errors and warnings from the running app
  turn up there, and you can type a line for that page to run. Someone using the app never sees it
  unless they open the developer tools.
- **credit:** full credit for saying it is where the page's own errors and messages appear, inside
  the browser's developer tools, out of an ordinary user's sight. Full credit for adding that you
  can run a line there. No credit for "the JavaScript console" or "the DevTools console", which
  name it again. Do not accept "the terminal" or "where npm prints things", and do not accept
  "where the errors are" with nothing about it being in the browser.

### q-console-vs-terminal

- **type:** free
- **goal:** w-browser-console
- **move:** DISTINGUISH
- **answer:** the terminal is where the dev server is running, and it reports what that program is
  doing on your laptop: the address it is serving on, files it noticed, its own failures. The
  console belongs to one browser tab and reports what happened inside the page while it ran, which
  is where an error thrown while the app was drawing shows up. They are two different places, and a
  message in one need not appear in the other.
- **credit:** full credit for placing both: the terminal is the dev server's own output on your
  machine, and the console is one tab's report of what happened in the running page. Half credit
  for one placed correctly and the other left vague. Do not accept "one is in the browser and one
  is not" with nothing about what each reports, and do not accept an answer that makes them two
  views of the same messages.

### q-pasted-terminal-for-console

- **type:** free
- **goal:** w-browser-console
- **move:** CATCH
- **answer:** what they copied is the dev server's output, not the console. The console is in the
  browser's developer tools on the app's own tab, and an error thrown while the page was being
  drawn is reported there, which is why a page that goes white often has its only explanation in
  the console and nothing at all in the terminal.
- **credit:** full credit for saying these are two different places, and that the console is in the
  browser's developer tools on the app's tab, so the terminal's output is not what was asked for.
  Do not accept a different quibble as the error: that a screenshot would have been better, that
  they should have reloaded first, or that the agent's request was unclear.
