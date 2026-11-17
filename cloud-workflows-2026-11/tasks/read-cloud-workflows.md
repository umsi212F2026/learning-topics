# Where the agent runs, and who pays

In Problem Set 5 you built a workflow on your own laptop, with at least one step done by an agent
following a skill file. It ran under your account, on your machine, for you. What if you wanted other people to be able to use it? Or what if you wanted to add an agent to the app you deployed for Problem Set 3?

The moment you want a workflow to run in the cloud, or be used by other people, a question you never had
to ask for PS5 comes up. When someone else runs the workflow, where does the agent step run, and who pays
for it?

This page is about that one decision. It doesn't re-teach putting a web app online; the hosting,
deploy config, deploy pipeline and database hosting topics covered that. It lays out five alternative plans for
the agent step and what each does to four goals: cost, privacy, access and correctness.

## Nadia's workflow

Nadia is looking for an apartment. On her laptop she built a workflow that collects new rental
listings each morning. An agent, following her skill file, reads each listing, pulls out the rent,
the address and the move-in date, and then judges it against her notes: her budget, her commute,
her cat, and the roommate she hopes to move in with. She reads the agent's top five over coffee.

Her friends want it. Then the housing group at her university, about 200 students, hears about it.
Most of them would want to run it a few times a week. A handful, in a hurry to find a place, would run it
every hour. Some have laptops and a paid subscription to ChatGPT or Claude; many have
neither. Some search only on their phones. And everyone's notes say things about them that they might want to keep private: what they earn, who they live with, where they work.

## Five alternative plans

Here are five ways the agent step could run once other people use it.

1. **Each user runs it on their own machine, under their own subscription.** This is what Nadia
   does now. The coding agents from OpenAI and Anthropic can sign in with a chat subscription, so
   the agent step is covered by what the user already pays each month, within its limits. Each
   friend would copy the workflow and the skill file onto their laptop and run it there.

2. **It runs in the cloud, on each user's own API key.** Nadia puts the workflow online as a web
   service. An **API key** is a secret a program sends with each request to a model company like OpenAI or Anthropic. It tells the company whose account to bill. 
   This approach is called **BYOK** ("bring your own key"): each user gets
   their own API key from a model company and gives it to Nadia's service, so the model calls made
   for them are billed to them. A chat subscription generally does not cover these calls: both OpenAI and
   Anthropic bill use of their API separately from their chat plans.

3. **It runs in the cloud, and the service pays a model company.** Nadia's service uses one API key,
   hers, for everyone. Model companies charge for API calls by **usage-based pricing**: so much per
   amount of text sent and returned, so the bill grows with every run, whoever made it.

4. **The service runs an open-weight model on servers it pays for.** An **open-weight model** is one
   whose trained weights, the numbers that make up the model, are published, so anyone may download
   it and run it on hardware of their choosing. Several companies publish such models. Nadia would
   rent a server able to run one, and no model company would be involved at all.

5. **An open-weight model runs in each user's browser.** Small open-weight models can now run inside
   a web page, on the user's own device, using a browser feature called WebGPU. Nadia's page would
   download the model to each visitor's device, and the agent step would run there.

Stop here before reading on, and answer for yourself ("I don't know yet" is an honest answer):
if Nadia's service runs the step for all 200 students, does plan 2 or plan 3 cost Nadia less?

## Cost

Under plan 3, Nadia pays for every run, and the handful who run it every hour make most of the
runs. Under plan 2 their runs are billed to their own keys, and Nadia pays for none of them. So plan
2 costs Nadia less; the users carry their own cost. Plan 1 costs her nothing for the model
either, since each user's subscription pays.

Under plan 4, Nadia pays for the servers the model runs on instead of paying a model company per
token. Whether that costs her less than plan 3 depends on how well she sizes the servers to the
runs, which takes care. Plan 5 costs Nadia almost nothing for the step, since the users' own devices do the work.

