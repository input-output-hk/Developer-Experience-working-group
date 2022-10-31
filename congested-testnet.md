# Congested Developer Testnet
Developer Experience Working Group Proposal #1

v0.1

## Linked Issue
https://github.com/input-output-hk/Developer-Experience-working-group/issues/32

## Preamble

As seen during a variety of events on Ethereum, congestion can result in a wide variety of unpredictable behaviors, often leading to protocol exploits. In particular I want to draw attention to the MakerDAO attack on Black Thursday (March 2020), where congestion caused Oracle updates to happen unpredictably with stale data, and where transaction fees drove liquidators away, resulting in 0-bid auctions and assets being given away for free.

Developers may need environments that represent these black-swan states of the chain - particularly when trying to prevent bank runs and other exceptional cases that could cause large amounts of lost assets.


## Developer Experience Concerns
Developers may need to run tests that show the chain in a non-ideal state, such that they can safegaurd protocol security and user experience in suboptimal conditions.

## Proposed Solution
An organization will need to create a test network with blockfrost support, with a transaction volume that exceeds the current mainnet capabilities - ideally with simulated traffic representing a similar relative split between the following:

- smart-contract/'complex' transactions
- Ada/Asset peer-to-peer transactions

Even more important than this split, the network should *always* have delayed blocks due to traffic.

## Sponsorship status
This proposal currently has no sponsor

## Additional Reading
https://medium.com/aave/crypto-black-thursday-the-good-the-bad-and-the-ugly-7f2acebf2b83
