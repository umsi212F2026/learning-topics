# Rubrics: The words of coding agents

Answers for `tasks/words.md`. **Do not read this before attempting the questions.**

### q-worth-switching-plan-has-code

- **type:** free
- **goal:** c-choose-model
- **answer:** not worth trying. The task is mechanical and the plan already contains the code to
  write, so there is no judgment left for a stronger model to make. The default handles it, and
  switching up would cost more per token for the same edit.
- **credit:** full credit for "not worth trying" with the reason tied to the detail in the situation:
  the plan already contains the code, or the task is a mechanical rename with nothing to decide. Half
  credit for "not worth trying" with only a general preference for the cheaper model, or with a
  reason not in the situation. No credit for "worth trying", however argued.

### q-split-after-spec

- **type:** free
- **goal:** c-split-chats
- **answer:** a new chat. Everything the next step needs, the spec and the plan, is written down in
  files the new chat can read, so nothing is lost by leaving this one behind, and the ideas you
  abandoned are exactly what you do not want the agent working from. The hour of conversation would
  also be resent as input on every turn of the execution, so the fresh chat is cheaper as well.
- **credit:** full credit for a new chat with a reason tied to the situation: the spec and plan are in
  files, so nothing the next step needs lives only in this chat, or a fresh start keeps the abandoned
  ideas out of the way. The token reason also earns full credit when it is tied to the chat being an
  hour long. Half credit for a new chat with a generic reason ("fresh chats are cleaner") tied to
  nothing in the situation. No credit for staying in this chat, and no credit for a reason that does
  not apply here, such as a split saving work that has not been written down.

### q-estimate-basis

- **type:** free
- **goal:** c-ask-cost-estimate
- **answer:** it rests on two things: the token counts it read out of that chat's session log, input
  and output, and the price list it applied to them, which is U-M's rates for gpt-5.6-luna. The bill
  could still differ because U-M's rates are subject to change and need not match a vendor's own
  list, because the chat may have run more than one model or spun off a subagent logged in a separate
  file that the count missed, because the gateway publishes no rate for cached input, or because
  Toolkit spend is reported per key rather than per chat, so no bill for this one chat exists to
  compare it with.
- **credit:** full credit needs both halves: the basis named as which counts (input and output tokens
  from the log) and whose prices (U-M's, for that model); and one specific reason the bill could
  differ, such as a model switch partway, subagent work in another log file, cached input the
  published rates do not cover, rates having changed, or the counts having been read wrongly from the
  log's running totals. Half credit for the basis alone. No credit for "it is only an estimate", for
  "AI can make mistakes", or for any reason with nothing specific to this chat or this key in it.