Cost to the users is a different question, and it turns on how the compute is priced. Use of an API
key is billed per token, so every run adds to the bill. A subscription costs a fixed amount each month
however much it is used, up to its limits. So for someone who already pays for a subscription and doesn't hit the limits, another run costs nothing extra. At the limits OpenAI and Anthropic currently set, a subscription used heavily
buys far more model use than the same money would buy at API prices. We discovered that in this course, when we found that a $20/month subscription was enough to use OpenAI's Sol model for all the interactions and problem sets while $50/month in token credits using a university-provided API key was not enough even when using the much less capable Astra model.

So for one of Nadia's hourly
users who already has a subscription, plan 1 costs far less than plan 2. For a student who would
run it twice a month and has no subscription, the reverse holds: a few runs on an API key cost much
less than a month of a subscription bought just for this.

## Privacy

For privacy, ask one question about each plan: besides the user, who sees the data the agent step
reads?

- Plan 1: the model company the user subscribes to. Nadia's service never sees it, because there is
  no service.
- Plans 2 and 3: Nadia's service, and the model company. BYOK changes who is billed, not who sees the
  data, so on privacy these two do about as well.
- Plan 4: Nadia's service only. No model company sees it.
- Plan 5: nobody. The data stays on the user's device.

A plan does better on privacy when fewer parties see the data. When a model company does see it, its
**data retention** policy promises how long it keeps what was sent before deleting it. OpenAI and
Anthropic both publish such policies for their APIs: As of November 2026 by default they keep what is sent for a limited
number of days and they say they don't train their models on it. They offer some customers
arrangements under which nothing is kept. Short retention is better than long, but a company that
keeps a prompt for a day has still seen it.

Those promises are for the API. Plan 1 runs under a chat subscription, which is a consumer plan with
rules of its own: on both companies' consumer plans, the user's settings decide whether what they send
may be used to train models, and on some plans it may unless the user turns that off. So plan 1 does
better than plans 2 and 3 on privacy for a user who has turned training off. For one who hasn't, the
model company may keep what it saw and learn from it.

One more thing decides privacy: whose data it is. If the agent step read only public listings and
nobody's notes, every plan would do about as well, because there would be nothing private to see.

## Access

Access asks how many of the people who might want to use the workflow can actually start it and see its
results.

Plan 1 works only for someone with a laptop, a subscription and the patience to set the workflow up
themselves. Plans 3 and 4 work for anyone with a web
browser, phones included, so on access they do about as well as each other, and for Nadia's group both beat plan 1. If every user had a laptop and a subscription and had already set the workflow up, plan 1 would
do about as well as they do. Plan 2 also runs
in a browser, but each user must first create an account with a model company, add a payment method
and get an API key. Plan 5 needs a device recent enough to run the model,
and the first visit means downloading hundreds of megabytes or more; recent versions of the major
browsers support WebGPU, but not every device does.

## Correctness

The best open-weight models are less capable than the best models the model companies sell, and the
small ones that fit in a browser are less capable still. That sounds as though plans 4 and 5 always
lose on correctness. But sometimes a step doesn't need the most capable model.

Suppose Nadia tried an open-weight model on a week of listings. It pulled out the rent, the address and the
move-in date as reliably as the model she uses now. On that step the two plans seemed to do about as well. It
was noticeably worse at the judging step, weighing a listing against everything in her notes. On
that step a model company's model did better.

## Weighing a plan

"About as well" is often the honest answer, and not only on correctness. Two plans can tie on cost
when their bills come out close, on privacy when the same parties see the data, and on access
when both run in a browser. Saying so is part of weighing plans well.

Often, no plan wins on every goal. Plan 5 does best on privacy and worst on correctness for Nadia's judging
step. Plans 3 and 4 are easiest to reach, and plan 3 puts every heavy user's runs on Nadia's bill. Once you know
which goal matters most for your project, and the facts about your users and their data, you can say
which of two plans does better on it, or that they do about as well. 
