# Rubric: deploy

If the learner misses a question here, set a DEFINE or INTERPRET move for deploy live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

To deploy is to put the app where anyone's browser can reach it. The confusable is build, which
turns your code into what gets sent to the hosts and leaves it on your own machine. "Ship" and "go
live" mean the same as deploy and are not confusables.

### q1

- **goal:** `w-deploy`
- **move:** DISTINGUISH
- **answer:** Building turns the code into what gets sent to the host (for a React frontend, the
  files in `dist/`), and those files are still only on your machine, where nobody else can reach
  them. Deploying puts them on a host where anyone's browser can reach the app. You can build
  without deploying, and a deploy sends what a build made.
- **credit:** full for the difference that matters: a build makes what gets sent, and only a
  deploy makes the app reachable by other people. Half for one half only (for example, "deploying
  puts it online" with nothing on what a build is). None for an incidental difference alone, such
  as that one is a command and the other a button, or that one takes longer.

### q2

- **goal:** `w-deploy`
- **move:** CATCH
- **answer:** `localhost` is the student's own machine, so only their own browser can open the app.
  Deployed means on a host where anyone's browser can reach it, and nobody else can reach this.
- **credit:** full for naming that the app is reachable only from the student's own machine, while
  deployed means anyone's browser can reach it. Half for "it's only running locally" without saying
  why that falls short of deployed. None for a different quibble alone, such as that `npm run dev`
  is a dev server rather than a build, or that they should have run the build first.
- **tutor note:** a learner who says "they need to build it first" has named a step, not the error;
  ask who else could open that address right now.
