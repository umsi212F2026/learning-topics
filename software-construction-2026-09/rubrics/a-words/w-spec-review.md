# Rubric: spec compliance review

### q-define-spec-review

- **type:** free
- **goal:** w-spec-review
- **move:** DEFINE
- **answer:** the review that holds the finished change up against what was asked for: was
  everything in the request or the plan actually built, does it behave the way the request said,
  and was anything built that nobody asked for. It is about matching the request, not about how
  good the code is.
- **credit:** full credit for "it checks whether the change does what was asked", or "whether it
  matches the plan or the spec". Adding "and nothing extra" is a good addition and is not required.
  Half credit for "it checks the work is correct" with nothing about the request or the plan. No
  credit for "a spec review", which is another name for it. No credit for an account of code
  quality (readable, efficient, well structured), which is the other review.

### q-spec-vs-quality-review

- **type:** free
- **goal:** w-spec-review
- **move:** DISTINGUISH
- **answer:** the code quality review asks whether the code itself is any good: clear, sensibly
  organised, not repeating itself, not leaving a trap for the next change. The spec compliance
  review asks a different question entirely: does this do what was asked, all of it, and nothing
  that was not asked. A change can be beautifully written and answer the wrong request, or do
  exactly what was asked in an awful way, and each review catches one of those.
- **credit:** full credit for both questions: quality is about the code itself, spec compliance is
  about the match with what was requested. Half credit for one side named clearly and the other
  left vague. No credit for treating them as the same review run twice, for "one is stricter than
  the other", or for saying the spec review is the one that runs the tests.

### q-spec-review-passed

- **type:** free
- **goal:** w-spec-review
- **move:** INTERPRET
- **answer:** it tells you the change matches the plan the agent was working from, item by item,
  and that nothing was built beyond it. It leaves open whether that plan was what you actually
  wanted, whether the code is any good, and whether it works at all: matching a plan is not the
  same as behaving correctly, and a plan can faithfully describe the wrong thing.
- **credit:** full credit for both halves: the change matches the plan or request, plus at least one
  thing that leaves open (the plan may not be what you wanted, the quality is unjudged, or it may
  still not work). Half credit for the first half alone. No credit for reading it as "the tests
  pass", "the code is good", or "the app now does what I want" with no caveat.
