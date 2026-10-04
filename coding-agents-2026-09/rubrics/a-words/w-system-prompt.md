# Rubric: system prompt

### q-system-prompt-vs-first-message

- **type:** free
- **goal:** w-system-prompt
- **move:** DISTINGUISH
- **answer:** the system prompt is the set of instructions the agent sends ahead of the conversation
  on every turn: who the model is acting as, what tools it has, how it should behave. You did not
  write it and usually cannot see it, and it is counted in the input tokens for each turn. Your first
  message is yours, part of the conversation, and it sits after the system prompt as one more turn;
  the model treats the system prompt as standing instructions that later messages do not simply
  override.
- **credit:** full credit for saying the system prompt comes from the agent rather than from you, is
  sent ahead of the conversation, and governs the whole chat, while your first message is just the
  first turn of the conversation. Full credit for an answer that names the standing-instruction
  difference instead. Half credit for "one comes from the app and one comes from me" with nothing
  about it being sent ahead or holding over the whole chat. No credit for "the system prompt is
  whatever I say first", which is the confusion the question is about.

### q-system-prompt-billed

- **type:** free
- **goal:** w-system-prompt
- **move:** CATCH
- **answer:** the system prompt is sent to the model as part of the input on every turn, so it is
  counted in that turn's input tokens and billed like anything else that is sent. Not having written
  it and not being shown it make no difference to what is in the context and what is counted.
- **credit:** full credit for saying the system prompt is sent with every turn and counted in the
  input tokens, so it is paid for. Half credit for "it is in the context" with nothing about being
  counted or billed. Do not accept a different quibble as the error: that it is short enough not to
  matter, that caching may make it cheap (it is still counted, and caching changes the rate), or that
  the university is paying.
