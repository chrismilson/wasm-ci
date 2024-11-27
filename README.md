# WASM-WF

Why? Contrived reason that would be convincing: Existing CI/CD/Pipeline/Workflow solutions (hereonout referred to as workflows and workflow frameworks) fit into a couple of categories:

- Can't run complex distributed tasks
- Reusable parts of workflows have limited compatibility guarantees

They often have a bunch of different levels of abstraction: self contained tasks that do a single thing and run sequentially (and are hopefully incredibly reusable), jobs or collections of tasks that run concurrently with other jobs, stages or collections of jobs that run concurrently with other stages.

Tasks often have outputs, but they are not stongly typed - so no intellisense when composing them into jobs or stages. The limited interface on tasks potentially makes it an insurmountable task for workflow frameworks to provide any better interfaces on jobs and stages.

The idea with this project is to force the user to define tasks as wasm modules, that will need to implement concrete interfaces to provide these much needed compatibility guarantees at higher levels.

Actually why? I would like to give it a try. Think of all the candy(!):

- distributed system
- plugin interfaces
- intellisense on workflow definitions

I may very well be crazy!

## PoC

As with any new project, this will die unless scope is ruthlessly defined and pruned. Requirements:

- [ ] User can define arbitrary workflows
- [ ] Workflows are run in a distributed manner
- [ ] Workflow tasks are wasm modules
- [ ] Type checking when defining workflows

So not:

- Optional container/script/etc. task definitions
- UI for defining workflows
- (others to follow as extra potential scope is found...)
