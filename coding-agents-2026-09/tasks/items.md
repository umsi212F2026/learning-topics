# The words of coding agents

**Intended goals:** `w-token`, `w-input-tokens`, `w-output-tokens`, `w-prompt-caching`, `w-model`,
`w-reasoning-effort`, `w-context`, `w-context-window`, `w-compaction` and `w-system-prompt`, with
three questions on `c-choose-model`, `c-split-chats` and `c-ask-cost-estimate` at the end.

Answer each question in one to three sentences, in your own words, with nothing open. Where a
question quotes a coding agent, imagine it is Codex working on one of your own course projects,
running the course default (gpt-5.6-luna at medium reasoning effort) unless the question says
otherwise.

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
