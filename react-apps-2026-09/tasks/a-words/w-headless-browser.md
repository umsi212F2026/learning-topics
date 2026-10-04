# headless browser

### q-define-headless-browser

Your agent says it will check the page in a headless browser. Say what a headless browser is, in
your own words.

### q-headless-vs-your-browser

What is the difference between the headless browser your agent uses and the browser you have open
on your laptop?

### q-no-headless-browser-here

Your agent says: "I don't have a headless browser in this session, so I can't look at the page
myself. Could you open http://localhost:5173, click Add, and tell me what you see?" Which of these
does that tell you?

1. The agent cannot open your app for itself here, so what it knows about the problem is whatever you report back.
2. The app is broken in a way that only a person could see.
3. Your dev server is not running, which is why the agent cannot reach the page.
4. The agent can see your browser tab already and wants you to confirm what is in it.
