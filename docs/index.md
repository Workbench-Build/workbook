# The Workbook

- [The Workbook](#the-workbook)
  - [About](#about)
  - [Brainstorming](#brainstorming)
    - [Problems in search of solutions](#problems-in-search-of-solutions)
    - [How?](#how)
    - [Mechanism design](#mechanism-design)
  - [1 Pager](#1-pager)
  - [Diagramming](#diagramming)
    - [Causal Loop](#causal-loop)
    - [Stock and Flow](#stock-and-flow)
    - [cadCAD Differential Specification](#cadcad-differential-specification)
    - [cadCAD Diagram](#cadcad-diagram)
    - [Technical contract specification](#technical-contract-specification)
  - [Modeling](#modeling)
    - [cadCAD](#cadcad)
    - [Other](#other)
  - [Prototyping](#prototyping)
    - [Design](#design)
      - [Tokens](#tokens)
    - [Implementation](#implementation)
  - [Auditing](#auditing)
    - [Economic Review](#economic-review)
    - [Technical Review](#technical-review)
  - [Incentivized Testing](#incentivized-testing)
  - [Deployment](#deployment)
  - [Monitoring and analysis](#monitoring-and-analysis)
  - [Community engagement and governance](#community-engagement-and-governance)
  - [Upgrades](#upgrades)
  - [Examples](#examples)
  - [Resources](#resources)

---

## About

This document will take you through the token design, development, and deployment process. Some parts may or may not be relevant to you. Choose your own adventure.

---

## Brainstorming

### Problems in search of solutions

*and not the other way around*

This explores the ideation stage. Here it's most important to think about the value you want to create for users. Who are the users? What problems are you going to solve for them? The bigger the problem you can solve for the most people, the more value you can create (and capture) with your token.

Ideally you want to be solving a problem that is:

- Popular (lots of people have it)
- Growing (more and more people have it)
- Frequent (those people experience it a lot)
- Expensive (it's hard for people to solve for themselves)
- Mandatory (it must be solved)

> This list is from [YC's Startup School](https://www.youtube.com/watch?v=DOtCl5PU8F0). While it's focused on startups, a lot of the same concepts apply to both startups and token projects. Highly recommend checking out their videos.

From there, you should be able to explain [why](https://simonsinek.com/product/start-with-why/) you're solving this problem in a way that's simple and intuitive. It should be something so simple you can explain it in a single sentence and people get it. It should be a [meme](https://en.wikipedia.org/wiki/Meme). People should understand what and why. It's your job to abstract away all the complexity of the how so that the solution "just works."

### How?

Once you've identified a problem to solve, and people who have that problem, you have to then go solve it for them. This is hard. While choosing the right thing to work on is often what will determine your success or failure, after that it's all about execution. In blockchain land this means you need to create a token system to align incentives for the community to create, use, and maintain an application/protocol.

Tokens = value = incentives. If your token has value people should be incentivized to do things to create/capture that value. If done correctly this can be positive-sum. It's very important that you understand this. Token networks are socio-economic systems. Incentives + humans = value creation. Your token system needs to reward people for doing things that create value for token holders. Then people will want to earn, buy, and hold/use your token. Supply and demand.

This is two layers deep in the problem solving stack. First you need to figure out how to solve the core problem (whatever that is) for end users. Then you need to solve the problem of creating an incentive system that gets people to work on that problem. It's like building the car and the factory that builds the car. You need both.

Startup founders have the same problem. They need to solve a problem for end users, while also building a company to solve that problem at scale. The main difference is that there's library of knowledge freely available on how to create, fund, and grow startups. Best practices for token projects are TBD. Token projects are mix of entrepreneurship, politics, economics, software development, systems design, and more. Depending on your goals and system architecture your token project will probably sit on the spectrum between an API, corporation, and government.

### Mechanism design

So the question then becomes, how do you design a system? When you think through your token system it's important to consider what properties you want to hold. This will help you make (or not make) design decisions. For example, do you want the system to be truly permissionless or do you want a core team (or community multi-sig) to have admin permissions for a while?

From there you can look at currently available token system templates to see if any meet your needs and/or just design your own. You'll likely end up starting with a base template and extending it for your use case.

Also, there are many token system templates that you can use to get started. You can use them as is, modify them to suite your needs, or create something from scratch. Knowing the resources available could save you a lot of time and money. This way you can focus on the unique aspects of your system vs having to build everything from scratch for everything.

To start, we recommend checking out the current templates and token systems live in the wild. This can give you an idea of what's available, what's working, and where you might have an opportunity to create something new and exciting.

- LIST OF TOKEN THINGS GOES HERE
- Or maybe just links to other people's lists of things?

---

## 1 Pager

Once you've identified a problem to solve, people who have that problem, and how you're going to solve it for them you should write it down! This will help you clarify your thinking. It will also help you communicate your vision to others. Then they might join you on your quest and/or point out ways that you might improve things.

To start, keep it simple. Just create a single page that describes what you're trying to do, why, and how. Eventually this might evolve into a formal specification, but right now we just want a rough sketch that's simple and intuitive. YOu can then update this as you design, develop, and deploy your token system. Then share it as a blog post or white paper. For now, keep it in a format (Google docs, HackMD, GitHub repo, etc..) that people can easily read, review, and comment on. This can help catch errors early on as well as engage your community.

The paper should describe the various components that are composed to achieve your goal, the properties of each mechanism, and the properties of your system as a whole.

It should also talk about why anyone could/should/would care about your token. You should explain why your token is useful (aka provide value) and how that will drive demand (resulting in a high token price). Supply and demand 101m, with tokens. It ain't much, but it's honest work.

Some things that might drive value:

- Access to a token permissioned chat
- Bounties for creators or communities
- Loot boxes to earn special products/services
- Discount token model for products/services
- Staking and TCRs
- Governance (easier said than done)
  - Signalling: Snapshot
  - Binding: optimistic games or on-chain mechanisms

---

## Diagramming

Diagramming can help you refine your understanding of the system and it's components. It's also useful when you want to communicate your vision to others. There are many types of diagrams and charts, but what's best for your use case and audience may vary.

### Causal Loop

Template for causal loop diagrams goes here.

### Stock and Flow

Template for Stock/Flow diagram goes here.

### cadCAD Differential Specification

[The cadCAD differential specification template](`https://community.cadcad.org/t/differential-specification-syntax-key/31`) is a good exercise to help you think through all the variables at play in your system and how they relate to each other. There's a [Figma template](https://www.figma.com/file/yBgOopbmcdkYxo2jDNmua1/cadCAD-Diff-Spec-Syntax?node-id=0%3A1) or you can create your own in your favorite diagramming software.

### cadCAD Diagram

cadCAD diagrams can be autogenerated for any cadCAD model. It's often as simple as adding a single line of code after you run the model. The [cadCAD Diagram repo](https://github.com/cadCAD-org/cadCAD_diagram) has more information on how to set that up.

### Technical contract specification

Solidity contract diagrams can be autogenerated via [Surya](https://github.com/ConsenSys/surya) and/or the [VSCode Soldity Visual Developer extension](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor). You can also manually create diagrams that show each function, it's inputs, and outputs. This can help you (and your community) understand the boundaries of your contract and the permissions and relationships between functions.

---

## Modeling

> Stuff about developing intuition on modeling goes here (go through notes and turn them into something practical).

### cadCAD

[cadCAD](https://cadcad.org/) is a python based library for modeling complex systems. There's free and open source [demos and tutorials](https://github.com/cadCAD-org/demos). There's also some [templates](https://github.com/cadCAD-org/snippets) to help you get started with your own models. If you have questions there's a [community forum](http://community.cadcad.org/) and [Discord](https://discord.gg/cewBa9zsxS).

### Other

- [Machinations](https://machinations.io/) - A platform and graphical interface for designing and simulating games.
- [DIY Python](https://www.python.org/) - Create your modeling framework in python like Ocean Protocol did with [TokenSpice](https://github.com/oceanprotocol/tokenspice2).

---

## Prototyping

### Design

Once you know what you're doing and how all the pieces come together you can create a prototype.

Based on your initial 1pager, diagrams, and model you should be able to answer the following questions about your token (or tokens):

- Are you creating a single or multi-token system (KISS!)?
- What type of token is the best fit for your use case fungible (ERC-20), unique (ERC-721), or exotic (ERC-XXX).
- Are tokens transferable and/or is it possible to unlock transferability via a governance decision (admin, community multi-sig, token holder vote, etc..)?
- What is the supply schedule: fixed, inflationary, variable (ex: bonding curve)?

#### Tokens

**Fungible:**

The most common form of fungible Ethereum tokens is the ERC-20 token standard. ERC-20 allows for the implementation of a standard API for tokens within smart contracts. This standard provides basic functionality to transfer tokens, as well as allow tokens to be approved so they can be spent by another on-chain third party. A standard interface allows any tokens on Ethereum to be re-used by other applications: from wallets to decentralized exchanges.

An ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

Often times people will use the ERC-20 template as a base, but then add additional features and functionality on top. This ensures that the token will have the standard ERC-20 interfaces required to work with wallets, protocols, and exchanges while also incorporating additional features needed for the tokens use case.

Resources:

- [Ethereum.org Developer Docs: ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) - A high level overview of fungible tokens and how ERC-20 works.
- [Ethereum EIP repo Issue 20](https://github.com/ethereum/EIPs/issues/20) - The original discussion and specification for ERC-20.
- [Ethereum Improvement Proposal 20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) - The final technical specification for ERC-20.

Examples:

- [OpenZeppelin Safe ERC-20](https://docs.openzeppelin.com/contracts/3.x/erc20-supply) - A guide on how to use the [OpenZeppelin ERC-20 implementation](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/SafeERC20.sol).
- [TORN token](https://github.com/tornadocash/torn-token/blob/master/contracts/TORN.sol) - The [TornadoCash](https://tornado.cash/) token uses the OpenZeppelin Safe ERC-20 as a base, then extends additional functionality on top.

**Non-Fungible:**

A Non-Fungible Tokens (NFT) is used to identify something or someone in a unique way. This type of Token is perfect to be used on platforms that offer collectible items, access keys, lottery tickets, numbered seats for concerts and sports matches, etc. This special type of Token has amazing possibilities so it deserves a proper Standard, the ERC-721 came to solve that!

The ERC-721 introduces a standard for NFT, in other words, this type of Token is unique and can have different value than another Token from the same Smart Contract, maybe due to its age, rarity or even something else.

All NFTs have a uint256 variable called tokenId, so for any ERC-721 Contract, the pair contract address, uint256 tokenId must be globally unique. Said that a dApp can have a "converter" that uses the tokenId as input and outputs an image of something cool like zombies, weapons, skills, or amazing characters.

Resources:

- [Ethereum.org Developer Docs: ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) - A high level overview of non-fungible tokens and how ERC-721 works. Also links to other non-fungible token standards at the bottom of the page.
- [Ethereum EIP repo Issue 721: non fungible token standard](https://github.com/ethereum/EIPs/issues/721) - The original discussion and specification for ERC-721.
- [Ethereum Improvement Proposal 721](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) - The final specification for ERC-721.

Examples:

- [ERC-721 Impleimentations](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md#references) - See the "NFT Implementations and Other Projects" section.

**Other:**

Beyond fungible (ERC-20) and non-fungible (ERC-721) tokens, there are many other types of tokens. This includes, but is not limited to:

- 1450 A compatible security token for issuing and trading SEC-compliant securities
- 1155 Multi Token Standard
- 1167 Minimal Proxy Contract
- See more here: `https://eips.ethereum.org/erc`

Examples:

- Lots of games use 1155
- Some dapps are starting to use 1167

### Implementation

> For now we're starting with Ethereum. Can't boil the ocean. That being said, the token design process is rather general and can be applied to any blockchain project.

Then once you know what you want, your resources (time/money) and technical ability will determine the tools that are the best fit:

- If you want something that works out of the box a social token platform such as CollabLand, Roll, or StakeOnMe might be a good choice. While you'll be able create a token in minutes these platforms may charge fees, have proprietary components, and/or limited customization. As such you'll likely be tied to the platform so choose wisely.
- If you want to deploy your own independent token system, but still use a template there's a few other options such as Aragon, Moloch, Liquidity Delegated governance, bonding curves, etc..
- If you really want to build something unique then rolling your own Solidity contracts is the way to go. Even still, there's some basic building blocks you might want to consider such as OpenZeppelin and (more examples go here).
- Do you want to be able to pause the contract if/when things are going wrong ('circuit breaker'), and if so, who has that power (project team, community multi-sig, token holder vote)?
- Do you want to put constraints on the amount of money that can move through the system in a single transaction (rate limiting, maximum usage)?
- Do you want to create an [upgrade path for bugfixes and improvements](https://consensys.github.io/smart-contract-best-practices/software_engineering/#upgrading-broken-contracts), or migrate to new contracts?

Remember to have a full test suite with 100% test coverage (or close to it) so that your community and/or a profession review team isn't spending time on easily avoidable errors.

Once you've selected, assembled, or written your contracts you'll want to check if they work on one of Ethereum's many testnet (free) or xDAI (very cheap).

`https://remix.ethereum.org/`

`https://eth.build/`

`https://ethereum.org/en/developers/learning-tools/`

`https://ethereum.org/en/developers/local-environment/`

`https://consensys.github.io/smart-contract-best-practices/general_philosophy/`

`https://github.com/OpenZeppelin/openzeppelin-contracts`

Within the wild world of Ethereum there are many languages to write contracts. Solidity is the most popular with many tutorials, support, and tooling. Vyper and Fe are for more advanced developers. If you're not familiar with these languages already, here's a few resources to get started.

Solidity:

- `https://docs.soliditylang.org/`
- `https://consensys.github.io/smart-contract-best-practices/`

Vyper:

- `https://vyper.readthedocs.io/`
- `https://github.com/ethereum/fe`

Fe:

`https://fe.ethereum.org/`

---

## Auditing

On the blockchain code is law. The contract will do what is written, even if that's not what you intended. As such, it's good to have a trusted third party review your token system before deploying to production. This does not guarantee anything, but it can help - sometimes a lot. There are two main types of review to think about, economic and technical. Economic reviews look for ways to game the token system, and technical reviews look for bugs in the code.

Good reviews are expensive. They cost a lot of time and money. To get the most bang for your buck, and potentially eliminate some low hanging fruit, there's a few things you can do before a review. In the best case this will reduce the initial leg work for the review team giving them more time to dig deeper into your token system and contracts. In the worst case, even if the review team replicates your work [given enough eyes, all bugs are shallow](https://en.wikipedia.org/wiki/Linus%27s_law). As such it's important to open source your code for the community and have a bug bounty / testing program. Ideally your community continuously reviews your codebase with fresh eyes looking for bugs and unintended behavior.

All that being said, even if you don't have the capital for a professional security review we recommend that you go through this process and do as much work as you can on your own. This shows the community that you're serious about security. It also provides the opportunity for skilled community members or peers to contribute. By sharing your design process and code you're contributing to the open source community, and as a result people in the space might notice and contribute back.

### Economic Review

An economic review will involve reviewing your token system and testing it for unintended behavior. This requires you to first clearly state what you want the system to do. Then token engineers will try to find all the ways to make it do something else. If your system is designed correctly it's intended properties should hold. In addition, the system should specify under what conditions it is expected to hold (no 51% attack, ETH > 0, TOKEN > 0, etc..).

Before you get started with an economic review, there's a few things you can do to prepare. In the best case you'll catch unintended outcomes ahead of time so that the review team can focus on deeper work. In the worst case you'll learn about Ethereum token economics and be better prepared for the review process and future token system design:

- Resources go here.
- Common blunders such as relying on an AMM as an oracle (and then having that oracle report unexpected values via flash loans) (flashloan sandwich)
- Ensure that admins can't mint/burn tokens arbitrarily
- If your system has governance, think through the difficulty of getting things passed, esp how that difficulty will change over time if you have tokens that are vesting and not yet liquid or if you have "token sinks" that will have people locking up tokens (liquidity mining, derivative tokens, etc..)
- If you have an inflationary token think through how token holders will create value to drive more demand than inflation. What does the best case and worst case scenario look like? How can you create [minimax](https://en.wikipedia.org/wiki/Minimax) strategies that reduce risk and maximize the chance of sustainability?

At the moment there are not very many firms who specialize in this type of economic analysis. With the popularity of DeFi we expect this list to grow. For now, here's a few teams that provide token system designs and reviews:

- [BlockScience](https://block.science/) - An engineering, R&D, and analytics firm specializing in complex systems. Our focus is to design and build data-driven decision systems for new and legacy businesses leveraging engineering methodologies and academic-grade tools. Blockscience [open sources a lot of their work](https://github.com/blockscience) including past projects and even their system modeling library ([cadCAD](https://github.com/BlockScience/cadCAD-Tutorials))
- [Gauntlet](https://gauntlet.network/) - Gauntlet’s mission is to help make blockchain protocols and smart contracts safer and more trustworthy for users. At the time of writing their projects and tooling are proprietary.
- [TBD](TBD) - More teams coming soon.

### Technical Review

A technical review looks for bugs in your code. This also requires having a clear specification describing the intended behavior of your contracts and the review team will also try to make them to something else. Unlike the economic analysis, however, this is likely to be more focused on exploiting the contract itself vs how the contract composes with larger systems.

Before you get a technical review, there's a few things you can do to prepare. In the best case you'll catch bugs ahead of time so that the review team can focus on deeper work. In the worst case you'll learn about Ethereum contract security and be better prepared for the review process and future contract development:

- Review [Ethereum contract development best practices](https://consensys.github.io/smart-contract-best-practices/). Know the recommended interaction patterns, check your code for anti-patterns, and run security analysis tools to catch common errors.
- Make sure you have basic docs and a technical specification. This ensures that the review team knows what you *want* the code to do. Then they can check to see if that's what it actually does.
- Read security review reports from other projects (see [here](https://consensys.net/diligence/audits/) and [here](https://github.com/trailofbits/publications#security-reviews)) to get a better idea of what to expect. Might even give you ideas of things to check/change before your audit.

Here's a few teams that provide excellent security reviews for Ethereum contracts:

- [Consensys Diligence](https://consensys.net/diligence/) - Consensys Diligence provides a comprehensive smart contract audit service to help everyone from startups to enterprises launch and maintain their Ethereum blockchain applications. They also contribute a lot of open source [reviews and tooling](https://github.com/ConsenSys) to the Ethereum community.
- [Trail of Bits](https://www.trailofbits.com/) - Trail of Bits provides a variety of services to secure and test both Web2 and Web3 software. They're a great choice if you want an end-to-end security review that goes beyond Solidity contracts. They also contribute a lot of [open source research and tooling](https://www.trailofbits.com/products) to the space.
- [TBD](TBD) - There's lots of other security firms in the space as well. If you know of any good ones please submit a PR!

## Incentivized Testing

Once you've designed your system and gotten a review you can start to test it out! Remember, with enough eyes all bugs are shallow. With an incentivized test the community and traders can interact with your token system and potentially profit from it. Here the risk and rewards are real, but contained. This caps your downside in the event of an unexpected outcome.

If things don't go as planned, find out why and fix it. If things go smoothly, learn from your data top see if there's anything you want to change before deploying in production.

When creating incentivized tests, there's a few ways to go about it:

- [Ethereum](https://ethereum.org/) is another great place to test out your token system. You can create a beta version of your contracts for the community to test before transitioning to the full version. This beta version might have limits on the amount of tokens that can be processed or it might have a limited conversion to new tokens once you're out of beta.
- You can also deploy contracts anonymously and then test them out to ensure they function as intended before redeploying an official version.
- [xDAI](https://www.xdaichain.com/) is an EVM based blockchain. Gas fees, transaction times, and security are lower on xDAI than Ethereum mainnet. This makes it great for non-financial use cases and incentivized testing. Deploying contracts to xDAI is often as simple as switching the chainID from mainnet to xDAI.
- Beyond the Ethereum ecosystem, there are also other networks that have created incentivized testnets for developers such as Polkadot's [Kasuma](https://kusama.network/).

---

## Deployment

> Ship ship ship

Deployment tips and tools (remix, buidler, etc..) go here.

And [create a bug bounty](https://consensys.github.io/smart-contract-best-practices/software_engineering/#bug-bounty-programs)! (even if it's only in your native token1)

---

## Monitoring and analysis

Resources to monitor on-chain and community engagement goes here.

This will involve monitoring markets as well as fundamentals, both onchain (token price, distribution, hodl waves, volatility, etc...) and offchain (community engagement, etc..)

---

## Community engagement and governance

> Talk about how analysis informs governance and governance informs what we analyze.
> Create a place for the community to discuss things and mechanisms for them to express their sentiments to affect change.

- General community best practices
- Discord server organization
- Token permissioned chats
- Giving people a reason to stay engaged
- Recognize and reward community contributors
- Governance and governance minimization

Governance is hard.

This section will talk about why you might need governance (managing shared resources) and the tools you might use to do so (Snapshot, dApps, etc..).

We'll also talk about the difference between global governance and local governance, and when you might want to use one vs the other. For example, allowing decisions about how to organize Discord be managed via Discord polls but decisions on the inflation rate of your token to be managed by token holders directly.

Talk about various governance models:

- rough consensus
- snapshot/multi-sig
- global voting mechanism (token params)
- local voting mechanism (ecosystem mechanisms)

---

## Upgrades

It's likely that you'll want to upgrade and add on to your token system. Depending on your token system, and the nature of the update, this might involve a token holder vote or it might be permissionless. Often changes to the core structure are permissioned as they affect token holders. If you have a transferable token add-ons are permissionless as anyone can create a new contract/mechanism that uses your token and any token holder is free to choose whether or not they want to interact with that contract.

The simpler your core token system is, the easier it will be to incorporate new things in an opt-in permissionless way. The easiest way to do this is to start with a simple token contract, then create more things that use that contract.

Talk about minimizing governance and pushing it to the edges here.

Potential mechanisms include, but are not limited to:

- Tipping mechanisms
- Bounties
- DAOs (yes your token can be used in multiple community DAOs for multiple purposes - there doesn't have to be a single organization)
- Secondary bonding curves
- AMMs
- NFT minting factories
- Etc...

Explore ways to help your community go from consuming what you create to creating things themselves.

- Token bounties/rewards/challenges mechanisms (both for fans and creators)
- Prediction markets (on challenges fans can create for creators)
- Tipping/gifting mechanisms (give first)
- Signalling/polling mechanisms (soft governance)
- Voting mechanisms (hard governance)
- Collaborations/mergers with other projects

## Examples

- 1UP
- CommonsStack praise bot
- 1Hive nominations

---
---
---

## Resources

Additional resources related to the token design, development, and deployment process:

- [A Token Engineering Process](https://medium.com/@stephen_yo/a-token-engineering-process-16687f3b9a74) - Great article that covers the basics of system mapping and diagramming in the context of token engineering. More great articles on the token engineering process [here](https://blog.oceanprotocol.com/towards-a-practice-of-token-engineering-b02feeeff7ca) and [here](https://medium.com/block-science/on-the-practice-of-token-engineering-part-i-c2cc2434e727)
- [Token Engineering community](https://tokenengineeringcommunity.github.io/website/) - A community working to further the discipline of token engineering through education and outreach. Check out their [Library](https://tokenengineeringcommunity.github.io/website/docs/library-te-101) for more resources.
- [CommonsStack](https://commonsstack.org/) - A community working to create templates and best practices to realign incentives around public goods.
- [cadCAD Edu](https://www.cadcad.education/) is a great resource to learn about the token engineering process. While it's focused on cadCAD, the Complete Foundations Bootcamp is a great intro to the token engineering design process as a whole.
