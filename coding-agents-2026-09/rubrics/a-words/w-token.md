# Rubric: token

### q-define-token

- **type:** free
- **goal:** w-token
- **move:** DEFINE
- **answer:** a token is the unit of text that models count and charge in: text is chopped into
  pieces, roughly the size of a short word or a part of a longer one, before it goes to the model,
  and everything sent and everything written back is measured in those pieces. So 412,000 is a count
  of chunks of text, not of words, letters or messages.
- **credit:** full credit for saying a token is the unit text is counted and billed in, a chunk of
  text around the size of a word or smaller. Full credit for "a piece of a word, and what usage and
  prices are counted in" without mentioning billing. Half credit for "a piece of text" with nothing
  about counting or pricing. No credit for "a token is a word", for "a token is a message or a turn",
  or for reading it as an access token or API key.

### q-token-vs-word

- **type:** free
- **goal:** w-token
- **move:** DISTINGUISH
- **answer:** a word is a unit of language; a token is the unit the model's software splits text
  into and counts, and the two do not line up one to one. A common short word is usually one token,
  a long or unusual one is several, and spaces, punctuation and code symbols are counted too. That
  is why a bill or a usage figure in tokens cannot be read off a word count.
- **credit:** full credit for saying tokens are the counted and billed unit and do not correspond
  one to one with words: a word can be several tokens, and punctuation counts. Full credit for an
  answer that gives the rough ratio (a token is a bit under a word in English) as long as it says
  the two counts differ. Half credit for "a token is about the same as a word" with nothing about the
  counts differing. No credit for incidental differences, such as tokens being "what computers use
  and words being for people", with nothing about counting, or for "a token is a sentence".
