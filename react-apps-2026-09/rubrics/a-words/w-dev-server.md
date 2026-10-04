# Rubric: dev server

### q-define-dev-server

- **type:** free
- **goal:** w-dev-server
- **move:** DEFINE
- **answer:** the dev server is the program `npm run dev` starts and leaves running in that
  terminal. It serves your project to the browser at a local address such as
  http://localhost:5173 while you work on it, and it watches your files so that saved changes reach
  the open page. Stop it and that address stops answering.
- **credit:** full credit for saying it is what serves your project to your browser at a local
  address while you are working, and keeps running until it is stopped. Full credit for "the thing
  running in the terminal that makes localhost:5173 work". No credit for "the development server",
  which names it again. Do not accept "the terminal", "npm", or "where the app is hosted online".

### q-closed-terminal-still-up

- **type:** free
- **goal:** w-dev-server
- **move:** CATCH
- **answer:** the tab is showing a page the browser already has; nothing is serving it at this
  moment. With the dev server stopped, a reload has nothing to answer it and the page fails to
  load, and saved changes stop reaching the tab. The dev server is needed for as long as you are
  using the app, not just to start it.
- **credit:** full credit for saying the page on screen is what the browser already loaded, and
  that reloading now would fail because nothing is serving the app. Full credit for the hot reload
  half on its own: with the server stopped, saved changes no longer reach the page. Do not accept a
  different quibble as the error: that they should have stopped it with Ctrl+C, that the app is now
  in production, or that the browser has saved the whole app for good.

### q-dev-server-other-port

- **type:** free
- **goal:** w-dev-server
- **move:** INTERPRET
- **answer:** another dev server was already running on 5173, from an earlier run or another copy
  of the project, so this one took the next free port. The address for the project the agent just
  started is 5174, and whatever is at 5173 is a different server, so anything you check in a tab
  still pointing at 5173 tells you nothing about this app.
- **credit:** full credit for both: this project is now at 5174, and 5173 is something else already
  running, so looking there would be looking at the wrong app. Half credit for the change of
  address alone. No credit for reading it as the app being broken, as the agent having failed to
  start anything, or as the two addresses being two views of the same app.
