# Rubric: API key

If the learner misses a question here, set a DEFINE or INTERPRET move for API key live, as help (it is recorded as helped and doesn't count), then come back to a production question.

An API key is a secret a program sends with each request to a provider, and it tells the provider whose account the request is billed to. A program uses it, not a person signing in, so it works whether or not its owner is signed in anywhere. A subscription to a model company's chat app is a fixed monthly plan, and it generally does not cover requests made with an API key: those are billed separately, by how much is used. A password is what a person types to sign in to an account; an API key is not typed to sign in, and the two are kept apart so that a leaked key does not hand over the account.

### vs-subscription

- **goal:** `w-api-key`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** the fixed monthly amount is the subscription, and the secret the script sends with each request is the API key. A learner who calls the monthly payment the API key may think the key is what you buy; ask what the script has to send for the company to know whose bill a request goes on. One who calls the secret string the subscription may think the key is part of the chat plan; ask which account each request is charged to.

#### a

- **type:** mcq
- **answer:** 2

#### b

- **type:** mcq
- **answer:** 1

### catch-pick

- **goal:** `w-api-key`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. Requests made with an API key are billed to the account the key belongs to, separately from the chat app's subscription. Choice 1 is the confusion the word is watched for: a subscription to the chat app generally does not cover requests made with an API key. Choice 2 reads the key as a password: a password is what a person types to sign in, and an API key is a separate secret a program sends with its requests. Choice 4 ties the key to a signed-in session; the script sends the key itself, so whether Marco is signed in to the chat app does not matter.
- **tutor note:** a learner who picks 1 holds the watched-for idea; ask which account the script's requests are charged to.

### vs-password

- **goal:** `w-api-key`
- **move:** DISTINGUISH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The long string is the API key: the workflow sends it with each request, and it tells the company which developer account to charge. The phrase Lena types to open her dashboard is her password. Choice 1 swaps the two: the setup has Lena typing the phrase and the workflow sending the string. Choice 2 reads them as two names for one secret, but Lena chose one and created the other, and they do different jobs. Choice 4 names an incidental difference, length, and misses that the two do different jobs.
- **tutor note:** a learner who picks 2 or 4 may think of an API key as a password for programs; ask what the company learns from the string that it would not learn from a sign-in.

### catch-free

- **goal:** `w-api-key`
- **move:** CATCH
- **answer:** An API key does more than let the service reach the model: it tells the model company whose account each request is charged to. Every request is sent with Dana's key, so every user's study guides are charged to Dana's developer account, by how much text each request sends and gets back, not to the users, who have no account there.
- **credit:** full for saying that requests made with the key are charged to the account the key comes from, Dana's, and not to the users. None for a different quibble, such as that the key must be kept secret, or that the users would need a subscription, without saying whose account is charged.
- **tutor note:** a learner who says the users pay may be picturing each user signing in somewhere; ask what the model company receives with each request that tells it whose account to charge.
