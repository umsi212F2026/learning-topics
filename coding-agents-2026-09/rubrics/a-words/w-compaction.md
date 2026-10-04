# Rubric: compaction

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
