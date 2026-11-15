Devika wants a campsite for one August weekend at any of four state parks near her.

- Every night at 2 a.m. a saving program saves each park's campsite availability page from a park reservations site into the campsites folder. When a page won't load, the program writes a line saying so to a problems file in the workflow's folder, and puts a line at the top of the campsites list saying the problems file has something new.
- Then the assessing agent, following a skill file Devika wrote, reads each saved page and adds an entry to the campsites list for each open site, rated 'book it' or 'pass' against her dates and the kind of site she wants.
- Then the details program pulls each open site's nightly price and its open nights out of the saved page and writes them into that site's entry.
- Each morning before work, Devika reads the campsites list from the top.

On Wednesday night one park's page wouldn't load, so the saving program wrote a line saying so to the problems file and went on to the next park.

### q1

Would this mistake be noticed?

1. Yes, it would be noticed.
2. No, a silent failure: the step can tell something went wrong, but no one would hear about it.
3. No, a silent failure: the result looks like a right one, and nothing in the workflow would catch it.
