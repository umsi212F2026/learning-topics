Step 3 is `structured-irreversible`: natural choice a program, alternative an AI agent. Step 4 is
`judgment-few-costly`: natural choice a person, alternative an AI agent. Rule on the reasons,
never on the choice: any executor defended by reasons tied to the step's facts passes.

Where the facts are. The setup's second sentence gives step 3's volume: about sixty donations in
a normal week. In the manager's paragraph, step 3's facts are in sentences 1, 4 and 5: the approved
list has one line per donation in a fixed form, with each donor's home mailing address (sentence
1, its input and its data); a few lines a week are marked "CAD", with the amount in Canadian
dollars (sentence 4, the odd entries); a receipt for the wrong amount is a tax record the donor
files and the nonprofit reports, and nobody checks it once it's mailed (sentence 5, what a mistake
costs). Step 4's facts are in sentences 2, 3, 6 and 7: two or three letters a week, most of them
settled by no policy (sentence 2, its input); the letters explain a layoff, a divorce or a death
in the family (sentence 3, its data); a wrong refusal can leave a donor out several hundred dollars
they badly need, and the reply goes out with no second reader (sentence 6, what a mistake costs);
the director answers these only on Thursday afternoons (sentence 7, when the decider is free).

The irrelevant details, one per open step: for step 3, the envelopes with the children's logo
(sentence 8); for step 4, the motto the director signs with (sentence 9). A reason resting on
either is not tied.

### q1

- **goal:** `c-assign-a-lane`
- **answer:** A program rather than an AI agent. It helps correctness: it puts exactly the amount
  on the approved line on each receipt, every time, and a wrong amount is a tax record the donor
  files and nobody checks once it's mailed. It hurts timeliness or someone's time: the few "CAD"
  lines a week will stop it, and someone has to convert those amounts by hand before their
  receipts go out. Other pairings that pass:
  - An agent rather than a program: helps timeliness (it can convert a "CAD" amount and keep
    going); hurts correctness (it may convert or copy an amount wrong, on a tax record nobody
    rechecks) or privacy (the donors' home addresses go to the agent's provider).
  - A program rather than a staff member: helps timeliness or staff time (about sixty receipts a
    week, more in December, made by hand otherwise) or correctness (no copying slip on a tax
    record nobody rechecks); hurts timeliness on the "CAD" lines it stops on.
  - A staff member rather than a program: helps correctness or timeliness on the "CAD" lines (a
    staff member can convert them on the spot); hurts timeliness or staff time (the volume) or
    correctness (a copying slip goes out unchecked).
  - An agent rather than a staff member: helps timeliness (the volume); hurts privacy (the home
    addresses go to the provider) or correctness (a misread amount on an unchecked tax record).
  - A staff member rather than an agent: helps privacy (the home addresses stay in the office);
    hurts timeliness (the volume).
- **credit:** full when the answer chooses an executor for step 3, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the approved list's fixed form, the "CAD" lines, the home
  addresses, the volume, or a wrong amount on a tax record nobody checks again. A reason is tied
  when it refers to this step: "a program gets these receipts out sooner than staff could" is tied;
  after ruling, the tutor says it would be stronger naming what about the receipts makes that
  hold, asks for that, and if the learner can't say, points to the approved list's fixed form and
  its sixty lines a week. Generic reasons, which don't refer to the step at all: "programs don't
  make mistakes", "a program costs almost nothing to run", "an agent is cheaper than paying
  staff". A reason resting on the envelopes the children's logo is printed on is not tied. An
  intermediate goal from the reading counts on the same terms: "a program fails loudly on the CAD
  lines instead of guessing the amount" is tied; "a program fails loudly" alone is generic. Half
  when one of the two is tied and the other is generic or missing, or when both are tied but no
  alternative is named. None when neither is tied, or no executor is chosen.
- **tutor note:** a learner who says a program hurts nothing has missed the "CAD" lines; ask what
  a program would put on the receipt for a line marked "CAD".

### q2

- **goal:** `c-assign-a-lane`
- **answer:** A person, the director, rather than an AI agent. It helps correctness: each of the
  two or three letters is one no policy settles, and a wrong refusal can leave a donor out several
  hundred dollars they badly need, with no second reader; or it helps privacy: the letters' layoffs,
  divorces and deaths stay in the office. It hurts timeliness: the director answers only on
  Thursday afternoons, so a donor who wrote on Friday waits most of a week; or it takes her one
  office day. Other pairings that pass:
  - An agent rather than the director: helps timeliness (a reply the day a letter arrives, not the
    next Thursday); hurts correctness (no policy settles these, and a wrong refusal goes out with
    no second reader) or privacy (the letters' personal troubles go to the provider).
  - A person rather than a program: helps correctness (no rule could weigh a lost job against a
    pledge paid up front); hurts timeliness (Thursday afternoons) or the director's time.
  - A program rather than a person: helps timeliness (it answers at once); hurts correctness (a
    rule's answer to a case no policy settles goes out unchecked).
  - An agent rather than a program: helps correctness (it can read each letter's circumstances);
    hurts privacy (the layoffs, divorces and deaths go to the provider) or cost.
  - A program rather than an agent: helps privacy (the letters stay in-house) or cost; hurts
    correctness (no rule fits letters this varied).
- **credit:** full when the answer chooses an executor for step 4, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the few letters no policy settles; the layoffs, divorces
  and deaths they explain; a wrong refusal costing a donor several hundred dollars with no second
  reader; or the director being free only on Thursday afternoons. A reason is tied when it refers
  to this step: "an agent would answer these donors sooner than the director" is tied; after
  ruling, the tutor says it would be stronger naming what about the step makes the wait matter,
  asks for that, and if the learner can't say, points to the director answering only on Thursday
  afternoons. Generic reasons, which don't refer to the step at all: "a person is accountable for judgments",
  "a person has better judgment", "an agent is faster", "agents can be wrong in ways that look right". A reason resting
  on the motto the director signs with is not tied. An intermediate goal from the reading counts
  on the same terms as a final goal. Half when one of the two is tied and the other is generic or
  missing, or when both are tied but no alternative is named. None when neither is tied, or no
  executor is chosen.
- **tutor note:** a learner who argues the director from accountability alone ("she's responsible
  for the money") has given a reason that holds for any step; ask what about these letters makes
  her the one who should answer them.
