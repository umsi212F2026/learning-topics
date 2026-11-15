### q1

Tomas is treasurer of a community choir, and members email the choir's inbox, where anyone can
write, to be paid back for things they bought for the choir. Each Sunday a program Tomas wrote
saves every new message from that inbox into a folder called requests, and then the reimbursement
agent, following a skill file Tomas wrote, reads each request, looks through the choir's bank
account history to see whether it has already been paid, and writes the unpaid ones into a file
called to-pay. To get the account history it uses the choir's bank token, saved in a settings file
in Tomas's home folder, which lets its holder see the account's transactions and also send payments
from it. Tomas started the agent with its harness's default settings, as himself in his home
folder, so it can read and change every file there, run shell commands and reach the internet. The
agent reads the skill file, the requests, each written by whoever sent it, and the account history
the bank sends back. Tomas pays each item on the to-pay list himself, from his phone, without
rereading the requests.

The harm Tomas is worried about: a hidden line in a request makes the agent use the bank token to
send a payment from the choir's account to the sender.

His agent proposes: "I can swap the bank token in the settings file for a scoped token that can
only see the account's transactions."

#### a

Would this limit significantly reduce the risk of this harm?

1. Yes
2. No

#### b

Could the reimbursement agent still do its work under this limit?

1. Yes
2. No
