# Untyped Plutus Core Optimizing Debugger
Developer Experience Working Group Proposal #X

v0.1

## Preamble

Script size, cpu, and memory usage - are key concerns for cardano developers in all of the Plutus family of languages (PlutusTx, Plutarch, Helios, Imperator). Providing a tool which uses the existing plutus estimator/evaluator functions, the developer could be able to see which portions of their script create the most problems from a script budgeting perspective.


## Developer Experience Concerns
Optimization is a common task for the plutus developer, while automated tools such as Plutonomy acheive some optimizations, many products will acquire additional hand-tuning.  Additionally, these procedures do not follow optimization patterns from most common languages (TODO:Source).

## Proposed solution
a debugger tool that allows a user to step through their code and understand how their memory and cpu budgets get calculated will allow the most efficient use of developer time to resolve the most egregious problems first.

This debugger could utilize the existing CEK machine operations.  this would allow for a script to be optimized at the UPLC level, though most developers do not write UPLC directly.  Instead, by targetting the UPLC artifact - the system can be paired with sourcemaps to aid not just PlutusTx developers, but Plutarch, Helios, Imperator, and other alternative Cardano scripting languages.

## Additional Reading
TODO
