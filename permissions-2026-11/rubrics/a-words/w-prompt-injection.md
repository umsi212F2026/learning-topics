# Rubric: Prompt injection

If the learner misses a question here, set a DEFINE or INTERPRET move for prompt injection live, as help (it is recorded as helped and doesn't count), then come back to a production question.

Prompt injection is text in something an agent reads, such as an email, a web page or a submission, that steers it as though it were instructions from its user. What makes it injection is where the text comes from: not from the user, but from inside the material the agent was given to work on, written by someone else. A jailbreak is the course's contrast: the person talking to the model writes the prompt themselves, to get the model past its own built-in rules about what it will do. The jailbreaker is the user; the injector is someone the user never hears from. The reading draws this contrast in the sentence after it defines prompt injection.

### vs-jailbreak

- **goal:** `w-prompt-injection`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** the stranger's email is prompt injection: the line sat inside material the agent was reading, the organizer never wrote or saw it, and it steered the agent as though it were his instruction. The club member's prompt is a jailbreak: she is the agent's user, she wrote the prompt herself, and its aim was to get past the model's own refusal, not to pose as someone else. A learner who calls the email a jailbreak may be reading jailbreak as any attempt to make an agent misbehave; ask who wrote the line and whether the organizer knew of it. One who calls the member's prompt prompt injection may be reading injection as any tricky prompt; ask whose instructions she was pretending to be.

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 2

### catch-pick

- **goal:** `w-prompt-injection`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The line sits in a submission the agent reads and tries to steer it as though the organizer had asked for the link: prompt injection. Choice 1 reads the term as its confusable: a jailbreak is the user's own prompt aimed at the model's built-in rules, while this line was written by a member, not the organizer, and poses as the organizer's instructions. Choice 2 stretches the term to any outside text; most submissions are ordinary notes that steer nothing, so they are untrusted but not injection. Choice 4 drops the agent: a program saves the line as data and nothing happens, so there is nothing to be steered.

### catch-own-request

- **goal:** `w-prompt-injection`
- **move:** CATCH
- **answer:** That isn't prompt injection. The only instruction the agent followed was Omar's own request, and it read no text from anyone else that could have steered it. The harm came from a vague request that the agent read too broadly, not from someone else's words posing as his.
- **credit:** full for naming that the instruction came from Omar himself, the agent's user, and no text from anyone else reached the agent, so this is not prompt injection. Naming the vague request as the real cause is welcome but not required. Half for "his request was too vague" with nothing on why that rules out injection, or for "nothing was injected" with nothing on where the instruction did come from. None for a different quibble alone, such as that Omar should have kept a backup.
- **tutor note:** a learner who agrees, since the agent did something harmful, is reading prompt injection as any harmful instruction; ask who wrote the words the agent acted on.
