## Token System Modeling

- [Token System Modeling](#token-system-modeling)
  - [About](#about)
    - [1 Pager](#1-pager)
    - [Diagramming](#diagramming)
    - [Modeling](#modeling)
    - [Incentivized Testing](#incentivized-testing)
    - [Auditing](#auditing)
    - [Deployment](#deployment)
    - [Monitoring and analysis](#monitoring-and-analysis)
    - [Governance](#governance)
  - [Resources](#resources)
    - [Courses and tooling](#courses-and-tooling)
    - [Communities](#communities)
  - [Examples](#examples)

### About

This section includes tools and techniques to design and analyze your token economy. This includes token engineering best practices, system modeling tools, and communities that are pushing forward the frontier of token engineering.

#### 1 Pager

This should describe what you're trying to do, why, and how to implement it. Eventually this will look like a formal specification, but initially it's more of a rough sketch. It's expected that you'll update this as you build out and refine your token system.

#### Diagramming

> A picture says a thousand words!

Do we have a template for causal loop diagrams?

[The cadCAD differential specification template](`https://community.cadcad.org/t/differential-specification-syntax-key/31`) is a good exercise to help you think through all the variables at play in your system and how they relate to each other. There's a [Figma template](https://www.figma.com/file/yBgOopbmcdkYxo2jDNmua1/cadCAD-Diff-Spec-Syntax?node-id=0%3A1) or you can create your own in your favorite diagramming software.

#### Modeling

**Resources:**

- [cadCAD](https://cadcad.org/) - A python based library for modeling complex systems.
- [Machinations](https://machinations.io/) - A platform and graphical interface for designing and simulating games.
- [DIY Python](https://www.python.org/) - You can also create your modeling framework in python like Ocean Protocol did with [TokenSpice](https://github.com/oceanprotocol/tokenspice2).

#### Incentivized Testing

[xDAI](https://www.xdaichain.com/) is an EVM based blockchain. Gas fees, transaction times, and security are lower on xDAI than Ethereum mainnet. This makes it great for non-financial use cases and incentivized testing. Deploying contracts to xDAI is often as simple as switching the chainID from mainnet to xDAI.

[Ethereum](https://ethereum.org/) is another great place to test out your token system. You can create a beta version of your contracts for the community to test before transitioning to the full version. You can also deploy contracts anonymously and then test them out to ensure they function as intended before redeploying an official version.

#### Auditing

On the blockchain code is law. The contract will do what is written, even if that's not what you intended. As such, it's good to have a trusted third part review your token system before deploying to production. This does not guarantee anything, but it can help - sometimes a lot. There are two main types of review to think about, economic and technical. Economic analysis looks for ways to game the token system, and technical analysis looks for bugs in the code.

**Economic Review:**

- BlockScience
- Any others?

**Technical Review:**

- Consensys Diligence
- Trail of Bits
- Etc..

#### Deployment

Ship ship ship

#### Monitoring and analysis

What's the best/easiest way to do this?

#### Governance

How to use said analysis to inform governance decisions.

### Resources

#### Courses and tooling

- [cadCAD Edu](https://www.cadcad.education/) is a great resource to learn about the token engineering process. While it's focused on cadCAD, the Complete Foundations Bootcamp is a great intro to the token engineering design process as a whole.
- [A Token Engineering Process](https://medium.com/@stephen_yo/a-token-engineering-process-16687f3b9a74) - Great article that covers the basics of system mapping and diagramming in the context of token engineering.
- `https://blog.oceanprotocol.com/towards-a-practice-of-token-engineering-b02feeeff7ca`
- `https://medium.com/block-science/on-the-practice-of-token-engineering-part-i-c2cc2434e727`
- `https://tokenengineeringcommunity.github.io/website/docs/library-te-101`

#### Communities

- Token Engineering community: `https://tokenengineeringcommunity.github.io/website/`
- CommonsStack community

### Examples

- Ocean V2 is going through the token engineering process to launch V2 of their network.
- 1Hive uses token engineering to design and manage their HNY token and DAO.
- The Token Engineering Commons is designing and deploying their token/DAO using these techniques and tools.
