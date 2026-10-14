# alert

Answer in two or three sentences, in your own words, with nothing open in front of you.

Choirsheet is a community choir's app where members mark which rehearsals they will come to. Its
server and its database both run on a host called Lanternwell, and Lanternwell keeps Choirsheet's
server log, where the server records each error as it happens.

### q-catch-page-nobody-opens

Choirsheet's builder asked their agent to make sure they hear about problems on the live app. The
agent added an admin page to Choirsheet that counts the errors from the last hour and turns red
when there are more than five. The builder writes in their notes:

"Choirsheet has an alert now. If the app starts failing in the middle of the night, the admin page
goes red, so we'll know."

What is wrong with that?

### q-alert-vs-server-log

Lanternwell keeps thirty days of Choirsheet's server log, and the agent offers to set up an alert
as well. The builder asks why: the server log already has every error in it. What is the
difference between Choirsheet's server log and an alert?

### q-alert-vs-health-check

Lanternwell runs a health check on Choirsheet: every minute it asks one of Choirsheet's addresses
whether the app still answers, and if it doesn't, restarts the app without telling anyone. The agent also offers to set up
an alert for when Choirsheet stops answering. What is the difference between the health check and
that alert?
