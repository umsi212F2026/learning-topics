The secret in this scenario is the Larder connection string, which includes the database's
password. A message should be declined when it would put that string in the chat or let the agent
write it into a file; it should be gone along with otherwise. The frontend's and the backend's
addresses are public: anyone who uses the app sees them. Saying what to do instead is welcome but
not judged here.

### q1

- **answer:** No. It asks for the connection string to be pasted into the chat.
- **credit:** full for declining. None for going along with it.

### q2

- **answer:** Yes. A server's address is public, so it can go in the chat.
- **credit:** full for going along with it. None for declining.
- **tutor note:** the near-miss is declining because it looks like a setting.

### q3

- **goal:** `c-judge-secret-request`
- **answer:** Yes. The agent only names the setting; the connection string goes from Larder's
  dashboard to Kettle's without passing through the chat or any file.
- **credit:** full for going along with it. None for declining.
- **tutor note:** the near-miss is declining because the message mentions a connection string. Ask
  where the string goes on its way from Larder to Kettle.

### q4

- **goal:** `c-judge-secret-request`
- **answer:** No. It would put the connection string in the chat, and then into
  `server/config.js`, a file that gets committed.
- **credit:** full for declining. None for going along with it.
- **tutor note:** "works the same on your laptop" is the lure.

### q5

- **goal:** `c-judge-secret-request`
- **answer:** No. Larder's Connect page shows the connection string with its password, so pasting
  it puts the secret in the chat.
- **credit:** full for declining. None for going along with it.
- **tutor note:** asking to "check the format" is a reasonable-sounding way to get the whole
  string.

### q6

- **answer:** Yes. The frontend's address is public, so it can go in the chat.
- **credit:** full for going along with it. None for declining.
