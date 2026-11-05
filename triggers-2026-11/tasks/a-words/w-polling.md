# Polling

### vs-hook

A bakery takes orders through an online shop, and wants a program in its kitchen to print each new
order as soon as it is placed. The kitchen program could ask the shop every two minutes whether
any new orders have come in. Or the bakery could use a setting the shop offers: a web address the
shop sends a message to each time an order is placed.

Which of these two ways is polling, and which uses a hook? Answer in one sentence.

### catch-pick

A hiking club keeps its sign-up sheet in a shared spreadsheet, and new members add themselves as
a new row. Every 15 minutes a script opens the spreadsheet, looks for rows it hasn't seen before,
and emails each new member a welcome.

In this workflow, what is polling?

1. The script checking the sheet every 15 minutes
2. Nothing; polling would be the sheet telling the script
3. The script emailing each new member a welcome
4. Nothing; polling would be checking nonstop

### catch-build

A team keeps its code on a code-hosting site and has a build server that builds the code after
every change. One of them says:

"Our build server polls the code site: the site sends the server a message each time someone
pushes a change, and a build starts."

What is wrong with that? Answer in two or three sentences, in your own words.
