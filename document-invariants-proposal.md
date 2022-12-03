
# Plutus Data Invariant Documentation Proposal
Developer Experience Proposal #1

v0.1 - August 17, 2022

## Preamble
The Official Plutus Haskell API contains makes use of a number of data types which currently can easily be constructed without any validation functions provided to ensure that this data is well-formed. In fact outside of the official specifications, often the correct format for these types are not documented anywhere.

This runs contrary to common practice in Haskell, which is to create clear and obvious constructors meant for parsing potentially hostile data into a known, trustable data type.

This is both confusing to developers, and a potential security threat in plutus contracts.

Fortunately, in many cases the solution is straightforward:

Plutus needs to document the best practices for working with these types on-and-offchain when they are supplied as potentially hostile user inputs, and to provide 'smart-constructor' functions for the purpose of performing these validations.

## Security Concerns
If the best practices and documentation do not direct developers toward validating these data types, what are the real-world consequences?

A smart contract might for example lock some funds unless a given PublicKey address is able to sign to retreive them.  If the Address is initially ill-formed, then no signature will ever satisfy the smart contract and the funds are permanently locked.

if the contract is a state-machine, other locked funds may also become permanently unavailable.

This forms a significant attack vector, as well as a very serious consequence for contract misuse if the address format is not verified onchain.

If the address can be parsed and verified to be well-formed onchain, then a programmer is able to handle the case where the contract is not well formed and create alternative behaviors.

## Developer Experience Concerns

Without these smart constructors, a developer must implement these themselves on each project. this represents a tremendous amount of duplicated effort, especially when we include testing coverage, API breakages, and bugfixing to each new implementation.

Developers looking at the current documentation would not necessarily know that this is a best practice without reading the spec.

When building tests, even more types need to be correctly constructed in such a way that they should be plausible. This encompasses the entire `ScriptContext` and its consituent parts.

These issues have also resulted in incorrect audit tooling based on plutus's provided API. This is costing developers and founders real money today.

## Proposed Solutions
### Phase I - Documentation
This should be relatively rapid as at the time of writing there is [an existing PR](https://github.com/input-output-hk/plutus/pull/4597/files) and a [public commitment](https://github.com/input-output-hk/plutus/issues/4476#issuecomment-1213360220) to merge the documentation from this PR on the relevant types.

We would like to see this documentation expanded to include all types used in scriptContext with invariants that can reasonably be checked (ie, excluding invariants that arise from chain-state or balancing).

### Phase II - Security Sensitive Validation Functions ('Smart-Constructors')
Providing validation functions onchain for commonly used data types with invariants is critical.

However, we recognize that not all validation functions are necessary onchain. Since functions intended to run onchain have a much higher maintenance overhead, we only ask that the following functions types be given vailidation functions onchain:
- PubKey 
- Address (and its constuents)
- POSIXTime 
- Signature 
- DatumHash
- CurrencySymbol
- TokenName
- TxId
- ValidatorHash
- Value
- PubKeyHash

These represent the most urgent types as these are the the data types which are most likely to be required onchain. 

### Phase III - Types needed for a strong testing workflow
off-chain validation is still an important step, as it will guide developers toward better testing workflows.

This work should seek to make it easier to construct a valid ScriptContext for the purposes of testing a smart contract.

## Should the Plutus Team and/or IOG maintain these smart constructors?
As the Ledger and Plutus teams are most likely to introduce API breakage or new invariants in the future, the maintainer of these safe constructors and documents should unequivocably be part of the IOG team.

## Additional reading:

The issue is described in detail on the following github issues
https://github.com/input-output-hk/plutus/issues/4476
https://github.com/input-output-hk/plutus/issues/4811
