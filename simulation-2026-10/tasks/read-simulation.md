# Simulations, and the questions they answer

This page says what a simulation
is, what goes into one, and what kinds of question one can answer.

## What a simulation is

Suppose a tennis coach wants to know her player's chances of reaching the final of next month's
tournament. She can't have the player enter that tournament a thousand times to find out. She can
do the next best thing: describe how a tennis match works, precisely enough for a computer, and
have the computer simulate play of the tournament a thousand times.

That is a **simulation**: running a model of a process on a computer to see what the process would
produce. Each simulation trial generates synthetic data, made-up results that follow the model's rules. You analyze the data from many trials to answer a question. An experiment is different. An experiment runs the real process, with real players in real matches, and watches what happens. A simulation runs a description of the process instead.

## The model

That description is the **simulation model**: a simplified description of how a process works,
precise enough for a computer to run. A simple tennis model might say: on each point, the server
wins with a fixed chance, and otherwise the receiver wins; points make games, games make sets and
sets make matches, following tennis's scoring rules.

The model is not the real process it describes. Real players tire in the third set and tighten up
on big points; this model leaves that out. Every model leaves things out, keeping only what someone
decided matters. Those decisions can affect the simulation outcomes in big ways. A model in which each point is independent of the last can never show a player riding a wave of momentum, for example.

A **model parameter** is a value chosen before a simulation runs that the model's rules use. In
the tennis model, the parameters might be the chance the player wins a point on her own serve, the
chance she wins one on her opponent's serve, and how many sets a match lasts. Change a parameter
and the model behaves differently.

A **simulation outcome**, also called an **output measure**, is what a run produces that the
question cares about: how many tie-breaks were played in a simulated tennis match, how high the oceans rose in a simulation of global warming.
Parameters go in and outcomes come out. You choose the chance of winning a point on serve. You
don't choose whether the player reaches the final of the tournament: that is what the simulation outcome tells you.

## Chance, and why one run isn't enough

Some models have no chance in them. A **deterministic** model gives the same result every time it runs with the same parameters. A model of a savings account that grows by a fixed interest rate
each month ends at the same balance every time.

A **stochastic** model, also called a **probabilistic** model, has chance built into its rules, so
the same parameter settings can give different results on different runs. The tennis model is stochastic: each point is like
tossing a weighted coin. Play the same tournament twice with the same parameters, and the player
might reach the final the first time and lose in the third round the other time.

One **simulation trial** is one run of the model from start to finish, with its chance events drawn
afresh: one whole tournament, played point by point. Trials are also called **runs**,
**replications** or **iterations**. Every trial of a simulation uses the same parameters; only the
coin tosses differ. Changing a parameter and running again is something else. That is a new
setting, whose trials you might compare with the first setting's, not one more trial of the first.

With a stochastic model, one trial tells you almost nothing, any more than one real tournament
would. So you run many trials, thousands of them, and look at the **outcome distribution**: how
often each simulation outcome turns up across many trials with the same model parameters. Out of
10,000 simulated tournaments, perhaps the player reached the final in 2,300, lost in the semifinal
in 2,600 and went out earlier in the rest.

The average outcome is one summary of a distribution, but not the whole of it. Two players can win
the same number of matches on average while one is steady and the other swings between winning
tournaments and losing in the first round. If your question is about the spread, or about rare
results, the average hides what you want to know, so report at least the average and something about the spread (the standard deviation is a common thing to report).

Notice, too, that one trial's outcome is not the answer to the question. "She reached the final" is
one trial's outcome. "She reaches the final about 23% of the time" is the answer. It comes from
analyzing many trials' outcomes together.

## When to simulate

A simulation is not the only way to answer a what-if question. You could run an experiment, when
doing the real thing is cheap and safe, such as showing two versions of a sign-up page to real
visitors. You could use existing data, when the past already holds the answer. Or you could use a
formula, when the math is simple enough to work out directly.

Simulate when none of those will do: when the real thing is too slow, costly, dangerous or
impossible to run (nobody can rerun a century of floods); when the conditions you are asking about
have never happened, so there is no data; or when the process has so many steps, each depending on
the ones before, that the math gets out of hand. Tennis scoring, with its games, deuces, sets and
tie-breaks, is a good example of the last.

Simulation has a second use in software, generating test data or programs that pretend to be
thousands of users hitting an app at once, but that is not the use this page is about.

## Six kinds of question

What you do with a simulation depends on the question you ask of it. Most questions are one of six
kinds.

- **What outcomes are likely.** What are the player's chances of reaching the final? Run many
  trials at one setting and read the outcome distribution.
- **Whether something can happen at all.** Picture a model of a busy highway with no accident on
  it. Every driver follows sensible rules: keep a safe gap, and brake a little when the car ahead
  slows, by an amount that varies a little at random from driver to driver. Can a jam form with no
  accident, lane closure or other cause? It turns out it can. One driver's small slowdown makes the next brake
  a little harder, the slowdown grows as it passes back through the line of cars, and the jam
  travels backward. For a question like this, seeing it happen under the model is the answer; how
  often it happens matters less. The point is to show that it can happen at all without some external cause other than what's explicitly modeled.
- **Which option is better.** Should the player spend her prize money on serve coaching or on a
  sports psychologist? Run the model under different parameter settings and compare the two
  distributions.
- **What setting reaches a target.** How big an edge do servers need to have over returners for most sets to go to a tie-break? Change a parameter in small steps and look for the value at which the
  outcome reaches the target.
- **How bad things can get.** How high is the river's "100-year flood", the level it has a 1 in
  100 chance of rising above in any one year? Run thousands of simulated years and look at the rarest, most extreme outcomes,
  not the typical ones.
- **What would have happened if things had gone differently.** Would last season's champion still
  have won if the league had used a different scoring system? Replay the past season under the
  other rules.

The wording of a question can mislead about the right approach to simulation. A model with chance in it doesn't make every question one about likely outcomes: the highway's drivers brake by random amounts, and the question was whether a jam could form at all. "What if" can be about a choice still to be made ("what if
she hires the serve coach?") as well as about the past. And a question can mention the worst case
while asking something else, such as which option makes the worst case rarer. Think carefully about what you really want to learn from a simulation, what question you want to ask.

## When your agent builds one

An agent will build a simulation for you quickly, and it will produce numbers: a percentage, an
average, a chart. Using Superpowers, it will even generate a bunch of tests to rule out certain kinds of implementation mistakes. But there is no answer key for the original question, "how often does she reach the final?" If the agent's simulation says 23%, nothing outside it
says whether 23% is right, and a model with a mistake in it produces numbers that look just as
believable as a correct one.

So you have to understand what the agent built well enough to know what it should do. What does
the model include, and what does it leave out? What does each parameter mean, and what range of
values makes sense for it? What is one trial, and how many does it run? Then predict before you
run it. If the player wins every point on her own serve, she should never lose a game she serves.
If two players are evenly matched, each should win about half their matches. When the simulation
surprises you, either you have learned something surprising or the model is wrong. Your job will be to find out which.
