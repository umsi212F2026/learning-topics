# Rubric: prompt caching

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
