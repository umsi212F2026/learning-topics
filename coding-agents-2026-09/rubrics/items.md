# Rubrics: The words of coding agents

Answers for `tasks/words.md`. **Do not read this before attempting the questions.**

### q-define-token

- **type:** free
- **goal:** w-token
- **move:** DEFINE
- **answer:** a token is the unit of text that models count and charge in: text is chopped into
  pieces, roughly the size of a short word or a part of a longer one, before it goes to the model,
  and everything sent and everything written back is measured in those pieces. So 412,000 is a count
  of chunks of text, not of words, letters or messages.
- **credit:** full credit for saying a token is the unit text is counted and billed in, a chunk of
  text around the size of a word or smaller. Full credit for "a piece of a word, and what usage and
  prices are counted in" without mentioning billing. Half credit for "a piece of text" with nothing
  about counting or pricing. No credit for "a token is a word", for "a token is a message or a turn",
  or for reading it as an access token or API key.

### q-token-vs-word

- **type:** free
- **goal:** w-token
- **move:** DISTINGUISH
- **answer:** a word is a unit of language; a token is the unit the model's software splits text
  into and counts, and the two do not line up one to one. A common short word is usually one token,
  a long or unusual one is several, and spaces, punctuation and code symbols are counted too. That
  is why a bill or a usage figure in tokens cannot be read off a word count.
- **credit:** full credit for saying tokens are the counted and billed unit and do not correspond
  one to one with words: a word can be several tokens, and punctuation counts. Full credit for an
  answer that gives the rough ratio (a token is a bit under a word in English) as long as it says
  the two counts differ. Half credit for "a token is about the same as a word" with nothing about the
  counts differing. No credit for incidental differences, such as tokens being "what computers use
  and words being for people", with nothing about counting, or for "a token is a sentence".

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

### q-define-prompt-caching

- **type:** free
- **goal:** w-prompt-caching
- **move:** DEFINE
- **answer:** every turn sends the conversation so far all over again, and prompt caching is the
  provider holding on to the beginning of what was sent on a recent turn so it does not have to be
  processed from scratch the next time. When a turn's input starts with text that is already cached,
  that part is billed at a lower rate than input the model has not seen before, which is why a long
  chat can cost less per turn than the raw input count suggests. The saving only lasts while the
  cache does, and only while the start of the input stays the same.
- **credit:** full credit for saying that input which is sent again is charged at a lower rate, or
  does not have to be reprocessed, because it has been seen before. Full credit without the details
  that it has to be the start of the input or that the cache expires. Half credit for "it makes
  things cheaper the second time" with nothing about the input being sent again. No credit for "the
  model remembers what I told it", which is the confusion with memory, since the model keeps nothing
  and the conversation is still sent every turn. No credit for "it stores the answers, so asking the
  same question again is free".

### q-cached-input-report

- **type:** free
- **goal:** w-prompt-caching
- **move:** INTERPRET
- **answer:** of the 48,000 tokens sent on that turn, 41,000 had been sent recently enough to be
  served from the cache, so they were billed at a lower rate than the 7,000 that were new. The cached
  tokens are part of the 48,000, not 41,000 more on top of it, so the turn sent 48,000 tokens and
  cost less than 48,000 fresh tokens would have. It does not mean the model remembered anything by
  itself: all 48,000 were still sent.
- **credit:** full credit needs both: cached input is part of the input count rather than an addition
  to it, and that part is charged at a lower rate than new input. Half credit for either half alone.
  No credit for reading the turn as 89,000 tokens, for reading it as the model having remembered the
  conversation instead of being sent it, or for reading the turn as free.

### q-caching-is-memory

- **type:** free
- **goal:** w-prompt-caching
- **move:** CATCH
- **answer:** caching is about the price of text that gets sent again, not about the model keeping
  anything. A new chat sends none of yesterday's conversation, so there is nothing for a cache to
  match and nothing for the model to have kept. Even inside one chat the conversation is resent every
  turn; the cache only makes the repeated part cheaper, and it expires.
