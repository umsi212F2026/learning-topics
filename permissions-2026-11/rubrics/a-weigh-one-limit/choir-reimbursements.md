Part a: for the harm to happen, the agent would have to read a request carrying the hidden line
(it reads every request, and anyone can write one) and then use a secret that can send payments
from the choir's account. The only such secret in the paragraph is the bank token, which "lets its
holder see the account's transactions and also send payments from it." A scoped token that can
only see transactions cannot send a payment, and it replaces the old one in the settings file, so
however the agent is steered, and whatever command it runs, it holds nothing that moves money. The
limit cuts the harm's route: Yes.

Part b: the step reads the skill file and the requests, uses the bank token to get "the choir's
bank account history," and writes the to-pay file. Seeing the account's transactions is all it
needs the token for; it never sends a payment itself, since Tomas pays the list by hand. The
scoped token leaves everything the step uses: Yes.

### q1

- **goal:** `c-judge-limits`
- **cases:** sound-limit
- **type:** compound

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 1
