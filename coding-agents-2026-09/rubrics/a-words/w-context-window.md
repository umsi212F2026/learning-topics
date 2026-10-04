# Rubric: context window

### q-context-vs-window

- **type:** free
- **goal:** w-context-window
- **move:** DISTINGUISH
- **answer:** the context is the text actually in front of the model on a turn; the context window is
  the ceiling on how much of it there can be, a fixed size for that model, measured in tokens. The
  context grows as the chat goes on and the window does not, so when the context would exceed the
  window something has to be dropped or summarized to fit.
- **credit:** full credit for both: the context is what is sent on a turn, the window is the maximum
  that fits and is a property of the model, and the first grows toward the second. Half credit for
  naming one of them correctly and leaving the other vague. No credit for treating them as the same
  thing, or for describing the window as how long the agent remembers in hours or days rather than as
  an amount that fits.

### q-window-percent-left

- **type:** free
- **goal:** w-context-window
- **move:** INTERPRET
- **answer:** the conversation plus everything read into this chat now fills 92% of the most this
  model can be given on one turn, so there is room for only a little more before the chat has to be
  compacted or restarted. It is a statement about how full this one chat is: it is not about what you
  have spent or are allowed to spend, not a limit on your account, and it says nothing about whether
  the work so far is any good.
- **credit:** full credit for saying the chat's context is close to the ceiling on what fits in one
  turn, so something has to give soon, by compaction, a new chat, or dropping material. Half credit
  for "the chat is nearly full" with nothing about a ceiling on what fits on a turn. For the second
  half, accept any one correct exclusion: not a spending limit, not an account quota, not a time
  limit, not a claim about the quality of the work, not about other chats. No credit for reading it as
  a budget warning, or as the model being about to stop working for good.
