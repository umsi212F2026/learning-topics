# Rubric: headless browser

### q-define-headless-browser

- **type:** free
- **goal:** w-headless-browser
- **move:** DEFINE
- **answer:** a headless browser is a real browser with no window, driven by a program rather than
  by a person. Your agent starts one, through a tool such as Playwright or Puppeteer, to open your
  app's address, click things, read what is on the page and take screenshots, so that it can see
  for itself what the app does.
- **credit:** full credit for saying it is a browser with no visible window that a program, the
  agent, drives, used to load a page and look at it. Half credit for "a browser the agent uses"
  with nothing about there being no window or about it being driven by a program. Do not accept "a
  way for the agent to see your browser tab", which is the confusion the word is against, and do
  not accept the dev server or a screen reader.

### q-headless-vs-your-browser

- **type:** free
- **goal:** w-headless-browser
- **move:** DISTINGUISH
- **answer:** the browser on your laptop is yours: it has a window you look at, your tabs, and
  whatever you are signed in to. The agent's headless browser is a separate browser it starts and
  drives itself, with no window and none of your tabs or sessions. It can open the same address you
  can, but it cannot see what is in your tab, which is why the agent still has to ask you what you
  are seeing.
- **credit:** full credit for both: the headless one is a separate browser the agent starts and
  drives with no window, and it does not have your tabs, your session or your view of the page.
  Half credit for "one has no window" alone. Do not accept "it is a fake browser" or "it cannot run
  the app properly", and do not accept an answer in which the agent's browser is a way of watching
  your screen.

### q-no-headless-browser-here

- **type:** mcq
- **goal:** w-headless-browser
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 makes it a problem only a human could see; the agent simply cannot open the page in
  this session. 3 blames the dev server, which the message says nothing about. 4 has the agent
  seeing your tab, which is the thing a headless browser is not.
