# Rubric: input tokens

### q-input-vs-output-tokens

- **type:** free
- **goal:** w-input-tokens
- **move:** DISTINGUISH
- **answer:** input tokens are everything sent to the model on a turn: the system prompt, the
  conversation so far, any file or command output the agent read in, and your latest message. Output
  tokens are what the model wrote back on that turn, including the reasoning it did before answering.
  They are counted apart because they are priced apart, with output costing several times more per
  token than input on most models.
- **credit:** full credit for both sides: input is what goes to the model, which is more than the
  message you typed, and output is what the model produces, with the two counted and priced
  separately. Full credit if the separate prices are missing but the sent-versus-produced split is
  clear. Half credit for "input is my question and output is the answer", which leaves out everything
  else that is sent. No credit for reversing the two, or for treating them as two names for one
  count.

### q-short-message-small-input

- **type:** free
- **goal:** w-input-tokens
- **move:** CATCH
- **answer:** the input for a turn is not just the message you typed. The whole conversation so far
  goes to the model again, along with the system prompt and anything the agent has read into the
  chat, so a one-line message late in a long chat can carry tens of thousands of input tokens. The
  length of the message says almost nothing about the input count for that turn.
- **credit:** full credit for saying the conversation so far, and anything else in the context, is
  sent again on every turn, so the input count depends on the state of the chat rather than on the
  length of the message. Half credit for "there is other stuff in there too" with no mention of the
  conversation being resent. Do not accept a different quibble as the error: that output tokens cost
  more, that a short message can still ask for expensive work (that is the output side), that prompt
  caching may make the repeated part cheaper (it changes the rate, not the fact that it is sent), or
  that they should check the prices.

### q-what-counts-as-input

- **type:** mcq
- **goal:** w-input-tokens
- **move:** DEFINE
- **answer:** 1
- **credit:** 2 is the common mistake, and the one the count punishes: everything already in the chat
  is sent again on each turn. 3 puts the reply on the wrong side, since what the model writes is
  counted as output. 4 treats separate chats as one thing: another chat is not in this one's context
  and is not sent.
