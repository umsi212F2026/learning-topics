Emeka keeps his household's receipts in order for his taxes, and he wants the receipts that shops email him turned into one sheet. His workflow has two steps.

- Each evening the collector, a program, signs in to Emeka's email account, downloads the receipts that shops emailed him that day, and saves them in a folder called receipts.
  - His home folder holds the skill file, the receipts folder, the tax sheet, his family photos, his past tax returns, a scan of his passport and a settings file where the collector's email token is saved.
  - Its token, saved in that settings file, reads his messages and sends mail as him.
- Then the sorting agent, following a skill file Emeka wrote, reads each new receipt, which the shop that sent it wrote, and adds a row with its date, shop, amount and tax category to a file called the tax sheet.
  - His home folder holds the skill file, the receipts folder, the tax sheet, his family photos, his past tax returns, a scan of his passport and a settings file where the collector's email token is saved.
  - It holds no logins, keys or tokens of its own.

### collector-reach

Can the collector reach anything its step does not need?

1. Yes
2. No

### sorting-agent-reach

Can the sorting agent reach anything its step does not need?

1. Yes
2. No

### sorting-agent-context

Does untrusted input end up in the sorting agent's context while it does its step?

1. Yes
2. No
