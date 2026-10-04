# Key: judge what an agent asks you to do with a value

**For the tutor only.** Never show this file to the learner. It goes with
`judge-agent-requests.md`.

Every pair has one message to decline and one to go along with, in no fixed order.
For a decline, a complete answer has three parts: don't paste it or let it be written into code;
put it straight into the host's settings yourself and tell the agent it's there; and the reasons.
Both reasons apply to every message that would route a secret through the agent, even one that
only asks for a paste: the chat is kept and can be shared, and an agent that holds the secret can
write it into a file, which can be committed.

| item | go along? | what to do instead | what decides it |
| ---- | --------- | ------------------ | --------------- |
| A1 | no | Add `DATABASE_URL` (or whatever the agent calls it) in Kettle's settings, pasting the string from Larder, and tell the agent it's done. | The connection string holds the database's password. Pasted here, it stays in the chat's record. |
| A2 | yes | | A server's address is public: anyone who uses the app sees it. The near-miss is declining it because it looks like a "setting". |
| B1 | yes | | The agent asks only for the setting's name to be added on the host, and the value goes from one dashboard to another without passing through the chat or the code. This is the pattern to copy. The near-miss is refusing because the message mentions a connection string. |
| B2 | no | As for A1, and say no to the file: the value belongs in Kettle's settings, not in `server/config.js`. | Two problems at once: the chat, and a file that will be committed. "Works the same on your laptop" is the lure. |
| C1 | no | Don't paste the page. Add the string in Kettle's settings and tell the agent it's there. Describing its shape without its values (for example, that it starts `postgres://`) is a fine extra, but not a replacement for that. | The Connect page shows the password. Asking to "check the format" is a reasonable-sounding way to get the whole thing. |
| C2 | yes | | The frontend's address is public, like A2. |

**Order to serve.** Pair A first: it is the plainest contrast. Then B, whose secret-free message
mentions a connection string, and C, whose secret request sounds like debugging.
