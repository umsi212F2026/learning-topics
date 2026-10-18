# Rubric: output tokens

### q-completion-tokens-report

- **type:** free
- **goal:** w-output-tokens
- **move:** INTERPRET
- **answer:** completion tokens are output tokens: the model wrote 24,000 tokens across that chat,
  including any thinking it did before answering. Prompt tokens are input tokens: 380,000 is what
  was sent to the model over all the chat's turns. The two are priced separately, with output
  costing more per token.
- **credit:** full credit for both halves: the 24,000 completion tokens are what the model wrote
  (the output side), and the 380,000 prompt tokens are what was sent to it (the input side).
  Saying the reasoning is part of the 24,000, or that the two sides are priced apart, is welcome
  and is not required. Half credit for either half alone. No credit for reading completion tokens
  as what the learner typed, or as the tokens left to finish the task.

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
