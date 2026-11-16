# Rubric: Sandbox

If the learner misses a question here, set a DEFINE or INTERPRET move for sandbox live, as help (it is recorded as helped and doesn't count), then come back to a production question.

A sandbox is a closed-off place where a program or agent runs, which it cannot reach out of: anything outside it, such as a settings file holding a login, is out of its reach altogether, and a sandbox can also cut off shell commands and the network. Read-only access is the course's contrast: it limits what an executor can do to the files it can get to, letting it read them but not change them. The two answer different questions. Read-only access to everything still lets an executor read every file, secrets included; a sandbox says nothing on its own about whether the files inside it can be changed. The reading gives both in "Limits you can put on a step": read-only access under files, and the sandbox as one of the five ways to impose limits, where it keeps the grading agent away from the settings file with the token.

### vs-read-only

- **goal:** `w-sandbox`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** under A the agent can open every file on the laptop, the settings file included; it just can't change any of them, so it can read the login. Under B the settings file is outside the sandbox and out of the agent's reach. A learner who picks "Neither" or "B only" is reading read-only access as keeping the agent away from files; ask what read-only access stops the agent from doing to a file it can open.

### catch-can-change

- **goal:** `w-sandbox`
- **move:** CATCH
- **answer:** A sandbox limits what the agent can get to, not what it can do with what is inside. The setlists are inside the sandbox, so unless they are also made read-only, the agent can still change or delete them. What the sandbox stops is the agent reaching anything outside the setlist folder.
- **credit:** full for naming that the sandbox keeps the agent from reaching outside the folder but does not stop it changing the files inside, so the setlists can still be changed. Half for "it can still change the setlists" with nothing on what the sandbox does limit, or for "a sandbox only keeps it from getting out" with nothing on the files inside it. None for a different quibble alone, such as that cutting off the network was unnecessary.
- **tutor note:** a learner who agrees is reading sandbox as read-only access; ask which files the agent can still get to, and what it could do to them.

### catch-pick

- **goal:** `w-sandbox`
- **move:** CATCH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. The settings file is outside the sandbox, so the agent cannot reach it. Choice 1 reads the term as its confusable: nothing says the price list is read-only, and a sandbox alone leaves files inside it changeable. Choice 3 stretches the term past what it names: the requests are inside the sandbox and the agent reads them, so their words can still steer it; the sandbox only limits what a steered agent can reach. Choice 4 reads it as an approval prompt, which is a person checking the agent's actions, not a closed-off place.
