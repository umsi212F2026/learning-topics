# code review

### q-code-review-vs-testing

After your agent finishes the Delete button, Superpowers runs the tests and also sends the change
to a second agent for code review. What does the code review do that running the tests does not?

### q-catch-own-tests-are-review

A classmate says: "My agent ran the test suite on its own change and everything passed, so that
change has been code reviewed." What is wrong with what they said?

### q-review-no-findings

Your agent says: "I sent the Delete change for code review. The reviewer came back with no
findings, so I merged it." Which of these does that tell you?

1. The Delete button has been tested, since a code review runs the tests over the change.
2. Delete works, because someone read the code change and found nothing wrong with it.
3. Nothing was looked at: "no findings" means the review never ran.
4. Someone read the code change and found nothing wrong with it. Delete may or may not work.
