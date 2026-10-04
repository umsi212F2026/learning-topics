# Rubric: reasoning effort

### q-effort-vs-model

- **type:** free
- **goal:** w-reasoning-effort
- **move:** DISTINGUISH
- **answer:** the model is which system is generating the text, and it sets the per-token rates and
  the ceiling on what the agent can do. Reasoning effort is a dial on whichever model you already
  chose, saying how much thinking it should do before it answers: turning it up makes that same model
  work longer and produce more output tokens per turn, and it changes neither which model is running
  nor its rates.
- **credit:** full credit for saying the model is which system is running while the effort is how
  much thinking that model does before answering, set separately from the model. Full credit for an
  answer framed as which dial can be changed without changing the other. Half credit for "one is the
  brain and the other is how hard it thinks" with nothing about them being set separately. No credit
  for "high effort means a better model", or for treating effort as another name for the model's
  capability.

### q-high-effort-better-model

- **type:** free
- **goal:** w-reasoning-effort
- **move:** CATCH
- **answer:** reasoning effort is a dial on the model that is already running, and turning it up does
  not change the model. They are on the same model as before, at the same rates, doing more thinking
  per turn and paying for it in output tokens. Moving to a stronger model is a separate choice.
- **credit:** full credit for saying the two are set separately, so raising the effort leaves you on
  the same model. Full credit whether or not they add that the extra thinking costs output tokens. An
  answer that says raising the effort first can still be the right move has found the error only if it
  also says the model has not changed. Do not accept a different quibble as the error: that high
  effort is slower, that they should save money, or that the top model would be overkill.
