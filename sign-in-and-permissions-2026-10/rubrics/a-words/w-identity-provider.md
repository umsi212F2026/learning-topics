# Rubric: Identity provider

If the learner misses a question here, set a DEFINE or INTERPRET move for identity provider live,
as help (it is recorded as helped and doesn't count), then come back to a production question.

An identity provider is the outside service that vouches for who the user is, such as Google or
GitHub. It is outside your app, and its job ends at saying who the user is: what that user may do
in your app is your app's decision. The confusable is your host, which runs your app's code and
holds its settings but knows nothing about who your users are. "IdP" and "sign-in provider" are
other names for the same thing, not confusables.

### q1

- **goal:** `w-identity-provider`
- **move:** DISTINGUISH
- **answer:** Google, as identity provider, vouches for who each member is when they sign in.
  Rivetbox, as host, runs Pantry's backend code and holds its settings; it has nothing to say about
  who any user is.
- **credit:** full for naming that the identity provider tells the app who the user is, and the
  host runs the app. Half for one side right with the other vague, such as "Google handles
  sign-in" with nothing on what the host does. None for an incidental difference alone, such as
  that one is free, one is bigger, or one is a different company.
- **tutor note:** a learner who says "the host stores the client secret, the provider issues it"
  has named a true detail that doesn't separate the two jobs; ask which of them knows who a member
  is.

### q2

- **goal:** `w-identity-provider`
- **move:** CATCH
- **answer:** An identity provider is an outside service that vouches for who the user is; here
  that is Google. The `users` table is Pantry's own record of members it already knows, keyed by
  the id Google gave it; it vouches for nobody.
- **credit:** full for naming that the identity provider is the outside service that tells Pantry
  who someone is (Google), and the table is only Pantry's own record of what it was told. Half for
  "the identity provider is Google" without saying why the table isn't one. None for a different
  quibble alone, such as that the table should also store email addresses.

### q3

- **goal:** `w-identity-provider`
- **move:** CATCH
- **answer:** An identity provider only vouches for who the user is. Google knows nothing of
  Pantry's recipes or its rule that members edit only their own; Pantry's server decides that, by
  checking the signed-in member against each recipe's author.
- **credit:** full for naming that the identity provider says who the user is and nothing about
  what they may do in Pantry, which Pantry itself decides. Half for "that's Pantry's job" without
  saying what Google's job is. None for a different quibble alone, such as that GitHub would be a
  better choice than Google.
