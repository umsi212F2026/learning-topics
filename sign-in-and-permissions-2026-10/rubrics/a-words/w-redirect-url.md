# Rubric: Redirect URL

If the learner misses a question here, set a DEFINE or INTERPRET move for redirect URL live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A redirect URL is the address in your app the provider sends the user back to after signing in,
usually a callback route on the backend, such as `/auth/github/callback`. The provider sends users
back only to a redirect URL registered with it in advance, so each place the app runs, localhost
and the live app, needs its own registered there. A GitHub OAuth app takes several (up to ten as
of August 2026), and a Google client takes several too, so the live one is added beside the
localhost one, not swapped for it. The confusable is the app's own URL, the address people go to
in order to use the app. "Callback URL" and "redirect URI" are other names for the same thing, not
confusables.

### q1

- **goal:** `w-redirect-url`
- **move:** DISTINGUISH
- **answer:** Pantry's own URL, `https://pantry.pagecove.app`, is where people go to use the app.
  The redirect URL is the particular address in the app, such as the backend's
  `/auth/github/callback`, that GitHub sends the user back to after they sign in, and it has to be
  registered with GitHub in advance.
- **credit:** full for naming that the redirect URL is where the provider sends the user back after
  sign-in, while the app's URL is where users go to use it. Half for "the redirect URL is the
  callback" or "it's on the backend" without saying who sends the user there or when. None for an
  incidental difference alone, such as that one is longer or ends in `/callback`.

### q2

- **goal:** `w-redirect-url`
- **move:** CATCH
- **answer:** That is Pantry's own URL, where people go to use it. The redirect URL is the address
  GitHub sends the user back to after they sign in, the backend's callback route, such as
  `https://pantry-api.rivetbox.com/auth/github/callback`.
- **credit:** full for naming that the redirect URL is where the provider sends the user back after
  signing in, not the address people use to reach the app. Half for "it should be the backend's
  address" without saying why. None for a different quibble alone, such as that people don't type
  addresses, they click links.
- **tutor note:** an app can be set up so that GitHub sends the user back to a frontend route; a
  learner who says so and still names the redirect URL as the return address after sign-in earns
  full.

### q3

- **goal:** `w-redirect-url`
- **move:** CATCH
- **answer:** The redirect URL isn't only a setting in the code: GitHub sends users back only to a
  redirect URL registered with it. The live one has to be added at GitHub too, beside the
  localhost one, or GitHub will refuse to send users back to the live app.
- **credit:** full for naming that the live redirect URL must also be registered with the provider,
  since the provider sends users back only to a registered one. Half for "GitHub needs to know
  about it" without saying that the provider refuses an unregistered one. None for a different
  quibble alone, such as the spelling of the path or that the setting should be an environment
  variable.
- **tutor note:** a learner who says to replace the localhost one at GitHub has the word right and
  earns full; ask what happens next time they work on their laptop, since GitHub can hold both.
