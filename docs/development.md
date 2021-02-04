# Development

## TL;DR:

- Determine if any available platforms or contracts would meet your needs (or get you close). Then figure out how to build anything that's missing.
- Review your code and token system. If you're using or building off of previously audited/tested contracts the review process is a lot easier.

---

## Templates

> Moving from design to implementation.

Once we understand who's going to do what and under what circumstances, then we'll want to determine the mechanisms that will allow them to do those things.

To start, we recommend checking out the current templates and token systems live in the wild. This can give you an idea of what's available, what's working, and where you might have an opportunity to create something new and exciting. These mechanisms can be composed into systems themselves, or added onto a template.

There are many token system templates that you can use to get started. You can use them as is, modify them to suite your needs, or create something from scratch. Knowing the resources available could save you a lot of time and money. This way you can focus on the unique aspects of your system vs having to build everything from scratch.

**Questions to ask:**

- Is there currently available code (ideally audited and battle tested) that you can use to create all or part of your token system?
- Can you use templates as a base and then extend them with the additional functionality that you need?

**Examples:**

- [TORN token](https://github.com/tornadocash/torn-token/blob/master/contracts/TORN.sol) - The [TornadoCash](https://tornado.cash/) token uses the OpenZeppelin Safe ERC-20 as a base, then extends additional functionality on top.
- [Snapshot](https://docs.snapshot.page/) is a time boxed voting mechanism. It's been adopted by many projects with different types of token systems. See them in action [here](https://snapshot.page/).
- [ERC-721 Implementations](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md#references) - See the "NFT Implementations and Other Projects" section. Many started with the base NFT standard and extended it for their use case.
- [Compound Autonomous Proposals](https://medium.com/compound-finance/compound-autonomous-proposals-354e7a2ad6b7) - Let's anyone submit a proposal, then if/when there's enough delgation power the proposal can be put to a vote. This mechanism is part of Compound, but it also exists independently and many projects have forked it for their own use cases.
- [Gitcoin grants quadratic funding](https://qf.gitcoin.co/) uses a variety of signal processing mechanisms to distribute tokens based on user input. Unlike most voting systems where you vote by casting a ballot, here you vote by spending money. Learn more about Gitcoin grants [here](https://gitcoin.co/blog/towards-computer-aided-governance-of-gitcoin-grants/).

**Resources:**

> Should the Workbook focus on design patterns and then have separate pages or links for implementations?

https://ethereum.org/en/developers/docs/

**Design patterns and standards:**

Design patterns are abstract blueprints for a class of things. Popular designs are oftend turned into standards. There may be a single or multiple implementations of these design patterns.

- ERC-20:
  - [Ethereum.org Developer Docs: ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) - A high level overview of fungible tokens and how ERC-20 works.
  - [Ethereum EIP repo Issue 20](https://github.com/ethereum/EIPs/issues/20) - The original discussion and specification for ERC-20.
  - [Ethereum Improvement Proposal 20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) - The final technical specification for ERC-20.
- ERC-721:
  - [Ethereum.org Developer Docs: ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) - A high level overview of non-fungible tokens and how ERC-721 works. Also links to other non-fungible token standards at the bottom of the page.
  - [Ethereum EIP repo Issue 721: non fungible token standard](https://github.com/ethereum/EIPs/issues/721) - The original discussion and specification for ERC-721.
  - [Ethereum Improvement Proposal 721](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) - The final specification for ERC-721.
- [Bonding curves](TBD) - Explain the concept here.
- [Airdrops](TBD) - Send people tokens based on a prior heuristics. This might involve rewarding users of your protocol such as with UNI, or contributors to Gitcoin grants such as with BADGER.
- Play to Earn (AKA [Loot tokens](https://medium.com/@adamscochran/what-are-loot-tokens-understanding-an-emerging-asset-class-380b0cc38749)) - Explain how "play to earn" works here.
- [Multi-signature accounts](TBD) - Explain the concept here.
- [ERC3K](https://eips.ethereum.org/EIPS/eip-3000) - An open template for optimistic organizations.
- [Off-chain voting](TBD) - Users sign votes with their keys. Then an off-chain mechanism (often a server) checks the token balance of that key on the blockchain and uses that as an input into the voting mechanism. Then the voting mechanism runs off-chain (probably on a server) and returns a result. Ideally this is constructed in a way that participants can verify the integrity of the off-chain computation. Because this is an off-chain mechanism, if the vote needs to be enacted on-chain then an additional mechanism will be required. At the time of writing this is often a community multi-sig, however it could also be an optimistic protocol or a non-interactive cryptographic system.
- [Ranked choice voting](https://en.wikipedia.org/wiki/Ranked_voting) - Voters use a ranked (or preferential) ballot to rank choices in a sequence on the ordinal scale: 1st, 2nd, 3rd, etc.
- [Conviction voting](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475) - Proposals are passed based on the aggregated continuous preferences of community members. Token holders have to choose how to allocate their attention and voting power between proposals, and when they do they stake their voting weight behind a proposal. The amount of conviction a proposal has is a combination of time staked and the amount of tokens staked. This creates an opportunity cost between different proposals. The proposals with the most support rise to the top of a token curated list until they pass, but those without will fall to the bottom of the stack as token holders move their votes from old proposals to new ones.
- [Delegated democracy](TBD) - Delegate your votes to someone else.
- [Quadratic voting](https://en.wikipedia.org/wiki/Quadratic_voting) - Voting weight scales quadratically with the number of tokens one holds. Not sybil resistant, but only works if everyone has a single account in the system.
- [Time boxed voting](TBD) - Vote yay or nay on a thing within a window of time.
- [Wait for quite voting](https://medium.com/@dominic_w/using-wait-for-quiet-voting-in-the-dao-12ecd9d9ccc3) - Wait until voting has quited down before closing a vote.
- Token permissioned chats - Explain the concept here.

**Token creation mechanisms:**

- [OpenZeppelin Safe ERC-20](https://docs.openzeppelin.com/contracts/3.x/erc20-supply) - A guide on how to use the [OpenZeppelin ERC-20 implementation](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/SafeERC20.sol).

These resources explain the core mechanics of bonding curves:

- `https://medium.com/coinmonks/token-bonding-curves-explained-7a9332198e0e`
- `https://yos.io/2018/11/10/bonding-curves/`
- `https://blog.relevant.community/how-to-make-bonding-curves-for-continuous-token-models-3784653f8b17`
- `https://blog.relevant.community/bonding-curves-in-depth-intuition-parametrization-d3905a681e0a`
- `https://github.com/relevant-community/contracts/tree/bondingCurves/contracts`
- `https://medium.com/@billyrennekamp/converting-between-bancor-and-bonding-curve-price-formulas-9c11309062f5`
- `https://medium.com/@simondlr/bancors-smart-tokens-vs-token-bonding-curves-a4f0cdfd3388`
- `https://medium.com/thoughtchains/on-single-bonding-curves-for-continuous-token-models-a167f5ffef89`
- `https://medium.com/thoughtchains/on-bonding-curves-as-funding-mechanisms-a0812b22cc3d`
- [Bancor whitepaper](../Papers/Bancor-Conversion-Function.pdf) - OG Bancor formula
- [From curved bonding to configuration spaces](../Papers/'from-curved-bonding-to-configuration-spaces.pdf') - mZ's paper

Common curve types:

- Exponential
- Square Root
- Sigmoid
- Other

These are interactive bonding curve applications that allow you to set parameters for various types of bonding curves.

- `https://sigmoid-tbc-app.herokuapp.com/`
- `https://gitlab.com/linumlabs/bonding-curve-playground`
- `https://github.com/cadCAD-org/demos/blob/master/demos/Multiscale/bonding_curve/Bonding_Curve.ipynb`

Projects that use bonding curves in the wild.

- `https://katanapools.com/`
- `https://github.com/pRoy24/katanapools`
- Aavegotchi
- TEC Commons

**Add on mechanisms:**

Mechanisms are often implementations of designs. Sometimes mechanisms are designed and created in a single instance. In this case while there is a pattern, there's only a single instance. These will also appear in the mechanisms section as the implementation is often what people think of vs the more abstract pattern.

- [Gnosis multi-sig implementation](https://blog.gnosis.pm/gnosis-safe-multisig-desktop-app-and-contract-interactions-6f8b92c3275b) - It's a shared Ethereum account. Parameters can be set so that actions can only be taken if signatures from many accounts are provided. Those actions can including sending tokens as well as contract interactions.
- [Aragon Govern](https://github.com/aragon/govern) - Aragon's implementation of ERC3K. Optimistic organizations that use [Snapshot](https://snapshot.page/#/) for voting with the option for disputes if the vote is incorrect.
- Rough consensus - This is kind of the default, but you should be conscious about it if that's what you're going with.
- [Snapshot](https://github.com/balancer-labs/snapshot) - Verify user's token balances, then let them sign messages to create off-chain signalling votes. Perform votes off-chain, then enact on-chain via a trusted community multi-sig. [Create your Snapshot page here](https://docs.snapshot.page/guides/create-a-space). Check out current Snapshot pages [here](https://snapshot.page/#/).
- [Budget box](https://blog.colony.io/introducing-budgetbox/) - Pairwise comparisons for budgetting.
- [1Hive conviction voting](https://github.com/1Hive/conviction-voting-app). Learn more about conviction voting in general [here](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475).
- [Compound delegated voting](https://medium.com/compound-finance/delegation-and-voting-with-eip-712-signatures-a636c9dfec5e)
- [Holographic consensus](https://medium.com/daostack/holographic-consensus-part-2-4fd461e8dcde) - A governance mechanism that allows for local decisions that represent the interests of a global group.
- [MACI](https://github.com/clrfund/maci) - Minimum anti-collustion infrasctructure. Great for grants/investments DAOs.
- [LinkDrop](https://linkdrop.io/) - Put (transferable) tokens in a contract, then give people links they can use to claim tokens.
- [ArgoDisco](https://eth.taxi/blog/dao_notifications) - A Discord bot for Aragon DAO notifications ([code](https://github.com/acolytec3/ArgoDisco)).
- [Collab Land](https://collab.land/) - DAO tools to help communities improve their collaboration and coordination.
- [DAO Ops](https://medium.com/abridged-io/summoning-the-spirit-of-dao-ops-5928ee26b9d5) - Chat based interactions with DAOs.
- [Liquidity mining](TBD) - Send tokens to liquidity providers.
- [Aragon Agent](https://aragon.org/agent) - A token holder controlled address that can hold assets and interact with external contracts.
- [Moloch Minion](https://github.com/raid-guild/moloch-minion) - Like Agent, but for Molochs.

**Systems (compositions of mechanisms):**

- ***NEED TO ADD MORE DEFI AND TOKEN TEMPLATE STUFF HERE***
- `https://money-legos.studydefi.com/#/`
- [Aragon Company DAO](https://help.aragon.org/article/31-explore-the-company-organization) - Transferable token with voting and a treasury.
- [Aragon Fundraising](https://fundraising.aragon.black/) - A DAICO as described by Vitalik Buterin [here](https://ethresear.ch/t/explanation-of-daicos/465).
- [Gardens](https://forum.1hive.org/t/gardens-overview/32) - Composable community currencies.
  - TEC template: `https://github.com/TECommons/tec-template`
  - 1Hive template: `https://github.com/1Hive/gardens-template`
- [The da0](https://github.com/the-dao/whitepaper) - Description goes here.
- [Colony](https://colony.io/dev/docs/colonynetwork/intro-welcome) - Reputation based task management and dispute resolution.
- [Coin Machine](https://blog.colony.io/introducing-coin-machine/) - A simple way to continually sell tokens (on Colony).
- [Liquidity Delegated Governance](https://medium.com/@andre_54855/liquidity-delegated-governance-89184d40643a) - If you are looking for a boilerplate Liquidity Provision + Delegation + Governance + Timelock solution, all you need to do is create your token, provide liquidity to uniswap/balancer, and then call the deploy functions on the liquidity and governance factories. No multisig required and you have a fully configurable decentralized solution.
- [Buy back and make](https://www.placeholder.vc/blog/2020/9/17/stop-burning-tokens-buyback-and-make-instead) - Description goes here.
- [TrojanDAO V2](https://github.com/TROJANFOUNDATION/Trojan-DAO-Token-Engineering) - Fundraise and coordinate and manage capital with Moloch DAO and a bonding curve.
- [TrojanDAO V2](https://docs.google.com/document/d/1mnUcjCKE-j4B9qraH2RkC8sEnUNw6Y2t4yF33XMRsU8/edit) (WIP) - A fundraising mechanism that has a minimum presale goal to start, an open bonding curve for the fundraise, and then flattens the curve so that participants have a propotional stake in the upcoming venture.
- [MolochDAO](https://github.com/MolochVentures/moloch/tree/minimal-revenue/v1_contracts) - Coordinate and manage capital.
- [MolochDAO V2](https://github.com/MolochVentures/moloch) - Coordinate and manage capital.
- [MolochDAO V3](https://github.com/Moloch-Mystics) - Modular Moloch - plug and play DAO legos (WIP).
- [LAOland](https://github.com/openlawteam/laoland) - More modular moloch (WIP).
- Moloch (community w bank account)
  - Minion
  - Transmutation
  - Modular
- [Moloch V1 source code](https://github.com/MolochVentures/moloch/tree/master/v1_contracts) - The original Moloch. It's simple and effective. Start here.
- [Moloch Subgraph highlight](https://medium.com/graphprotocol/moloch-subgraph-highlight-faf9da2f7e73) - An overview of the Moloch subgraph from late 2019.
- [Moloch V2 source code](https://github.com/MolochVentures/moloch) - The V2 MolochDAO code and docs. Very informative. If you have to pick one, read this instead of all the other blog posts.
- [Moloch V2 audit report blog post](https://medium.com/@thelaoofficial/moloch-v2-smart-contract-audit-report-for-the-lao-48fb0415695a) - Overview of the Moloch V2 audit(the process of applying any design feature or control mechanism that maintains and steers a system)
- [Moloch V2X](https://medium.com/lexdaoism/introducing-moloch-dao-v2x-mystic-ethereum-contract-upgrades-c7984801d4db) - Moloch V2 with some extra features.
- [Summoning 101](https://medium.com/totle/summoner-101-expectations-of-launching-your-own-moloch-dao-d6bb0fbbe600) - What you should expect when summoning a Moloch DAO.
- [How to summon a Moloch DAO](https://bankless.substack.com/p/how-to-start-a-moloch-dao) - A [Bankless](https://bankless.substack.com/) tutorial on summoning a Moloch DAO.
- [How to summon a LAO](https://bankless.substack.com/p/how-to-create-a-bankless-dao) - How to summon a Moloch DAO with a legal wrapper.
- [Moloch V3 WIP](https://github.com/openlawteam/moloch) - Exploring a modular Moloch.
- [Moloch Minion FAQ](https://github.com/DAOresearch/awesome-daos/issues) - A rolling list of FAQ around Moloch Minions.
- [RaidGuld Minion](https://minion.raidguild.org/) - An example of a minion live in the wild.
- [Moloch Minion contract extensions](https://github.com/raid-guild/moloch-contract-extensions) - Contracts that extend the functionality of minions.
- [The LAO's Minion blog post](https://medium.com/@thelaoofficial/the-path-to-unaccredited-daos-with-minion-8113213f7195) - Overview of Moloch minion with a few use cases related to investment DAOs.
- [ScoutDAO](https://discourse.thelao.io/t/scoutdao/48) - Yet another minion use case, this time related to creating a shared account multiple Molochs can jointly manage.
- [Qaudratic Moloch](https://github.com/DemocracyEarth/DemocracyDAO) - A MolochDAO with quadratic voting built in.
- [Moloch L2 voting via merle tries](https://github.com/openlawteam/moloch/issues/2) - An exploration of off-chain voting with on-chain resolution in Moloch DAOs.
- [Open Raise](https://github.com/dOrgTech/OpenRaise) - Open Raise is a modular library of smart contracts and UI components that bring these ideas to life and make it easy for organizations to run accountable fundraising campaigns.
- [AraCred](github.com/aracred/) - Measure and reward contributions.

**Communities:**

- [GovBase](https://github.com/thelastjosh/govbase) - An open database of projects and tools in online governance. Learn more about it [here](https://thelastjosh.medium.com/introducing-govbase-97884b0ddaef) and check out the [Govbase GitHub repo](https://github.com/thelastjosh/govbase) if you want to contribute.
- [MetaGov](https://metagov.org/) is a community project working to understand and improve community governance across the interwebs.
- [Commons Stack](https://commonsstack.org/) - A community focused on helping people coordinate and sustain common goods.
- TokenEngineering Community

---

**Resources:**

https://ethereum.org/en/developers/docs/programming-languages/

**Solidity:**

https://github.com/cryptofinlabs/audit-checklist

**Vyper:**

- [Vyper](https://github.com/vyperlang/vyper) - Ethereum python.
- [Brownie](https://github.com/eth-brownie/brownie) - Like Truffle, but for Vyper.
- [Awesome Vyper](https://github.com/spadebuilders/awesome-vyper) - All the good Vyper things.
  - [Tools](https://github.com/vyperlang/vyper/wiki/Vyper-tools-and-resources)
  - [Vyper.fun](https://vyper.fun/)
- [Live Vyper contracts](https://github.com/search?q=def+path%3Acontracts+extension%3Avy) - Live and loaded!
  - [Curve](https://github.com/curvefi/curve-contract)
  - [ERC721](https://github.com/maurelian/erc721-vyper)
- [Vyper docs](https://vyper.readthedocs.io/) - Knowledge is power.

**Fe:**

https://github.com/ethereum/fe/
https://twitter.com/official_fe
https://snakecharmers.ethereum.org/fe-a-new-language-for-the-ethereum-ecosystem/

---

## Building

Once you know what you're doing and how all the pieces come together you can create a prototype. This might look like using a platform (fast/cheap), open source contracts (medium difficulty and cost), or roll your own token system (expensive and time consuming). Which option is best for you will likely be determined by your resources (time and money) and technical ability/interest. 

If you're creating something really unique rolling your own contracts is the way to go, but otherwise there's a good chance that one of the currently available contracts/platforms can get you 80% of the way there for 20% of the effort. From there you can customize your token system to become whatever you want.

Within the wild world of Ethereum there are many languages to write contracts. [Solidity](https://docs.soliditylang.org/) is the most popular with many tutorials, support, and tooling. [Vyper](https://vyper.readthedocs.io/) and [Fe](https://fe.ethereum.org/) are also good, but are newer and less supported. If you're not familiar with these languages already, here's a few resources to get started.

If you choose to build your own contracts remember to have a full test suite with 100% test coverage (or close to it) so that your community and/or a profession review team isn't spending time on easily avoidable errors.

**Questions to ask:**

- Do you want to be able to pause the contract if/when things are going wrong ('circuit breaker'), and if so, who has that power (project team, community multi-sig, token holder vote)?
- Do you want to put constraints on the amount of money that can move through the system in a single transaction (rate limiting, maximum usage)?
- Do you want to create an [upgrade path for bugfixes and improvements](https://consensys.github.io/smart-contract-best-practices/software_engineering/#upgrading-broken-contracts), or migrate to new contracts?

**Examples:**

- Extremely well developed, tested, and documented projects go here.

**Resources:**

- If you want something that works out of the box a social token platform such as CollabLand, Roll, or StakeOnMe might be a good choice. While you'll be able create a token in minutes these platforms may charge fees, have proprietary components, and/or limited customization. As such you'll likely be tied to the platform so choose wisely.
- If you want to deploy your own independent token system, but still use a template there's a few other options such as Aragon, Moloch, Liquidity Delegated governance, bonding curves, etc..
- If you really want to build something unique then rolling your own Solidity contracts is the way to go. Even still, there's some basic building blocks you might want to consider such as OpenZeppelin and (more examples go here).
- `https://docs.soliditylang.org/`
- `https://consensys.github.io/smart-contract-best-practices/`
- `https://vyper.readthedocs.io/`
- `https://github.com/ethereum/fe`
- `https://fe.ethereum.org/`
- `https://remix.ethereum.org/`
- `https://eth.build/`
- `https://ethereum.org/en/developers/learning-tools/`
- `https://ethereum.org/en/developers/local-environment/`
- `https://consensys.net/developers/`
- `https://github.com/ConsenSys/ethereum-developer-tools-list`
- `https://consensys.github.io/smart-contract-best-practices/general_philosophy/`
- `https://github.com/OpenZeppelin/openzeppelin-contracts`
- Add that defi library/tutorial thing
- Ethereum testing resources and best practices goes here.

---

## Audits and Reviews

On the blockchain code is law. The contract will do what is written, even if that's not what you intended. As such, it's good to have a trusted third party review your token system before deploying to production. This does not guarantee anything, but it can help - sometimes a lot. There are two main types of review to think about, economic and technical. Economic reviews look for ways to game the token system, and technical reviews look for bugs in the code.

Good reviews are expensive. They cost a lot of time and money. To get the most bang for your buck, and potentially eliminate some low hanging fruit, there's a few things you can do before a review. In the best case this will reduce the initial leg work for the review team giving them more time to dig deeper into your token system and contracts. In the worst case, even if the review team replicates your work [given enough eyes, all bugs are shallow](https://en.wikipedia.org/wiki/Linus%27s_law). As such it's important to open source your code for the community and have a bug bounty / testing program. Ideally your community continuously reviews your codebase with fresh eyes looking for bugs and unintended behavior.

All that being said, even if you don't have the capital for a professional security review we recommend that you go through this process and do as much work as you can on your own. This shows the community that you're serious about security. It also provides the opportunity for skilled community members or peers to contribute. By sharing your design process and code you're contributing to the open source community, and as a result people in the space might notice and contribute back.

You can also [create your own bug bounty](https://consensys.github.io/smart-contract-best-practices/software_engineering/#bug-bounty-programs). While initially this might not seem like a lot, it shows that your serious and might attract contributors who believe in thye project. Just be aware that, without a staking mechanism, any bounty shown on your website or forum requires trust that you'll follow through. Often just the fact that you have thought through and setup a bug bounty program is enough, but there's still a lot of trust between all parties involved here. Some contributors might discount your offering based on their perception of your ability/liklihood to follow through so don't be stingy when it comes to community rewards for something as critical as security.

## Economic Review

An economic review will involve reviewing your token system and testing it for unintended behavior. This requires you to first clearly state what you want the system to do. Then token engineers will try to find all the ways to make it do something else. If your system is designed correctly it's intended properties should hold. In addition, the system should specify under what conditions it is expected to hold (no 51% attack, ETH > 0, TOKEN > 0, etc..).

Before you get started with an economic review, there's a few things you can do to prepare. In the best case you'll catch unintended outcomes ahead of time so that the review team can focus on deeper work. In the worst case you'll learn about Ethereum token economics and be better prepared for the review process and future token system design:

- Resources go here.
- Common blunders such as relying on an AMM as an oracle (and then having that oracle report unexpected values via flash loans) (flashloan sandwich)
- Ensure that admins can't mint/burn tokens arbitrarily
- If your system has governance, think through the difficulty of getting things passed, esp how that difficulty will change over time if you have tokens that are vesting and not yet liquid or if you have "token sinks" that will have people locking up tokens (liquidity mining, derivative tokens, etc..)
- If you have an inflationary token think through how token holders will create value to drive more demand than inflation. What does the best case and worst case scenario look like? How can you create [minimax](https://en.wikipedia.org/wiki/Minimax) strategies that reduce risk and maximize the chance of sustainability?

At the moment there are not very many firms who specialize in this type of economic analysis. With the popularity of DeFi we expect this list to grow. For now, here's a few teams that provide token system designs and reviews:

**Questions to ask:**

- TBD

**Examples:**

- Examples of tokenomic reviews go here.

**Resources:**

- [BlockScience](https://block.science/) - An engineering, R&D, and analytics firm specializing in complex systems. Our focus is to design and build data-driven decision systems for new and legacy businesses leveraging engineering methodologies and academic-grade tools. Blockscience [open sources a lot of their work](https://github.com/blockscience) including past projects and even their system modeling library ([cadCAD](https://github.com/BlockScience/cadCAD-Tutorials))
- [Gauntlet](https://gauntlet.network/) - Gauntlet’s mission is to help make blockchain protocols and smart contracts safer and more trustworthy for users. At the time of writing their projects and tooling are proprietary.
- [TBD](TBD) - More teams coming soon.

## Technical Review

A technical review looks for bugs in your code. This also requires having a clear specification describing the intended behavior of your contracts and the review team will also try to make them to something else. Unlike the economic analysis, however, this is likely to be more focused on exploiting the contract itself vs how the contract composes with larger systems.

Before you get a technical review, there's a few things you can do to prepare. In the best case you'll catch bugs ahead of time so that the review team can focus on deeper work. In the worst case you'll learn about Ethereum contract security and be better prepared for the review process and future contract development:

Notes:

- As much as possible use standards (WASM) or battle tested mechanisms (OpenZeppelin). You don't want to roll your own crypto, contracts, or blockchain unless you really need it.
- If you contracts depend on or connect with any other contracts (DeFi integrations, price feeds, or external code libraries), your system security is also dependent on those external factors. Make sure you understand how secure things you connect with are, as well as what their process is for upgrades and governance. Otherwise, a contract you connect to that looks good now might change in the future, resulting in unintended interactions. As much as possible, embed all dependencies to ensure you’re always in control of what you’re doing.
- With enough eyes all bugs are shallow. Connecting with the developer community is not just good for creating new things, but also security. It should be clear how to ask questions and raise issues if bugs are found. Everyone should feel comfortable speaking up. Don't build in a bubble! Ex: [yEarn created yAcademy](https://gov.yearn.finance/t/yip-53-yacademy-planting-the-seed-of-a-sustainably-secure-future-for-yearn-and-beyond/7929) to help the community learn about and participate in security auditing and testing of their contracts.
- Software bugs are a matter of “when” and “how bad”, not “if”. We must make mitigation efforts.

**Examples:**

- Examples of security audit reports and repos goes here.
- Ensure that the content addressed contracts that are deployed are the ones that were audited.

**Questions to ask:**

- Review [Ethereum contract development best practices](https://consensys.github.io/smart-contract-best-practices/). Know the recommended interaction patterns, check your code for anti-patterns, and run security analysis tools to catch common errors.
- Make sure you have basic docs and a technical specification. This ensures that the review team knows what you *want* the code to do. Then they can check to see if that's what it actually does.
- Read security review reports from other projects (see [here](https://consensys.net/diligence/audits/) and [here](https://github.com/trailofbits/publications#security-reviews)) to get a better idea of what to expect. Might even give you ideas of things to check/change before your audit.

**Resources:**

- Ethereum contract auditing tools go here.
- https://ethereum.org/en/developers/docs/security/
- [Consensys Diligence](https://consensys.net/diligence/) - Consensys Diligence provides a comprehensive smart contract audit service to help everyone from startups to enterprises launch and maintain their Ethereum blockchain applications. They also contribute a lot of open source [reviews and tooling](https://github.com/ConsenSys) to the Ethereum community.
- [Trail of Bits](https://www.trailofbits.com/) - Trail of Bits provides a variety of services to secure and test both Web2 and Web3 software. They're a great choice if you want an end-to-end security review that goes beyond Solidity contracts. They also contribute a lot of [open source research and tooling](https://www.trailofbits.com/products) to the space.
- Parity, who creates a lot of open source blockchain clients and code, created a [14 point checklist for secure smart contract development](https://www.parity.io/paritys-checklist-for-secure-smart-contract-development/). Lots of great tips on the development/deployment process (whereas the Consensys and Trail of Bits links focus more on contract architecture and testing).
- [TBD](TBD) - There's lots of other security firms in the space as well. If you know of any good ones please submit a PR!
