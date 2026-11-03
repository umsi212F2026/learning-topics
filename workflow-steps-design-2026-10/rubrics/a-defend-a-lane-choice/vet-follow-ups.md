Step 2 is `messy-volume-checked`: natural choice an AI agent, alternative a person. Step 4 is
`judgment-few-costly`: natural choice a person, alternative an AI agent. Rule on the reasons,
never on the choice: any executor defended by reasons tied to the step's facts passes.

Where the facts are. The setup's second sentence gives step 2's volume: about 150 replies a week.
In the manager's paragraph, sentences 1 to 3 carry step 2's facts: the replies are typed free text
of every length, and many cover two pets in one message, so a symptom can be put on the wrong pet
(sentence 1, its input); they mention the family's children by name (sentence 2, its data); a
wrong mark rarely gets past the technician at step 3 (sentence 3, what a mistake costs). Sentences
5 to 8 carry step 4's facts: four or five pets a week, each different in a way no rule settles
(sentence 5, its input); the technician's notes record the owner's money troubles, such as a
payment plan (sentence 6, its data); a wrong "wait" can cost the family well over a thousand
dollars at the emergency hospital, and nobody looks at the decision again (sentence 7, what a
mistake costs); Dr. Okafor decides these only in the late afternoon (sentence 8, when the
decider is free).

The irrelevant details, one per open step: for step 2, that the clinic has used the same texting
service since 2015 (sentence 4); for step 4, that the recheck room was repainted (sentence 9). A
reason resting on either is not tied.

### q1

- **goal:** `c-assign-a-lane`
- **answer:** An AI agent rather than the technician or another staff member. It helps
  timeliness or cost: about 150 replies a week, typed in owners' own words from a thumbs-up to
  three paragraphs, would take a staff member hours to read and mark. It hurts privacy: the replies
  name the family's children, and those names would go to the agent's provider; or it hurts
  correctness: a reply about two pets invites the agent to put a symptom on the wrong pet (a slip
  the technician rarely misses at step 3, which is also a tied reason the agent's mistakes are
  tolerable here). Other pairings that pass:
  - A staff member rather than an agent: helps privacy (the children's names stay in the clinic)
    or correctness (a staff member can tell, or ask, which pet a symptom belongs to); hurts
    timeliness or staff time (about 150 typed replies a week).
  - An agent rather than a program: helps correctness (free-text replies in owners' own words,
    which a program can't mark reliably); hurts privacy (a program keeps the children's names
    in-house) or cost (an agent costs more per run).
  - A program rather than an agent: helps privacy (the children's names go nowhere) or cost;
    hurts correctness (free text of every length, so many replies would get the wrong mark and the
    technician would spend step 3 fixing them).
  - A staff member rather than a program: helps correctness (reading free text and sorting out
    the two-pet replies); hurts timeliness (the volume).
  - A program rather than a staff member: helps timeliness (the volume); hurts correctness (free
    text a program can't read).
- **credit:** full when the answer chooses an executor for step 2, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the replies being typed free text, their volume, the
  two-pet replies, the children's names, or the technician's review at step 3 that catches a wrong
  mark. A reason is tied when it refers to this step: "an agent marks these replies faster than
  the technician could" is tied; after ruling, the tutor says it would be stronger naming what
  about the replies makes speed matter, asks for that, and if the learner can't say, points to the
  volume and the free-text replies of every length. Generic reasons, which don't refer to the step
  at all: "an agent is cheaper", "a person is accountable for judgments", "a person has better judgment", "agents can be wrong in ways that
  look right". A reason resting on the texting service the clinic has used since 2015 is not tied.
  An intermediate goal from the reading counts as a goal helped or hurt when its reason is tied to
  a fact here. Half when one of the two is tied and the other is generic or missing, or when both
  are tied but no alternative is named. None when neither is tied, or no executor is chosen.
- **tutor note:** a learner who says the replies are health information and so private has
  pointed at the pets' health; ask whose details in these replies would be going to the provider,
  and accept the children's names, or the pets' health if the learner ties it to these replies.

### q2

- **goal:** `c-assign-a-lane`
- **answer:** A person, Dr. Okafor, rather than an AI agent. It helps correctness: each of the four
  or five cases is different in a way no rule settles, and a wrong "wait" can send the family to
  the emergency hospital at well over a thousand dollars, with nobody looking at the decision
  again; or it helps privacy: the notes on the owner's money troubles stay in the clinic. It hurts
  timeliness: the decisions wait until late afternoon between surgeries, so a worried owner hears
  later; or it costs Dr. Okafor time she has little of between surgeries. Other pairings that pass:
  - An agent rather than Dr. Okafor: helps timeliness (it decides as soon as the call notes are
    in, not late in the afternoon); hurts correctness (each case is different and a wrong "wait"
    goes out unchecked, at a cost of over a thousand dollars to the family) or privacy (the notes
    on payment plans and what owners can afford go to the provider).
  - A person rather than a program: helps correctness (no rule could settle a dog that eats but
    limps, or what to do for an owner who can't afford another visit); hurts timeliness (late
    afternoon) or the vet's time.
  - A program rather than a person: helps timeliness (it decides at once); hurts correctness (each
    case is different, and a rule's wrong answer goes out unchecked).
  - An agent rather than a program: helps correctness (it can read each case's call notes and
    weigh what the owner can afford); hurts privacy (those money notes go to the provider) or cost.
  - A program rather than an agent: helps privacy (the money notes stay in-house) or cost; hurts
    correctness (no rule fits cases this varied).
- **credit:** full when the answer chooses an executor for step 4, names one alternative, and
  names a goal the choice helps and a goal it hurts compared with that alternative, each with a
  reason tied to a fact about this step: the few cases, each different; the notes on the owner's
  money; a wrong decision costing the family over a thousand dollars with nobody looking again; or
  Dr. Okafor being free only in the late afternoon. A reason is tied when it refers to this step:
  "Dr. Okafor makes better calls on these pets than an agent would" is tied; after ruling, the
  tutor says it would be stronger naming what about these cases makes judgment matter, asks for
  that, and if the learner can't say, points to each case being different and a wrong "wait" going
  out unchecked. Generic reasons, which don't refer to the step at all: "a person is accountable for judgments",
  "a person has better judgment", "an agent is faster", "agents can be wrong in ways that look right". A reason resting
  on the repainted recheck room is not tied. An intermediate goal from the reading counts on the
  same terms: "keeping the money notes away from a provider is least privilege for this step" is
  tied; "least privilege" alone is generic. Half when one of the two is tied and the other is
  generic or missing, or when both are tied but no alternative is named. None when neither is
  tied, or no executor is chosen.
- **tutor note:** a learner who says Dr. Okafor hurts nothing has missed when she is free; ask
  when a worried owner would hear back.
