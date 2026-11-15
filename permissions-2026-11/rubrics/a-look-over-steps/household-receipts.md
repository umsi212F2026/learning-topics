Medium. A household's receipts for taxes, not a tracker, with two executors: the collector (a program) downloads the receipts shops email Emeka, and the sorting agent turns each one into a row of his tax sheet. Neither executor has anything narrowing it, against steps that each use one folder or file and, for the collector, one email account it only reads. The sorting agent reads receipts the shops wrote. This scenario carries one reach case (`excess`) and one context case (`outside-text`). Each question asks what the step does as described, not what could go wrong next or how to fix it.

### collector-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Emeka can. Its step signs in to his email account, downloads the day's receipts and writes them into the receipts folder ("signs in to Emeka's email account, downloads the receipts that shops emailed him that day, and saves them in a folder called receipts"). Its token also sends mail as him ("Its token ... reads his messages and sends mail as him"), and its step only reads messages. It can also read and change his family photos, his past tax returns, his passport scan and the tax sheet ("His home folder holds ... the tax sheet, his family photos, his past tax returns, a scan of his passport"); it can run shell commands, though its step runs no named program; and it can reach the internet beyond his email site. Follow-up's answer: sending mail as him, his other files, shell commands, and sites beyond his email site.

### sorting-agent-reach

- **goal:** `c-spot-excess`
- **cases:** excess
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. Nothing narrows it (no limit is stated), so by the reading's rule it can do whatever Emeka can. Its step reads the new receipts and writes rows into the tax sheet ("reads each new receipt ... and adds a row ... to a file called the tax sheet"). It can also read and change his family photos, his past tax returns and his passport scan, and read the settings file with the collector's email token, which would let it read his messages and send mail as him ("His home folder holds ... his family photos, his past tax returns, a scan of his passport and a settings file where the collector's email token is saved"); it can run shell commands, though its step runs no named program; and it can reach the internet, though its step works on receipts already saved on the laptop. Follow-up's answer: the photos, the past tax returns, the passport scan, the email token and what it lets one do with his account, shell commands, and the internet. A learner who says no because it holds no token of its own should be asked what is in the settings file it can read.

### sorting-agent-context

- **goal:** `c-spot-injection`
- **cases:** outside-text
- **type:** mcq
- **answer:** 1
- **credit:** full for 1; none for 2.
- **tutor note:** Key: Yes. It reads two things: the skill file, which Emeka wrote ("following a skill file Emeka wrote"), and each new receipt, which the shop that sent it wrote ("reads each new receipt, which the shop that sent it wrote"). The collector saves the receipts as downloaded, so the agent reads the shops' own words. Follow-up's answer: the receipts the shops emailed him.
