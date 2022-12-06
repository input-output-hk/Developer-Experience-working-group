# Well-Architected Framework

## Rationale

Cloud-development platforms usually provide a "well-architected framework" that describes their view of how to approach the development of complex systems on top of their platforms.

Here are some examples:

AWS: https://aws.amazon.com/architecture/well-architected
Azure: https://learn.microsoft.com/en-us/azure/architecture/framework/

In essence, each framework provides a set of best-practices on how to approach different development disciplines, such as: security, reliability, performance-optimization, monitoring, tracing, etc.

Having a "Cardano Well-Architected Framework" in a similar fashion to the mentioned above would serve as useful guidelines for developer teams entering the ecosystem.

## Roadmap / Status

- [ ] Define scope for v1
- [ ] Identify KOLs for each topic
- [ ] Gather content from KOLs
- [ ] Prepare draft document
- [ ] Gather feedback
- [ ] Publish v1

> KOL: A key opinion leader (KOL) is an individual who is widely recognized as an authority or expert in a specific field or industry. 

## Scope

The following is a _live_ list of topics that the Well-Architected framework for Cardano should include.

It's organized by broad disciplines that are involved in the process of building a dApp. Each discipline describe relevant _principles_ and _best practices_.

> **Principle**: a fundamental rule or guideline that should be followed when designing and building software applications. Principles are typically broad, general statements that provide guidance and direction for software development.

> **Best Practice**: a specific approach or technique that has been shown to be effective in solving a particular problem or achieving a specific goal in software development. Best practices are typically based on the experiences and expertise of experts in the field, and they provide guidance on how to design and implement software in a way that is maintainable, scalable, and extensible.

### Reliability

#### Principles
- Design for business requirements
- Design for failure
- Observability
- Automation
- Self-healing

#### Best Practices
- Permanent Failure Handling
- Transient Failure Handling
- Congestion Handling
- Rollback Handling
- Tx Retry Policies
- Traffic Load Balancing

### Security

#### Principles
- Identity Management
- Infrastructure Security
- Application Security
- Contract Security
- Contract Auditing
- Property-based Testing

#### Best Practices
- Client-side Wallet Integration
- Server-side Key Management
- Node Network Topology
- Plutus Testing Pipeline

### Cost Optimization

#### Principles
- Cost Estimation
- Cost Models
- Cost Monitoring
- Capacity Planning

#### Best Practices
- Cardano Node Capacity Planning
- DB-Sync Capacity Planning
- Dynamic Scaling

### Performance

#### Principles
- Load Testing
- Stress Testing
- Process Profiling
- Plutus Cost Model

#### Best Practices
- Mempool Optimization
- Tx Chaining
- Plutus Script Optimization

## How to contribute

- By submitting a PR with changes to the scope (table of contents)
- By creating a new .md file that includes relevant information on any of the specific topics (it can be references to outside material or original content)
- By proposing candidate KOLs that would pontentially be able to fullfil the content for any of the topics.