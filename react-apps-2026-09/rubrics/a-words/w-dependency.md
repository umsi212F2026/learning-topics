# Rubric: dependency

### q-define-dependency

- **type:** free
- **goal:** w-dependency
- **move:** DEFINE
- **answer:** a dependency is somebody else's code that your project relies on and lists, so that
  `npm install` can fetch it into that project's `node_modules` folder. React itself is one, and
  the project will not run without the ones it lists.
- **credit:** full credit for saying it is outside code the project relies on and lists, fetched
  into the project by npm install. No credit for "a package", which is another name for it. Half
  credit for "something the project needs" with nothing about it being other people's code brought
  into the project. Do not accept "a program you install on your computer", and do not accept a
  file of your own that the project uses.

### q-dependency-vs-installed-program

- **type:** free
- **goal:** w-dependency
- **move:** DISTINGUISH
- **answer:** a program like Chrome is installed once on the machine, belongs to the machine, and
  you open it yourself. A dependency belongs to one project: `npm install` fetches it into that
  project's `node_modules`, another project of yours needs its own copy, and anyone else who gets
  your project runs `npm install` to fetch the same ones for themselves. You never open a
  dependency; the project uses it.
- **credit:** full credit for the per-project point: a dependency is fetched into one project's own
  folder and other projects need their own, while an installed program sits on the machine and is
  available to everything. Half credit for "one is for the project and one is for your computer"
  with nothing following from it. Do not accept a difference of size, "one is code and one is an
  application", or "one is free".

### q-agent-added-dependency

- **type:** free
- **goal:** w-dependency
- **move:** INTERPRET
- **answer:** the project now relies on somebody else's code, date-fns, for formatting dates: it
  has been added to the list of things the project depends on, and `npm install` has fetched it
  into this project's `node_modules` so the app can use it. Nothing was installed on your computer
  as a program, and only this project has it.
- **credit:** full credit for both: the project now depends on an outside package, and it has been
  fetched into this project so the code can use it. Half credit for "it added a library" with
  nothing about it belonging to this project. No credit for reading it as a program installed on
  your laptop, as something for you to open, or as code the agent wrote itself.
