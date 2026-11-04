Shape `poll-best`, variant `cant-be-reached`, case `poll`. The natural method is polling for new
requests every so often, ten minutes being well within what the facts allow. The source can send
word ("The website can send a notice each time a request comes in"), but the machine that does the
work can't receive it: "notices need a web server to arrive at, and the office computer doesn't run
one." Polling works ("can fetch the list of requests from the website") and the result can wait ("A reply within the hour is fine"), so a check
every ten minutes serves. The paragraph says nothing about when any machine is on. The neutral sentence is "The reply
is a short note with a picture of ballet shoes." Two polling, two webhook.

### q1

- **goal:** `c-choose-noticing`
- **cases:** poll
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** Sound (2): notices need a web server to arrive at, and the office computer
  doesn't run one, so the website's notices would have nowhere to arrive; that is what separates
  polling from a webhook here. Polling only needs the office computer to reach out to the website. 1 is the other method:
  it is true that the website can send a notice each time, but nothing can receive it. 3 is the
  other method: a reply within the hour is fine, but that doesn't rescue a webhook, whose notices
  still have nowhere to arrive. 4 is not a difference: the picture of ballet shoes bears on nothing
  about how new requests are found. If the learner picks 1, ask where the website's notice would
  go.
