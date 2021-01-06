# The Workbook

> This document will take you through the token design, development, and deployment process. In practice you'll go back and forth between steps as your project progresses. Some parts may or may not be relevant to you. Choose your own adventure.

---

- [The Workbook](#the-workbook)
  - [Design](#design)
    - [Brainstorming](#brainstorming)
    - [Mechanism design](#mechanism-design)
      - [Roles, methods, and states](#roles-methods-and-states)
      - [Token System Templates](#token-system-templates)
      - [Governance mechanisms](#governance-mechanisms)
      - [Additional token mechanisms](#additional-token-mechanisms)
      - [Tokens](#tokens)
        - [Fungible](#fungible)
        - [Non-Fungible](#non-fungible)
        - [Other](#other)
    - [1 Pager](#1-pager)
    - [Diagramming](#diagramming)
      - [Causal Loop](#causal-loop)
      - [Stock and Flow](#stock-and-flow)
      - [cadCAD Differential Specification](#cadcad-differential-specification)
      - [cadCAD Diagram](#cadcad-diagram)
      - [Technical contract specification](#technical-contract-specification)
    - [Modeling](#modeling)
      - [cadCAD](#cadcad)
      - [Other](#other-1)
  - [Development](#development)
    - [Platform or DIY?](#platform-or-diy)
      - [Platform](#platform)
      - [Templates](#templates)
      - [DIY](#diy)
      - [Scaling](#scaling)
    - [Auditing](#auditing)
      - [Economic Review](#economic-review)
      - [Technical Review](#technical-review)
  - [Deployment](#deployment)
    - [Testing](#testing)
    - [Production](#production)
    - [Monitoring and analysis](#monitoring-and-analysis)
    - [Community engagement and governance](#community-engagement-and-governance)
    - [Upgrades](#upgrades)

---

## Design

**TL;DR:**

- Find a problem to solve.
- Define your design goals.
- Define roles, methods, states.
- Define mechanisms.
- Define the composition of mechanisms into a token system.
- Write a blog post describing it.
- Draw a picture describing it.
- Create a model simulating it's behavior.

### Brainstorming

**TL;DR:**

- What is the problem you're solving?
- What is the purpose of your token (access, discounts, unique items/experiences, governance, etc..)?
- Is there any part of your token system (including the token itself) that could be removed while still achieving your goals?
- How will people acquire tokens (buy, earn, other)?
- How will the value of those tokens increase as the token system grows (network effects)?

It's better to be finding the solution to a big problem than finding a problem for your big solution.

This explores the ideation stage. Here it's most important to think about the value you want to create for users. Who are the users? What problems are you going to solve for them? The bigger the problem you can solve for the most people, the more value you can create (and capture) with your token.

Ideally you want to be solving a problem that is:

- Popular (lots of people have it)
- Growing (more and more people have it)
- Frequent (those people experience it a lot)
- Expensive (it's hard for people to solve for themselves)
- Mandatory (it must be solved)

From there, you should be able to explain [why](https://simonsinek.com/product/start-with-why/) you're solving this problem in a way that's simple and intuitive. It should be something so simple you can explain it in a single sentence and people get it. It should be a [meme](https://en.wikipedia.org/wiki/Meme). People should understand what and why. It's your job to abstract away all the complexity of the how so that the solution "just works."

Once you've identified a problem to solve, and people who have that problem, you have to then go solve it for them. This is hard. While choosing the right thing to work on is often what will determine your success or failure, after that it's all about execution. In blockchain land this means you need to create a token system to align incentives for the community to create, use, and maintain an application/protocol.

Tokens = value = incentives. If your token has value people should be incentivized to do things to create/capture that value. If done correctly this can be positive-sum. It's very important that you understand this. Token networks are socio-economic systems. Incentives + humans = value creation. Your token system needs to reward people for doing things that create value for token holders. Then people will want to earn, buy, and hold/use your token. Supply and demand.

This is two layers deep in the problem solving stack. First you need to figure out how to solve the core problem (whatever that is) for end users. Then you need to solve the problem of creating an incentive system that gets people to work on that problem. It's like building the car and the factory that builds the car. You need both.

Startup founders have the same problem. They need to solve a problem for end users, while also building a company to solve that problem at scale. The main difference is that there's library of knowledge freely available on how to create, fund, and grow startups. Best practices for token projects are TBD. Token projects are mix of entrepreneurship, politics, economics, software development, systems design, and more. Depending on your goals and system architecture your token project will probably sit on the spectrum between an API, corporation, and government.

In addition to exploring the technical specifications of tokens/mechanisms/systems it would be good to first identify the high level things such as the core value prop of the token (access, discounts, unique items/experiences, governance, etc..), how to acquire tokens (buy and/or earn), and how to extend and grow the value of tokens over time (network effects). There should be a quickstart guide so that if someone just wants to create a token or add a feature to do a thing they can do so easily.

**Questions to ask:**

- What problem are you solving?
- Who has this problem? How often?
- How much do they need this problem to be solved?
- How will your token contribute to solving this problem? Is your token incentivizing people to do work to solve the problem directly, or is it a component of a larger system that's working to solve that problem?
- What is the value prop of your token (access, unique items, discounts, governance, etc..)? Why would anyone want it?
- When it comes to token systems, simple is better. Is there anything you can remove while still maintaining the core value prop (and thus incentivizes) of your token system?
- If you substitute a stable coin or ETH with your token will things still work? If so, then you probably don't need to create a new token.
- How will people acquire your tokens (buy, earn, gift, etc..)?
- How will the token system work with 1 user? What about 10 or 100 (bootstrapping)?
- How will the token system get better as more people use it (network effects)? How will each additional user add more value than those before as the system grows?

**Examples:**

- TBD

**Resources:**

- [YC's Startup School](https://www.startupschool.org/) is a great resource to help you make something people want. The [How to find startup ideas](https://www.youtube.com/watch?v=DOtCl5PU8F0) video can help build intuition for what types of problems to solve, and more likely, prevent you from working on the wrong thing. While YC is focused on startups, a lot of the same concepts around solving problems and creating value for users apply to both startups and token projects. Highly recommend checking out [their videos](https://www.youtube.com/channel/UCcefcZRL2oaA_uBNeo5UOWg).
- Not to be outdone, [a16z](https://a16z.com/crypto/) also has a [crypto startup school](https://a16z.com/crypto-startup-school/). It has lots of content explaining high level concepts that are essential for the space. You can also sign up for their newsletter to get ongoing insights delivered to your inbox.
- [Simon Sinek](https://simonsinek.com/) has a lot of great content explaining why you should [start with why](https://simonsinek.com/product/start-with-why/).

### Mechanism design

So the question then becomes, how do you design a system? When you think through your token system it's important to consider what properties you want to hold. This will help you make (or not make) design decisions. For example, do you want the system to be truly permissionless or do you want a core team (or community multi-sig) to have admin permissions for a while?

From there you can look at currently available token system templates to see if any meet your needs and/or just design your own. You'll likely end up starting with a base template and extending it for your use case.

Also, there are many token system templates that you can use to get started. You can use them as is, modify them to suite your needs, or create something from scratch. Knowing the resources available could save you a lot of time and money. This way you can focus on the unique aspects of your system vs having to build everything from scratch for everything.

The architecture of your token system will vary based on your use case. The important thing here is to know what you want to do, then use the tools required to get the job done. Don't start with the tools! Otherwise you'll become like a man with a hammer. Choose the tools based on your goals and design constraints.

**Questions to ask:**

- TBD

**Examples:**

- TBD

**Resources:**

- The [Wikipedia mechanism design page](https://en.wikipedia.org/wiki/Mechanism_design). Is a great place to start. If you read one thing on mechanism design, make it this. There's also a whole [category on Wikipedia dedicated to the topic](https://en.wikipedia.org/wiki/Category:Mechanism_design).

#### Roles, methods, and states

Roles, methods, and states is just a fancy way of saying who can do what and under what circumstances.

Rights and access controls can be broken down into roles, methods, and states:
- **Roles:** bundles of rights determined by "the system state"
- **Methods:** actions that can be taken, mutates "the system state" but access or effect may be dependent on roles
- **State:** all of the information (not limited to smart contract state)

**Why do roles, methods, and states matter?**

The moment you create a modifiable/upgradeable token system you have a governance problem. Another way of framing this is as a rights/roles access problem. To more easily reason about this you need a process to describe and discuss the rules of the game. Then you can figuring out what the rules actually are, who can do what when, and how people participating in the system can change the rules of the system.

For governance to work people need to understand and respect the rules of the system, even if they don't agree with every decision. This is very important. We don't need consensus on the decisions themselves. We need consensus on the way we make decisions.

For example: if you respect the rules of a game you respect the scores that arise from playing, even if you wish your team won. Once people buy into the idea of the game they can focus on playing the game vs figuring out what the game is or arguing about the rules.

> Note: no one likes a rigged game. No one likes watching them and no one likes playing them. If everyone's not bound by the same rules and/or if the rules change or are fuzzy things are going to get weird. People get pissed if the rules don't apply equally or if they change in ways that are unfair or unclear. People like it, however, if they feel like they have agency in a system. If there is mobility within the system then people can engage how they want and move into a roles that suites them.

Rights access paradigms are a way to explicitly model and reason through these things. We need to map out rights and access controls to show who can do what and how people can move through the system. This is important because meritocracy and democracy are dependent on rights access controls. If we want to make it so that the rules apply to everyone equally the rules need to change slowly in a participatory way. We have to collectively buy into and accept the trade offs. Everyone can engage in the process and have agency in that process. You should be comfortable being dropped into a random role in society because there's a path towards the role you want.

Once we understand who's going to do what and under what circumstances, then we'll need to determine the mechanisms that will allow them to do those things.

**Questions to ask:**

- What are the requirements for participation?
- What the current rules are and how to change the rules?
- Would you be comfortable being dropped into a random role in the system?
- What does it mean for the world to be fair?

**Examples:**

- TBD

**Resources:**

- TBD

#### Token System Templates

To start, we recommend checking out the current templates and token systems live in the wild. This can give you an idea of what's available, what's working, and where you might have an opportunity to create something new and exciting.

**Questions to ask:**

- Is there an example of a project similar to what you want to build or working on a similar problem? If so, what's working for them and what's not? How can you do better?

**Resources:**

To be organized:

- Loot tokens (play to earn): `https://medium.com/@adamscochran/what-are-loot-tokens-understanding-an-emerging-asset-class-380b0cc38749`

Stuff:

- ***NEED TO ADD MORE DEFI AND TOKEN TEMPLATE STUFF HERE***
- [Gnosis multi-sig](https://blog.gnosis.pm/gnosis-safe-multisig-desktop-app-and-contract-interactions-6f8b92c3275b) - It's a shared Ethereum account. Parameters can be set so that actions can only be taken if signatures from many accounts are provided. Those actions can including sending tokens as well as contract interactions.
- [Snapshot](https://github.com/balancer-labs/snapshot) - Verify user's token balances, then let them sign messages to create off-chain signalling votes. Perform votes off-chain, then enact on-chain via a trusted community multi-sig. [Create your Snapshot page here](https://docs.snapshot.page/guides/create-a-space). Check out current Snapshot pages [here](https://snapshot.page/#/).
- [ERC3K](https://eips.ethereum.org/EIPS/eip-3000) - An open template for optimistic organizations.
- [Aragon Govern](https://github.com/aragon/govern) - Aragon's implementation of ERC3K. Optimistic organizations that use [Snapshot](https://snapshot.page/#/) for voting with the option for disputes if the vote is incorrect.
- [Aragon Company DAO](https://help.aragon.org/article/31-explore-the-company-organization) - Transferable token with voting and a treasury.
- [Aragon Fundraising](https://fundraising.aragon.black/) - A DAICO as described by Vitalik Buterin [here](https://ethresear.ch/t/explanation-of-daicos/465).
- [Colony](https://colony.io/dev/docs/colonynetwork/intro-welcome) - Reputation based task management and dispute resolution.
- [Commons Stack](https://commonsstack.org/) - Coordinate and sustain common goods.
- [Gardens](https://forum.1hive.org/t/gardens-overview/32) - Composable community currencies.
    - TEC template: `https://github.com/TECommons/tec-template`
    - 1Hive template: `https://github.com/1Hive/gardens-template`
- [MolochDAO](https://github.com/MolochVentures/moloch/tree/minimal-revenue/v1_contracts) - Coordinate and manage capital.
- [MolochDAO V2](https://github.com/MolochVentures/moloch) - Coordinate and manage capital.
- [MolochDAO V3](https://github.com/Moloch-Mystics) - Modular Moloch - plug and play DAO legos (WIP).
- Moloch (community w bank account)
  - Minion
  - Transmutation
  - Modular
- [LAOland](https://github.com/openlawteam/laoland) - More modular moloch (WIP).
- [TrojanDAO V2](https://github.com/TROJANFOUNDATION/Trojan-DAO-Token-Engineering) - Fundraise and coordinate and manage capital with Moloch DAO and a bonding curve.
- [Liquidity Delegated Governance](https://medium.com/@andre_54855/liquidity-delegated-governance-89184d40643a) - If you are looking for a boilerplate Liquidity Provision + Delegation + Governance + Timelock solution, all you need to do is create your token, provide liquidity to uniswap/balancer, and then call the deploy functions on the liquidity and governance factories. No multisig required and you have a fully configurable decentralized solution.
- [Buy back and make](https://www.placeholder.vc/blog/2020/9/17/stop-burning-tokens-buyback-and-make-instead) - Description goes here.
- [The da0](https://github.com/the-dao/whitepaper) - Description goes here.

Moloch:

- [Moloch V1 source code](https://github.com/MolochVentures/moloch/tree/master/v1_contracts) - The original Moloch. It's simple and effective. Start here.
- [Moloch Subgraph highlight](https://medium.com/graphprotocol/moloch-subgraph-highlight-faf9da2f7e73) - An overview of the Moloch subgraph from late 2019.
- [Moloch V2 source code](https://github.com/MolochVentures/moloch) - The V2 MolochDAO code and docs. Very informative. If you have to pick one, read this instead of all the other blog posts.
- [Moloch V2 audit report blog post](https://medium.com/@thelaoofficial/moloch-v2-smart-contract-audit-report-for-the-lao-48fb0415695a) - Overview of the Moloch V2 audit.
- [Moloch Evolved](https://medium.com/raid-guild/moloch-evolved-v2-primer-25c9cdeab455) - A primer on Moloch V2.
- [Moloch V2X](https://medium.com/lexdaoism/introducing-moloch-dao-v2x-mystic-ethereum-contract-upgrades-c7984801d4db) - Moloch V2 with some extra features.
- [Summoning 101](https://medium.com/totle/summoner-101-expectations-of-launching-your-own-moloch-dao-d6bb0fbbe600) - What you should expect when summoning a Moloch DAO.
- [How to summon a Moloch DAO](https://bankless.substack.com/p/how-to-start-a-moloch-dao) - A [Bankless](https://bankless.substack.com/) tutorial on summoning a Moloch DAO.
- [How to summon a LAO](https://bankless.substack.com/p/how-to-create-a-bankless-dao) - How to summon a Moloch DAO with a legal wrapper.
- [Moloch V3 WIP](https://github.com/openlawteam/moloch) - Exploring a modular Moloch.
- [Moloch Minion FAQ](https://github.com/DAOresearch/awesome-daos/issues) - A rolling list of FAQ around Moloch Minions.
- [Moloch Minion source code](https://github.com/raid-guild/moloch-minion) - An elegant solution for Moloch extensibility.
- [RaidGuld Minion](https://minion.raidguild.org/) - An example of a minion live in the wild.
- [Moloch Minion contract extensions](https://github.com/raid-guild/moloch-contract-extensions) - Contracts that extend the functionality of minions.
- [The LAO's Minion blog post](https://medium.com/@thelaoofficial/the-path-to-unaccredited-daos-with-minion-8113213f7195) - Overview of Moloch minion with a few use cases related to investment DAOs.
- [ScoutDAO](https://discourse.thelao.io/t/scoutdao/48) - Yet another minion use case, this time related to creating a shared account multiple Molochs can jointly manage.
- [Qaudratic Moloch](https://github.com/DemocracyEarth/DemocracyDAO) - A MolochDAO with quadratic voting built in.
- [Moloch L2 voting via merle tries](https://github.com/openlawteam/moloch/issues/2) - An exploration of off-chain voting with on-chain resolution in Moloch DAOs.

#### Governance mechanisms

> Talk about how you can include governance now, or leave it as an upgrade feature by enabling the `onlyOwner` (or whatever) to be changed so that you can transfer it to a multi-sig or DAO in the future.

Goverance is [the process of applying any design feature or control mechanism that maintains and steers a system](https://www.placeholder.vc/blog/2020/9/30/ten-theses-on-decentralized-network-governance). Here's a few governance mechanisms that are popular in blockchain land (although you might need L2/optimistic solutions to use some of them).

**Questions to ask:**

- Are there aspects of your system that will need to adapt and change over time?
- If so, who has the right to make that change?
- What is the process to make that change?
- Is it possible to change the process to make changes (meta-governance)?

**Examples:**

- TBD

**Resources:**

- [Ranked choice](https://en.wikipedia.org/wiki/Ranked_voting) - Voters use a ranked (or preferential) ballot to rank choices in a sequence on the ordinal scale: 1st, 2nd, 3rd, etc.
- [Budget box](https://blog.colony.io/introducing-budgetbox/) - Pairwise comparisons for budgetting.
- [Conviction voting](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475) - Proposals are passed based on aggregated continuous preferences of community members.
- [Delegated democracy]() - Delegate your votes to someone else.
- [Holographic consensus](https://medium.com/daostack/holographic-consensus-part-2-4fd461e8dcde) - A governance mechanism that allows for local decisions that represent the interests of a global group.
- [Quadratic voting](https://en.wikipedia.org/wiki/Quadratic_voting) - Voting weight scales quadratically with the number of tokens one holds. Not sybil resistant, but only works if everyone has a single account in the system.
- [Time boxed voting]() - Vote yay or nay on a thing within a window of time.
- [Wait for quite](https://medium.com/@dominic_w/using-wait-for-quiet-voting-in-the-dao-12ecd9d9ccc3) - Wait until voting has quited down before closing a vote.
- [MACI](https://github.com/clrfund/maci) - Minimum anti-collustion infrasctructure. Great for grants/investments DAOs.
- [Snapshot](https://github.com/balancer-labs/snapshot) - Verify user's token balances, then let them sign messages to create off-chain signalling votes. [Create your Snapshot page here](https://docs.snapshot.page/guides/create-a-space)!
- [Compound Autonomous Proposals](https://medium.com/compound-finance/compound-autonomous-proposals-354e7a2ad6b7) - Let's anyone submit a proposal, then if/when there's enough delgation power the proposal can be put to a vote.
- rough consensus
- snapshot/multi-sig
- global voting mechanism (token params)
- local voting mechanism (ecosystem mechanisms)
- [MetaGov](https://metagov.org/) is a community project working to understand and improve community governance across the interwebs.

#### Additional token mechanisms

These mechanisms can be composed into systems themselves, or added onto a template.

**Questions to ask:**

- Are there features you want that aren't available via any of the token system templates available?
- How will the addition of a feature/mechanism affect your token economy? Will it increase velocity or create a sink that locks up supply (and liquidity)?

**Examples:**

- TBD
- Find a few token systems that started as templates and extended their functionality by composing in additional mechanisms.

**Resources:**

- [Open Raise](https://github.com/dOrgTech/OpenRaise) - Open Raise is a modular library of smart contracts and UI components that bring these ideas to life and make it easy for organizations to run accountable fundraising campaigns.
- [TrojanDAO V2](https://docs.google.com/document/d/1mnUcjCKE-j4B9qraH2RkC8sEnUNw6Y2t4yF33XMRsU8/edit) (WIP) - A fundraising mechanism that has a minimum presale goal to start, an open bonding curve for the fundraise, and then flattens the curve so that participants have a propotional stake in the upcoming venture.
- [Coin Machine](https://blog.colony.io/introducing-coin-machine/) - A simple way to continually sell tokens (on Colony).
- [AraCred](github.com/aracred/) - Measure and reward contributions.
- [Airdrops]() - Because why not.
- [Liquidity mining](TBD) - Send tokens to liquidity providers.
- [LinkDrop](https://linkdrop.io/) - Put (transferable) tokens in a contract, then give people links they can use to claim tokens.
- [ArgoDisco](https://eth.taxi/blog/dao_notifications) - A Discord bot for Aragon DAO notifications ([code](https://github.com/acolytec3/ArgoDisco)).
- [Collab Land](https://collab.land/) - DAO tools to help communities improve their collaboration and coordination.
- [DAO Ops](https://medium.com/abridged-io/summoning-the-spirit-of-dao-ops-5928ee26b9d5) - Chat based interactions with DAOs.

#### Tokens

##### Fungible

The most common form of fungible Ethereum tokens is the ERC-20 token standard. ERC-20 allows for the implementation of a standard API for tokens within smart contracts. This standard provides basic functionality to transfer tokens, as well as allow tokens to be approved so they can be spent by another on-chain third party. A standard interface allows any tokens on Ethereum to be re-used by other applications: from wallets to decentralized exchanges.

An ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

Often times people will use the ERC-20 template as a base, but then add additional features and functionality on top. This ensures that the token will have the standard ERC-20 interfaces required to work with wallets, protocols, and exchanges while also incorporating additional features needed for the tokens use case.

**Resources:**

- [Ethereum.org Developer Docs: ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) - A high level overview of fungible tokens and how ERC-20 works.
- [Ethereum EIP repo Issue 20](https://github.com/ethereum/EIPs/issues/20) - The original discussion and specification for ERC-20.
- [Ethereum Improvement Proposal 20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) - The final technical specification for ERC-20.

Examples:

- [OpenZeppelin Safe ERC-20](https://docs.openzeppelin.com/contracts/3.x/erc20-supply) - A guide on how to use the [OpenZeppelin ERC-20 implementation](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/SafeERC20.sol).
- [TORN token](https://github.com/tornadocash/torn-token/blob/master/contracts/TORN.sol) - The [TornadoCash](https://tornado.cash/) token uses the OpenZeppelin Safe ERC-20 as a base, then extends additional functionality on top.

##### Non-Fungible

A Non-Fungible Tokens (NFT) is used to identify something or someone in a unique way. This type of Token is perfect to be used on platforms that offer collectible items, access keys, lottery tickets, numbered seats for concerts and sports matches, etc. This special type of Token has amazing possibilities so it deserves a proper Standard, the ERC-721 came to solve that!

The ERC-721 introduces a standard for NFT, in other words, this type of Token is unique and can have different value than another Token from the same Smart Contract, maybe due to its age, rarity or even something else.

All NFTs have a uint256 variable called tokenId, so for any ERC-721 Contract, the pair contract address, uint256 tokenId must be globally unique. Said that a dApp can have a "converter" that uses the tokenId as input and outputs an image of something cool like zombies, weapons, skills, or amazing characters.

**Resources:**

- [Ethereum.org Developer Docs: ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) - A high level overview of non-fungible tokens and how ERC-721 works. Also links to other non-fungible token standards at the bottom of the page.
- [Ethereum EIP repo Issue 721: non fungible token standard](https://github.com/ethereum/EIPs/issues/721) - The original discussion and specification for ERC-721.
- [Ethereum Improvement Proposal 721](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) - The final specification for ERC-721.

Examples:

- [ERC-721 Impleimentations](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md#references) - See the "NFT Implementations and Other Projects" section.

##### Other

Beyond fungible (ERC-20) and non-fungible (ERC-721) tokens, there are many other types of tokens. This includes, but is not limited to:

- 1450 A compatible security token for issuing and trading SEC-compliant securities
- 1155 Multi Token Standard (lots of games use this for in-game items, weapons, skins, etc..)
- 1167 Minimal Proxy Contract (some dApps and factories are using this)
- See more here: `https://eips.ethereum.org/erc`

**Questions to ask:**

- Are you creating a single or multi-token system (KISS!)?
- What type of token is the best fit for your use case fungible (ERC-20), unique (ERC-721), or exotic (ERC-XXX).
- Are tokens transferable and/or is it possible to unlock transferability via a governance decision (admin, community multi-sig, token holder vote, etc..)?
- What is the supply schedule: fixed, inflationary, variable (ex: bonding curve)?

### 1 Pager

Once you've identified a problem to solve, people who have that problem, and how you're going to solve it for them you should write it down! This will help you clarify your thinking. It will also help you communicate your vision to others. Then they might join you on your quest and/or point out ways that you might improve things.

To start, keep it simple. Just create a single page that describes what you're trying to do, why, and how. Eventually this might evolve into a formal specification, but right now we just want a rough sketch that's simple and intuitive. YOu can then update this as you design, develop, and deploy your token system. Then share it as a blog post or white paper. For now, keep it in a format (Google docs, HackMD, GitHub repo, etc..) that people can easily read, review, and comment on. This can help catch errors early on as well as engage your community.

The paper should describe the various components that are composed to achieve your goal, the properties of each mechanism, and the properties of your system as a whole.

It should also talk about why anyone could/should/would care about your token. You should explain why your token is useful (aka provide value) and how that will drive demand (resulting in a high token price). Supply and demand 101, with tokens. It ain't much, but it's honest work.

### Diagramming

Diagramming can help you refine your understanding of the system and it's components. It's also useful when you want to communicate your vision to others. There are many types of diagrams and charts, but what's best for your use case and audience may vary.

#### Causal Loop

Template for causal loop diagrams goes here.

#### Stock and Flow

Template for Stock/Flow diagram goes here.

#### cadCAD Differential Specification

[The cadCAD differential specification template](`https://community.cadcad.org/t/differential-specification-syntax-key/31`) is a good exercise to help you think through all the variables at play in your system and how they relate to each other. There's a [Figma template](https://www.figma.com/file/yBgOopbmcdkYxo2jDNmua1/cadCAD-Diff-Spec-Syntax?node-id=0%3A1) or you can create your own in your favorite diagramming software.

#### cadCAD Diagram

cadCAD diagrams can be autogenerated for any cadCAD model. It's often as simple as adding a single line of code after you run the model. The [cadCAD Diagram repo](https://github.com/cadCAD-org/cadCAD_diagram) has more information on how to set that up.

#### Technical contract specification

Solidity contract diagrams can be autogenerated via [Surya](https://github.com/ConsenSys/surya) and/or the [VSCode Soldity Visual Developer extension](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor). You can also manually create diagrams that show each function, it's inputs, and outputs. This can help you (and your community) understand the boundaries of your contract and the permissions and relationships between functions.

### Modeling

> Stuff about developing intuition on modeling goes here (go through notes and turn them into something practical).

#### cadCAD

[cadCAD](https://cadcad.org/) is a python based library for modeling complex systems. There's free and open source [demos and tutorials](https://github.com/cadCAD-org/demos). There's also some [templates](https://github.com/cadCAD-org/snippets) to help you get started with your own models. If you have questions there's a [community forum](http://community.cadcad.org/) and [Discord](https://discord.gg/cewBa9zsxS).

#### Other

- [Machinations](https://machinations.io/) - A platform and graphical interface for designing and simulating games.
- [DIY Python](https://www.python.org/) - Create your modeling framework in python like Ocean Protocol did with [TokenSpice](https://github.com/oceanprotocol/tokenspice2).

---

## Development

Once you know what you're doing and how all the pieces come together you can create a prototype.

### Platform or DIY?

> For now we're starting with Ethereum. Can't boil the ocean. That being said, the token design process is rather general and can be applied to any blockchain project.

Then once you know what you want, your resources (time/money) and technical ability will determine the tools that are the best fit:

- If you want something that works out of the box a social token platform such as CollabLand, Roll, or StakeOnMe might be a good choice. While you'll be able create a token in minutes these platforms may charge fees, have proprietary components, and/or limited customization. As such you'll likely be tied to the platform so choose wisely.
- If you want to deploy your own independent token system, but still use a template there's a few other options such as Aragon, Moloch, Liquidity Delegated governance, bonding curves, etc..
- If you really want to build something unique then rolling your own Solidity contracts is the way to go. Even still, there's some basic building blocks you might want to consider such as OpenZeppelin and (more examples go here).
- Do you want to be able to pause the contract if/when things are going wrong ('circuit breaker'), and if so, who has that power (project team, community multi-sig, token holder vote)?
- Do you want to put constraints on the amount of money that can move through the system in a single transaction (rate limiting, maximum usage)?
- Do you want to create an [upgrade path for bugfixes and improvements](https://consensys.github.io/smart-contract-best-practices/software_engineering/#upgrading-broken-contracts), or migrate to new contracts?
- Is the security of Ethereum mainnet (and it's associated cost) a feature or a bug for your use case? Would you benefit from a faster/cheaper settlement layer, and if so, is a sidechain, L2, or optimistic solution best for your use case?

#### Platform

Stuff about platforms goes here.

#### Templates

Stuff about templates goes here.

#### DIY

Within the wild world of Ethereum there are many languages to write contracts. Solidity is the most popular with many tutorials, support, and tooling. Vyper and Fe are for more advanced developers. If you're not familiar with these languages already, here's a few resources to get started.

Solidity:

- `https://docs.soliditylang.org/`
- `https://consensys.github.io/smart-contract-best-practices/`

Vyper:

- `https://vyper.readthedocs.io/`
- `https://github.com/ethereum/fe`

Fe:

`https://fe.ethereum.org/`

**Resources:**

- `https://remix.ethereum.org/`
- `https://eth.build/`
- `https://ethereum.org/en/developers/learning-tools/`
- `https://ethereum.org/en/developers/local-environment/`
- `https://consensys.net/developers/`
- `https://github.com/ConsenSys/ethereum-developer-tools-list`
- `https://consensys.github.io/smart-contract-best-practices/general_philosophy/`
- `https://github.com/OpenZeppelin/openzeppelin-contracts`
- Add that defi library/tutorial thing

Whenever you build stuff yourself remember to have a full test suite with 100% test coverage (or close to it) so that your community and/or a profession review team isn't spending time on easily avoidable errors.

- Ethereum testing resources and best practices goes here.

#### Scaling

As of the summer of 2020 summoning DAO on mainnet is often $100 USD in gas fees, up to $500. From there, simple things like adding new members and voting are $50-100 USD in gas. This prices most communities out of using mainnet for their DAOs. That being said, there are many sidechains and scaling solutions emerging to help DAOs thrive in the wild!

**xDAI:**

- [Aragon.1Hive.org](https://aragon.1hive.org/#/) - Aragon on xDAI thanks to 1Hive.
- [xDAI.DAOhaus.Club](https://xdai.daohaus.club/) - Easily spin up Moloch DAOs (V1 or V2) on xDAI via DAOhaus.

**IDchain:**

- [Aragon?](https://medium.com/brightid/introducing-idchain-392c76c31d73) - Aragon on IDchain!
- [IDchain.DAOhaus.Club](https://idchain.daohaus.club/) - DAOhaus on IDchain!

**Snapshot:**

While Snapshot isn't necessarily a scaling solution, it does allow DAO members to achieve rough consensus off-chain - potentially reducing the amount of on-chain transactions required to ratify decisions. That being said, you still have to submit transactions on-chain as Snapshot runs on a server.

- [Snapshot](https://github.com/balancer-labs/snapshot) - Verify user's token balances, then let them sign messages to create off-chain signalling votes. [Create your Snapshot page here](https://docs.snapshot.page/guides/create-a-space)!

### Auditing

On the blockchain code is law. The contract will do what is written, even if that's not what you intended. As such, it's good to have a trusted third party review your token system before deploying to production. This does not guarantee anything, but it can help - sometimes a lot. There are two main types of review to think about, economic and technical. Economic reviews look for ways to game the token system, and technical reviews look for bugs in the code.

Good reviews are expensive. They cost a lot of time and money. To get the most bang for your buck, and potentially eliminate some low hanging fruit, there's a few things you can do before a review. In the best case this will reduce the initial leg work for the review team giving them more time to dig deeper into your token system and contracts. In the worst case, even if the review team replicates your work [given enough eyes, all bugs are shallow](https://en.wikipedia.org/wiki/Linus%27s_law). As such it's important to open source your code for the community and have a bug bounty / testing program. Ideally your community continuously reviews your codebase with fresh eyes looking for bugs and unintended behavior.

All that being said, even if you don't have the capital for a professional security review we recommend that you go through this process and do as much work as you can on your own. This shows the community that you're serious about security. It also provides the opportunity for skilled community members or peers to contribute. By sharing your design process and code you're contributing to the open source community, and as a result people in the space might notice and contribute back.

#### Economic Review

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

#### Technical Review

A technical review looks for bugs in your code. This also requires having a clear specification describing the intended behavior of your contracts and the review team will also try to make them to something else. Unlike the economic analysis, however, this is likely to be more focused on exploiting the contract itself vs how the contract composes with larger systems.

Before you get a technical review, there's a few things you can do to prepare. In the best case you'll catch bugs ahead of time so that the review team can focus on deeper work. In the worst case you'll learn about Ethereum contract security and be better prepared for the review process and future contract development:

- Review [Ethereum contract development best practices](https://consensys.github.io/smart-contract-best-practices/). Know the recommended interaction patterns, check your code for anti-patterns, and run security analysis tools to catch common errors.
- Make sure you have basic docs and a technical specification. This ensures that the review team knows what you *want* the code to do. Then they can check to see if that's what it actually does.
- Read security review reports from other projects (see [here](https://consensys.net/diligence/audits/) and [here](https://github.com/trailofbits/publications#security-reviews)) to get a better idea of what to expect. Might even give you ideas of things to check/change before your audit.

Here's a few teams that provide excellent security reviews for Ethereum contracts:

- [Consensys Diligence](https://consensys.net/diligence/) - Consensys Diligence provides a comprehensive smart contract audit service to help everyone from startups to enterprises launch and maintain their Ethereum blockchain applications. They also contribute a lot of open source [reviews and tooling](https://github.com/ConsenSys) to the Ethereum community.
- [Trail of Bits](https://www.trailofbits.com/) - Trail of Bits provides a variety of services to secure and test both Web2 and Web3 software. They're a great choice if you want an end-to-end security review that goes beyond Solidity contracts. They also contribute a lot of [open source research and tooling](https://www.trailofbits.com/products) to the space.
- [TBD](TBD) - There's lots of other security firms in the space as well. If you know of any good ones please submit a PR!

---

## Deployment

### Testing

> Ideally incentivized

Once you've designed your system and gotten a review you can start to test it out! Remember, with enough eyes all bugs are shallow. With an incentivized test the community and traders can interact with your token system and potentially profit from it. Here the risk and rewards are real, but contained. This caps your downside in the event of an unexpected outcome.

If things don't go as planned, find out why and fix it. If things go smoothly, learn from your data top see if there's anything you want to change before deploying in production.

When creating incentivized tests, there's a few ways to go about it:

- [Ethereum](https://ethereum.org/) is another great place to test out your token system. You can create a beta version of your contracts for the community to test before transitioning to the full version. This beta version might have limits on the amount of tokens that can be processed or it might have a limited conversion to new tokens once you're out of beta.
- You can also deploy contracts anonymously and then test them out to ensure they function as intended before redeploying an official version.
- [xDAI](https://www.xdaichain.com/) is an EVM based blockchain. Gas fees, transaction times, and security are lower on xDAI than Ethereum mainnet. This makes it great for non-financial use cases and incentivized testing. Deploying contracts to xDAI is often as simple as switching the chainID from mainnet to xDAI.
- Beyond the Ethereum ecosystem, there are also other networks that have created incentivized testnets for developers such as Polkadot's [Kasuma](https://kusama.network/).

### Production

> Ship ship ship

Deployment tips and tools (remix, buidler, etc..) go here.

And [create a bug bounty](https://consensys.github.io/smart-contract-best-practices/software_engineering/#bug-bounty-programs)! (even if it's only in your native token1)

You might also want to have:

- documentation and user guides
- onboarding support
- community marketing/outreach

### Monitoring and analysis

Resources to monitor on-chain and community engagement goes here.

This will involve monitoring markets as well as fundamentals, both onchain (token price, distribution, hodl waves, volatility, etc...) and offchain (community engagement, etc..)

- [Apiary Explorer](https://apiary.1hive.org/orgs)
- [DAO Dashboard](https://mydaodashboard.com/)
- [DAO Metrics](https://daometrics.com/)
- [Deep DAO - Insights for a Decentralized World](http://deepdao.world/#/app/dashboard)
- [How to monitor your Aragon Organization using Tenderly](https://blog.tenderly.dev/how-to-monitor-your-aragon-organization-using-tenderly/)

### Community engagement and governance

> Talk about how analysis informs governance and governance informs what we analyze.
> Create a place for the community to discuss things and mechanisms for them to express their sentiments to affect change.

- General community best practices
- Discord server organization
- Token permissioned chats
- Giving people a reason to stay engaged
- Recognize and reward community contributors
- Governance and governance minimization

It's very very important, esp in the early days, that you curate a strong group of value aligned members. They set the foundation for the rest of the project's evolution.

How to community:

- have a clear direction with strong goals (meme)
- curate members (onboarding)
- ensure that everyone know what the token system is about and how to participate

This will be hard. It will take a long time. It will test your patience. Good luck!
Governance is hard.

This section will talk about why you might need governance (managing shared resources) and the tools you might use to do so (Snapshot, dApps, etc..).

We'll also talk about the difference between global governance and local governance, and when you might want to use one vs the other. For example, allowing decisions about how to organize Discord be managed via Discord polls but decisions on the inflation rate of your token to be managed by token holders directly.

### Upgrades

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
- DAOhaus transmutation
- Etc...

Explore ways to help your community go from consuming what you create to creating things themselves.

- Token bounties/rewards/challenges mechanisms (both for fans and creators)
- Prediction markets (on challenges fans can create for creators)
- Tipping/gifting mechanisms (give first)
- Signalling/polling mechanisms (soft governance)
- Voting mechanisms (hard governance)
- Collaborations/mergers with other projects
- 1UP
- CommonsStack praise bot
- 1Hive nominations

---
---
---

> ***Notes***

Each section should have:

- A TL;DR:
- A description
- Questions to ask
- Examples and templates
- Resources to learn more

Should add more stuff on:

- optimistic games and L2git
- community management/engagement

There should be a quickstart guide so that if someone just wants to create a token or add a feature to do a thing they can do so easily.
