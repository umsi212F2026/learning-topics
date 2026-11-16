# Rubric: BYOK

If the learner misses a question here, set a DEFINE or INTERPRET move for BYOK live, as help (it is recorded as helped and doesn't count), then come back to a production question.

BYOK, bring your own key, is an arrangement in which each user gives a service their own API key, so the model calls made for them are billed to them rather than to the service. It changes who is billed, not who sees the data: the service and the model company still see what the agent step reads. Sign-in is a different thing: it tells a service who the user is, and says nothing about whose account pays for model calls. A service can ask users to sign in and still pay for every call itself, and a service can be BYOK with no sign-in at all.

### vs-sign-in

- **goal:** `w-byok`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. Service B uses each user's own key, so each user's summaries are billed to them, which is BYOK. Service A has users sign in, but pays for every summary from its own account, so it is not BYOK. Choice 1 reads BYOK as signing in with an account of your own. Choice 3 counts the sign-in as BYOK too. Choice 4 misses that Service B's users bring their own keys.
- **tutor note:** a learner who picks 1 or 3 may be reading "bring your own" as bringing your own account; ask whose account each service's summaries are billed to.

### catch-pick

- **goal:** `w-byok`
- **move:** CATCH
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only. Under BYOK each user's requests are made with their own key, so their runs are billed to them. Choice 2 has the billing the wrong way around: paying for every user from the service's own account is what BYOK replaces. Choice 3 stretches the term past what it names: BYOK changes who is billed, not who sees the data, so the model company still sees the notes. Choice 4 reads BYOK as a way of signing in; the key is for billing model calls, and BYOK says nothing about how users sign in.

### catch-free

- **goal:** `w-byok`
- **move:** CATCH
- **answer:** Under BYOK each user gives the service their own API key, and that key comes from the user's own account at a model company, which the model calls made for them are billed to. So a BYOK service is one where every user does need an account at a model company.
- **credit:** full for saying that BYOK means each user supplies their own API key, from their own account at a model company, so they would need such an account. None for a different quibble, such as that users would still sign up with the service, or that the service sees their notes, without saying that BYOK needs the user's own key and account.
- **tutor note:** a learner who sees nothing wrong may be reading BYOK as a feature that saves users trouble; ask where the key a BYOK user brings comes from.
