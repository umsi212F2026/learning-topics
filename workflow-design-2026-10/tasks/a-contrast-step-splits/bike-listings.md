A used-bike shop sells the bikes it takes in through listings on its own website, with a weekly
workflow. It takes in about 15 bikes a week.

1. Enter each bike taken in this week into the shop's inventory list, with its make, frame size
   and notes on its condition. (the shop's mechanic)
2. Suggest a price for each bike from what similar used bikes recently sold for, then set the
   final price of each bike, and pick which three bikes to feature on the website's front page
   this week. (an AI agent, then the shop owner)
3. Fill in each listing's make, frame size and final price, mark each listing shippable or pickup
   only by the shop's rule on frame size, then write a short, honest description for each listing.
   (an AI agent)
4. Post each listing on the shop's website. (a program)

Some of these steps do more than one step's work.

### q1

Hiro, Isabel and Jonah each propose splitting step 2 into two steps.

1. Hiro: split after the agent suggests a price for each bike, and hand those prices straight to
   the owner without storing them.
2. Isabel: split after the agent suggests a price for each bike, and keep the suggested price for
   each bike.
3. Jonah: split after the agent suggests a price for each bike, and keep the week's inventory list
   from step 1.

Which proposal is the best division of step 2?

1. Hiro's
2. Isabel's
3. Jonah's

### q2

Keiko, Luis and Maya each propose splitting step 3 into two steps.

1. Keiko: split after the agent marks each listing shippable or pickup only, and keep the
   filled-in listings with their marks.
2. Luis: split after the agent fills in each listing's make, size and price, and keep those
   filled-in fields for each bike.
3. Maya: split after the agent marks each listing shippable or pickup only, and keep a count of
   how many bikes are shippable.

Which proposal is the best division of step 3?

1. Keiko's
2. Luis's
3. Maya's
