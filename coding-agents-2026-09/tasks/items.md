# The words of coding agents

**Intended goals:** `w-token`, `w-input-tokens`, `w-output-tokens`, `w-prompt-caching`, `w-model`,
`w-reasoning-effort`, `w-context`, `w-context-window`, `w-compaction` and `w-system-prompt`, with
three questions on `c-choose-model`, `c-split-chats` and `c-ask-cost-estimate` at the end.

A practice draw takes 2 of these.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes a coding agent, imagine it is Codex working on one of your own course projects,
running the course default (gpt-5.6-luna at medium reasoning effort) unless the question says
otherwise.

### q-define-token

Your agent tells you that a chat used 412,000 tokens. Say what a token is, in your own words.

### q-token-vs-word

What is the difference between a token and a word?

### q-input-vs-output-tokens

A usage report for one chat lists input tokens and output tokens separately. What is the difference
between them?

### q-short-message-small-input

A classmate says: "My last message to the agent was one line, so that turn barely cost anything on
the input side." What is wrong with what they said?

### q-what-counts-as-input

You are twenty messages into a chat in Codex, working on your app, and you send one more message.
Which of these is counted in that turn's input tokens?

1. Your new message, the twenty messages before it, the system prompt, and the contents of any file the agent has read into the chat.
2. Only your new message.
3. Your new message and the agent's reply to it.
4. Every chat you have had with Codex this week.

### q-completion-tokens-report

Your agent reports: "That chat came to 380,000 prompt tokens and 24,000 completion tokens, and the
9,000 reasoning tokens are already inside the 24,000." What is it telling you?

### q-thinking-is-free

A classmate says: "I turned the reasoning effort up, but that part is free. The thinking never shows
up in the reply, so there is nothing extra to pay for." What is wrong with what they said?

### q-define-prompt-caching

Your agent mentions that prompt caching is why the last few turns cost less than you expected. Say
what prompt caching is, in your own words.

### q-cached-input-report

Your agent says: "On that turn, 41,000 of the 48,000 input tokens were cached input." What is it
telling you, and what does it rule out?

### q-caching-is-memory

A classmate says: "Prompt caching means the agent remembers our conversation. I can start a new chat
tomorrow and it will still have the cache of what we decided." What is wrong with what they said?

### q-model-vs-agent

You work with Codex, and Codex runs on one of several models. What is the difference between the
model and the agent?

### q-codex-priced

A classmate says: "Codex costs $1.25 per million tokens, so I can work out what my week cost by
multiplying that by my total token count." What is wrong with what they said?

### q-effort-vs-model

Codex lets you choose a model and, separately, set a reasoning effort. What is the difference
between the two?

### q-high-effort-better-model

A classmate says: "I put the reasoning effort on high, so I am on the top model now and do not need
to switch." What is wrong with what they said?

### q-define-context

Your agent says it is running low on context. Say what context means here, in your own words.

### q-new-chat-remembers

A classmate says: "I explained my database tables to Codex on Tuesday, so when I open a new chat on
Thursday it already has them in context and I can just say 'the tables we discussed'." What is wrong
with what they said?

### q-context-vs-window

What is the difference between a chat's context and the model's context window?

### q-window-percent-left

Your agent says: "Heads up: this chat is at 92% of the context window." What is it telling you, and
what does it not tell you?

### q-define-compaction

Your agent tells you it is about to compact the conversation. Say what compaction is, in your own
words.

### q-compaction-vs-new-chat

What is the difference between a chat being compacted and you starting a new chat?

### q-compacted-report

Partway through a long session on your app, Codex says: "Context low. I compacted the conversation."
Which of these is true right now?

1. The same chat is carrying on, with the earlier part of the conversation replaced by a summary, so detail the summary did not keep is no longer in front of the model.
2. The chat has been closed and a new one opened, so nothing from before it is available.
3. The whole conversation is still in front of the model, stored more efficiently.
4. The files in your project have been made smaller to save space.

### q-system-prompt-vs-first-message

What is the difference between the system prompt and the first message you type in a chat?

### q-system-prompt-billed

A classmate says: "The system prompt costs me nothing. I never wrote it and I cannot even see it, so
it is not part of my usage." What is wrong with what they said?

### q-worth-switching-plan-has-code

You are on the course default, gpt-5.6-luna at medium reasoning effort. The next task in your plan
is to rename a prop in two React components, and the plan already gives the complete code for both
changes. Is trying a better model worth it here? Give the detail that decides it.

### q-split-after-spec

You have spent an hour brainstorming in one chat. The spec and the plan are written and saved as
files in the repository, and the chat itself is full of ideas you tried and abandoned along the way.
The next step is to execute the plan. Should that happen in this chat or a new one, and why?

### q-estimate-basis

You asked an agent what yesterday's chat cost, and it replied: "About $0.74. I read the session log,
added up the input and output tokens for gpt-5.6-luna, and priced them at U-M's rates for that
model." What is that figure resting on, and name one reason the bill could still come out different?
