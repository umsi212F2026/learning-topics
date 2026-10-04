# Rubric: output tokens

### q-completion-tokens-report

- **type:** free
- **goal:** w-output-tokens
- **move:** INTERPRET
- **answer:** the model wrote 24,000 tokens across that chat, and the thinking it did before
  answering is part of that figure rather than a charge on top of it, so the output side is 24,000
  and not 33,000. The 380,000 is the other side of the count, what was sent to the model over all the
  chat's turns. The two are priced separately.
- **credit:** full credit for both halves: the model produced 24,000 tokens of output for the chat,
  and the reasoning tokens sit inside that number so they must not be added to it. Full credit for
  also naming the 380,000 prompt tokens as the input side. Half credit for either half alone. No
  credit for adding the 9,000 on top to get 33,000, or for reading completion tokens as what the
  learner typed.

### q-thinking-is-free

- **type:** free
- **goal:** w-output-tokens
- **move:** CATCH
- **answer:** what the model produces while reasoning is counted in the output tokens for that turn
  whether or not any of it is shown to you. Raising the reasoning effort makes it produce more of
  that, so the output count and the cost of the turn go up even when the visible reply is the same
  length.
- **credit:** full credit for saying reasoning tokens are counted as output and are billed, so more
  effort means more output tokens. Half credit for "thinking costs something" with nothing about
  output tokens or about being counted. Do not accept a different quibble as the error: that higher
  effort is slower, that a cheaper model would do, or that the reply might be better.
