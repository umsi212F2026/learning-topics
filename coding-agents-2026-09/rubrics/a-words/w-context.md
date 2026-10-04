# Rubric: context

### q-define-context

- **type:** free
- **goal:** w-context
- **move:** DEFINE
- **answer:** the context is everything the model is given on a single turn: the system prompt, the
  conversation so far, whatever files or command output the agent has read in, and your latest
  message. It is what the model has in front of it when it answers, which is far more than what you
  typed, and anything not in it, an earlier chat included, does not exist as far as that turn is
  concerned.
- **credit:** full credit for saying it is what the model is given, or has in front of it, on a turn,
  and that it is more than the latest message: the conversation so far and anything read in are part
  of it. Half credit for "the conversation" alone. No credit for "what the model remembers" or "what
  it knows", which describe the model holding something between turns rather than text being sent
  each time. No credit for describing the limit instead of the contents, which is the context window.

### q-new-chat-remembers

- **type:** free
- **goal:** w-context
- **move:** CATCH
- **answer:** a new chat starts with none of Tuesday's chat in its context. The model holds nothing
  between chats: it only has what is sent on the turn, and a fresh chat sends the system prompt,
  whatever project instructions the agent loads, and what you type. Thursday's agent has no way to
  resolve "the tables we discussed" unless they are written somewhere it can read, such as a file in
  the repository. AGENTS.md is the one Codex reads by itself at the start of every session.
- **credit:** full credit for saying nothing carries over by itself, so Tuesday's explanation is not
  in Thursday's context, which holds only what is sent in that chat. Full credit for adding that the
  way to carry it over is to write it down where the agent will read it. An answer that says the
  agent "forgot" counts only if it also says the model kept nothing between the chats in the first
  place. Do not accept a different quibble as the error: that the tables may have changed since
  Tuesday, that Codex may have been updated, or that they should have committed their work.
