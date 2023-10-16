# Annotated Specification & Documentation platform
Developer Experience Working Group Proposal #2
August 17, 2022

v0.1

## Preamble

"A Plutus Developer should not need to read the Plutus, Ouroboros, Ledger, or EUTXO specification in order to write production-worthy plutus code"

Currently a large amount of information about the workings of Cardano is exclusively available in spec documents. Often marked as a draft, these documents are hard to discover and search. Further, this documentation process means that little is known about ways that the current implementation may deviate from the specification.

Additionally many key features that have become cornerstones of how we tell developers to reason about ledger behavior (such as 'phase I' and 'phase II' transaction validation) are under-specified and arise as an emergent behavior in the implementation.

## Developer Experience Concerns
Providing key details through less accessible documentation is better than not providing them at all, however this slows the learning curve of developers, and discourages learners who either have accessibility problems with the documentation, or who were simply not directed to them to start with.

This has a concrete cost when hiring or training developers, as only the developers who can access the academic style of the specifications can succeed.

## Proposed solution
So far we've discussed the creation of a wiki or an 'Annotated Specification' which would allow community members to tag, or comment on subsections of the spec, perhaps linking or adding their own articles.

Leveraging community efforts is important, but we need to temper this with strong community moderation to ensure we prevent vandalism and are providing strong, factual documentation.


## Additional Reading
https://diataxis.fr/  - a strong description of cohesive documentation.