- **credit:** full credit for saying the cache carries nothing into a new chat: it lowers the price
  of input that is sent again, and a new chat sends none of the old conversation. Full credit for an
  answer built on caches expiring only if it also says the new chat would have to send the
  conversation for a cache to help at all. Do not accept a different quibble as the error: that they
  should write their decisions into a file (good advice, not the mistake), that the agent could read
  the old chat's log, or that caching is unreliable on the gateway.

### q-model-vs-agent

- **type:** free
- **goal:** w-model
- **move:** DISTINGUISH
- **answer:** the agent is the program you talk to: it takes your request, reads files, runs
  commands, keeps the chat, and calls out to have text generated. The model is what generates that
  text, chosen from a list and priced per token in its own right. One agent can run different models,
  and one model can be driven by different agents, so what a price list prices is the model, while
  the tools, the permissions and the interface belong to the agent.
- **credit:** full credit for saying the agent is the program doing the work around the model (files,
  commands, the chat) while the model is what generates the text and is what gets priced, with the
  model swappable under the same agent. Half credit for "one is the program and one is the AI" with
  nothing about the model being chosen or being what is priced. No credit for treating them as two
  names for one thing, or for "the model is which version of Codex you installed".

### q-codex-priced

- **type:** free
- **goal:** w-model
- **move:** CATCH
- **answer:** there is no price for Codex. Prices are set per model, and Codex is the agent that runs
  whichever model you picked, so the rate depends on whether the work ran on gpt-5.6-luna, gpt-5.6-sol
  or something else, and it can change partway through a chat. One rate over a total token count is
  the wrong shape besides, since input and output are priced separately.
- **credit:** full credit for saying prices attach to the model rather than to the agent, so which
  model ran is what sets the rate, and a week of work may have run more than one. Full credit for
  naming the separate input and output rates instead, if it is given as the reason a single rate over
  a total cannot work. Do not accept a different quibble as the error: that the number may be out of
  date, that U-M's rates differ from the vendor's, or that they should look at the Toolkit page.
  Those are all true and none of them is what is wrong with the sentence.

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
  agent "forgot" counts only if it also says nothing was kept between the chats in the first place.
  Do not accept a different quibble as the error: that the tables may have changed since Tuesday,
  that Codex may have been updated, or that they should have committed their work.

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

### q-define-compaction

- **type:** free
- **goal:** w-compaction
- **move:** DEFINE
- **answer:** when a chat's context comes close to the model's context window, the agent replaces the
  earlier part of the conversation with a shorter summary of it so the chat can carry on within the
  limit. The same chat continues, but the detail that the summary did not keep is no longer in front
  of the model.
- **credit:** full credit for saying the earlier conversation is summarized or compressed so that the
  chat fits the window and can continue, with detail lost in the process. Half credit for "it
  shortens the conversation" with nothing about the window or nothing about detail being lost. No
  credit for "it starts a new chat", "it deletes the chat", or "it saves the chat to a file".

### q-compaction-vs-new-chat

- **type:** free
- **goal:** w-compaction
- **move:** DISTINGUISH
- **answer:** both leave the model with less in front of it, but compaction happens inside the chat,
  to make room when it nears the window: the agent decides what the summary keeps, and it happens
  whether or not you were ready for it. Starting a new chat is your decision and begins from nothing,
  so whatever the next step needs has to be written down somewhere first or said again. Compaction
  leaves you a summary you did not write; a new chat leaves you nothing at all.
- **credit:** full credit for both halves: compaction is the agent summarizing the earlier
  conversation so that the same chat can continue, often at a moment you did not choose, while a new
  chat starts empty and carries nothing over. Half credit for one half right and the other vague or
  missing. No credit for "they are the same thing", or for "compaction is what happens when you start
  a new chat".

### q-compacted-report

- **type:** mcq
- **goal:** w-compaction
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 confuses compaction with starting a new chat: the same chat carries on. 3 is the
  tempting one, since the chat still reads normally on screen, but compaction is lossy and detail the
  summary did not keep is gone from the model's view. 4 reads it as something happening to the
  project; compaction touches the conversation, not your files.

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
