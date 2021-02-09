# Design

- [Design](#design)
  - [TL;DR:](#tldr)
  - [Brainstorming](#brainstorming)
    - [Problem Discovery](#problem-discovery)
    - [Do you need a token?](#do-you-need-a-token)
    - [Incentive Alignment](#incentive-alignment)
    - [Resources](#resources)
  - [Mechanism Design 101](#mechanism-design-101)
    - [Properties](#properties)
    - [System mapping](#system-mapping)
    - [Neutrality](#neutrality)
    - [Governance](#governance)
    - [Resources](#resources-1)
  - [Mechanism Design 102](#mechanism-design-102)
    - [Concepts](#concepts)
    - [Patterns](#patterns)
    - [Systems](#systems)
  - [Mechanism Design 103](#mechanism-design-103)
    - [From Curved Bonding to Configuration Spaces](#from-curved-bonding-to-configuration-spaces)
    - [Economic Games as Estimators](#economic-games-as-estimators)
    - [Translating Commons-Based Peer Production Values into Metrics: Towards Commons-Based Crypto-Currencies](#translating-commons-based-peer-production-values-into-metrics-towards-commons-based-crypto-currencies)
  - [Diagramming](#diagramming)
  - [Modeling](#modeling)
  - [Whitepaper](#whitepaper)

<br />

## TL;DR:

- Find a problem to solve.
- Understand who has that problem, why, how often, and how painful it is for them.
- Create a solution that's 10X better.
- Determine if a blockchain and a token system really makes sense.
- If so, define roles, methods, states for all the stakeholders who will participate in your token system (end users, providers, developers, community, etc..).
- Explore mechanisms that can help you create that system. Then if there's some you can use or modify compose them into a token system.
- Draw a picture describing the token system. Ideally showing not just the things, but the relationships between the things and how one thing affects another.
- Create a model simulating how users might interact with the token system.
- Write a blog post describing the token system. Focus on incentive alignment and checks and balances on power for all parties involved.
- Share with the community for feedback and contributions. Refine and revisit everything to make it better.

<br />

## Brainstorming

### Problem Discovery

> Start with why.

The bigger the problem you can solve, for the most people, the more value you can create (and capture).

Ideally you want a problem that is:

- Popular (lots of people have it)
- Growing (more and more people have it)
- Frequent (they experience it a lot)
- Expensive (it's hard to solve)
- Mandatory (it must be solved)

You should be able to explain the problem you're solving, [why](https://simonsinek.com/product/start-with-why/) it's important, and how the world will be better once you've solved it. Everyone should get it. It should be so obvious they ask why they didn't think of it first. Ideally it can become a [meme](https://en.wikipedia.org/wiki/Meme). If people don't get it, work to make it simpler or find a better problem to solve.

**Questions to ask:**

- What problem do you want to solve?
- What will the world look like after you solve it?
- Who will benefit and why should they care?
- What problem are you solving?
- Who has this problem? How often?
- How much do they need this problem to be solved?

### Do you need a token?

> Keep it simple.

Now that you've identified a problem what's the best way to solve it? Often times it's not a blockchain or a token. Blockchains allow you to create credible commitments. This can be great for monetary policies, permissionless applications, and more. Any time you need to shift the trust from subjective human enforcement to deterministic computer enforcement a blockchain might help. Anytime you need to align incentives and power between multiple (untrusting) parties a token might help. But it might not. Before jumping to creating a blockchain application and token it's important to check to see if there's any way you can achieve your goal without it. If and only if the blockchain version is 10X better should you proceed.

**Questions to ask:**

- Is there any part of your token system (including the token itself) that could be removed while still achieving your goals?
- If you substitute a stable coin or ETH with your token will things still work? If so, then you probably don't need to create a new token.
- Does the blockchain change the system of trust in any meaningful way, or just shift it around? Does it just try to replace trust with verification?
- Does the token create new trust relationships or strengthen existing trust relationships?
- What would your system look like if you didn’t use blockchain at all?

### Incentive Alignment

> Positive-sum games => growth => network effects.

Tokens can give holders the right to use the network, participate in governance, and benefit from increased demand if/when the network is successful. If you have a token it's purpose should be clear. Incentives should be aligned for all parties involved. Everyone who contributes to the network should have tokens. When the network succeeds demand for tokens should go up. As a result token price (and/or actions to earn tokens) should increase.

If you have governance power should be balanced between all parties involved. If one stakeholder group captures power things will likely not work out. Common stakeholders include, but are not limited to: developers, service providers, investors, and end users. Even if you don't have formal on-chain governance stakeholders should have a way to share their ideas and voice their opinions. Then you can [increase voice and loyalty instead of exit](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty).

**Questions to ask:**

- How will your token contribute to solving this problem?
- What is the value prop of your token (access, unique items, discounts, governance, etc..)? Why would anyone want it?
- Will your token incentivizing people to do work to solve the problem directly, or will it be a component of a larger system that's working to solve that problem? If so, why?
- Tokens are scarce digital assets that people can own. Is there an opportunity for your token to turn what was preciously an expenditure into an investment? Ex: buying computation credits can now go from an expense to an investment in a decentralized computation system.

### Resources

Many of the ideas in this section came from the following resources:

- [a16z](https://a16z.com/crypto/) has a [crypto startup school](https://a16z.com/crypto-startup-school/). It has lots of content explaining high level concepts that are essential for the space. You can also sign up for their newsletter to get ongoing insights delivered to your inbox. They also have a [tldr version here](https://a16z.com/2020/12/28/crypto-users-guide/).
- [YC's Startup School](https://www.startupschool.org/) is a great resource to help you make something people want. The [How to find startup ideas](https://www.youtube.com/watch?v=DOtCl5PU8F0) video can help build intuition for what types of problems to solve. Might help you avoid spending time working on the wrong thing. While YC is focused on startups, a lot of the same concepts around solving problems and creating value for users apply to both startups and token projects. Highly recommend checking out [their videos](https://www.youtube.com/channel/UCcefcZRL2oaA_uBNeo5UOWg).
- [The idea maze](https://a16z.com/tag/idea-maze/) can help you navigate the wild world of emerging technologies.
- [Simon Sinek](https://simonsinek.com/) has a lot of great content explaining why you should [start with why](https://simonsinek.com/product/start-with-why/).
- [Bruce Schneier](https://www.schneier.com/blog/archives/2019/02/blockchain_and_.html) has some great points as to why you might not want a blockchain. You should only use a blockchain if you really need one.

<br />

## Mechanism Design 101

> Developing intuition.

### Properties

Before jumping into design, or even implementation, it's good to think about the [properties and values you want the token system to express](https://www.youtube.com/watch?v=6ufHL5AkBEA). These should be concrete properties that your system will maintain under all conditions. This way with each mechanism you add to your system, and the system as a whole, you can ask yourself if would enhance or take away from the core principles. Some common principles many Web3 projects strive for are:

- **Permissionless:** anyone can interact with the contracts.
- **Trustless:** the contract run deterministically.
- **Secure:** the code does what it says it does without unexpected behavior.

Then once you know what you want to do, you have to figure out how. First know what you want to do, then find tools that can help you do it. Don't start with the tools! If you do you'll become a man with a hammer. Choose the tools based on your goals and design constraints, not the other way around.

The first step is just describing what you want to do. Write it down. You should be able to answer who, what, when, where, why.

### System mapping

![IAD](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9d/IAD_framework_diagram.png/400px-IAD_framework_diagram.png)

A way to define these things in the context of a digital system is rights, roles, and access. Who can do what and under what circumstances. This is similar to [Ostrom's institutional analysis and development framework](https://en.wikipedia.org/wiki/Institutional_analysis_and_development_framework) as well as [linux system permissions](https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-permissions).

- **State:** all of the information in the system.
- **Users:** actors who can engage with the system.
- **Actions:** things users can do.
- **Rights:** the authority to take an action or access part of the state.
- **Roles:** bundles of rights assigned to users.

Starting with "who," users/stakeholders might include:

- **End users:** acquire tokens to access goods and services.
- **Service providers:** provide services to earn rewards.
- **System designers:** design tokenomic systems for fun and profit.
- **Community developers:** build software for fun and profit.
- **Third-party developers:** create integrations for their product or service.
- **Protocol politicians:** create and/or explain governance proposals to other stakeholders.
- **Investors:** contribute capital and do work to improve their investments.
- **Traders:** mercenary capital that chases opportunities such as market volatility, arbitrage, portfolio diversification, etc..

The state of your system will be the "what" and the 'where." A blueprint of the system. This is what you'll have at the end of the design phase.

"When" explores how your system handles time. If you have governance this will often relate to voting or delay windows before actions can be taken.

To answer "how" we need to map actions to mechanisms. Mechanisms are how methods get instantiated. First just describe each mechanism and what it should do. Then as your token system evolves you can add more details.

Then once you have a set of mechanisms you can define who can engage with those mechanisms. Roles are a way to group assignments of rights to actors within the system. If you're familiar with linux permissions this is similar to user groups. In this case, however, we're assigning rights to tokens. Then addresses holding tokens will have a role and the rights associated with it.

You might also want to think about the process to modify the rights associated with roles. This would add a layer of [meta governance](https://en.wikipedia.org/wiki/Governance#Metagovernance) to the system enabling actors to change the system itself. This is a double edged sword. More [flexibility allows for adaptation, but also decreases stability](https://thedefiant.substack.com/p/we-need-to-re-think-decentralized-5df). The more a system can change the more power shifts from the mechanism design to the subjective judgement of actors within the system.

At this point everything should still be high level. We're not choosing a programming language, framework, blockchain or L2 solution. We're just describing the system.

**Questions to ask:**

- Can you easy answer who, what, when, where, and why questions about your token system?

### Neutrality

Decentralized protocols are valuable because they create credible commitments about the rules of the game. You can read the code, understand how the system works, and know that everyone interacting with the system has to play by the same rules. When this happens tokens systems can be said to be [credibly neutral](https://nakamoto.com/credible-neutrality/).

Rights access paradigms are a way to explicitly model and reason through [the fairness of your token system](https://en.wikipedia.org/wiki/Original_position). To do this we need to map out rights and access controls to show who can do what, how people can move through the system, and how the system itself can be changed (if at all). This way everyone can engage with full information.

Once the system is mapped out everyone can see the roles available as well as the path to move from one role to another. This might be as simple as acquiring tokens to stake or as complex as drafting a governance proposal to create the changes you want to see. It's important that this process feels fair. There needs to be a meaningful way to contribute to and level up within the system. Projects with high degrees of agency and mobility tend to attract more users and contributors. This can help you grow faster and/or save you time and money on marketing simply because incentives are aligned for all parties involved.

**Questions to ask:**

- Do all parties involved in your token system (end users, service providers, token holders, etc..) have tokens so that they can participate in the financial upside and management of the token system? If not, why not? How can you enable more stakeholders to participate in a meaningful way?
- Do you feel like your token system if "fair?" If so, would you be comfortable being dropped into a random role in the system?

### Governance

Some systems need human input. If so, then you have a governance problem. How you solve this coordination problem depends on what you're trying to achieve. Any governance solution you choose is a means to an end, not an end in itself. It needs to be simple and intuitive. Then people can collectively create the changes they want.

Another way of framing this is as a rights/roles access problem. Through this lens it should be clear what the rules actually are, who can do what when, and how people participating in the system can change the rules of the system. This way everyone has complete information.

Then once people know what's going on, even if they don't agree with every decision, they can at least respect the process that resulted in that decision. This is very important. We don't need complete agreement on every decision, but we do need to agree on how we make decisions.

Then players who choose to play the game will have [voice, loyalty, and exit](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty). Everyone will have all the information they need to create informed opinions. They'll have a process to share ideas and affect change. They'll also be able to leave the system if they disagree with decisions being made. The more agency players have the more their loyalty to the game will increase. While this can be intense and time consuming, it's a good sign that [people care](https://www.pet3rpan.net/blog/why-do-people-care).

If you don't want to design a governance process from day 1 you can leave it as an upgrade for the future. You don't have to choose right now, but it's important to think about. Thyen in the future if you want to set control of contracts to a community multi-sig or DAO in the future you can, but you could also set it to the 0 address so that the contract becomes immutable.

**Questions to ask:**

- Are there aspects of your system that will need to adapt and change over time? If so, who has the right to make that change? What is the process to make that change?
- Is it possible to change the process to make changes (meta-governance)?
- It's very important to make your governance process as simple as possible. Is there any way for you to minimize governance while still giving users control over your token system?

### Resources

- Vitalik's blog has a great [coordination post](https://vitalik.ca/general/2020/09/11/coordination.html) that can help you build intuition around aligning interests for all parties involved in a token system.
- The [Wikipedia mechanism design page](https://en.wikipedia.org/wiki/Mechanism_design). Is a great place to start. If you read one thing on mechanism design, make it this. There's also a whole [category on Wikipedia dedicated to the topic](https://en.wikipedia.org/wiki/Category:Mechanism_design).
- The [Wikipedia token economy](https://en.wikipedia.org/wiki/Token_economy) page is also rather informative. While many of the examples are based in the context of psychiatric care, the concepts generalize to any incentive system.
- [a16z's crypto startup school](https://a16z.com/2020/12/28/crypto-users-guide/) has a great talk with Sam Williams from [Arweave](https://www.arweave.org/) exploring [how to think about incentives in token systems](https://www.youtube.com/watch?v=gCFlGLbI_kE).
- The Foundations of Cryptoeconomic Systems [lecture](https://www.youtube.com/watch?v=HldQF_MJN_Y) and [paper](https://epub.wu.ac.at/7309/) can help you build intuition around token system design. Beyond that, all the [resources on the BlockScience website](https://block.science/resources) are good.
- [Web3 Revenue Primitives](https://github.com/FEMBusinessModelsRing/web3_revenue_primitives) - An open source list of business models that might be helpful for Web3 projects.
- If you're going to include governance Placeholder VC has a post exploring [ten thesis on decentralized network governance](https://www.placeholder.vc/blog/2020/9/30/ten-theses-on-decentralized-network-governance).
- [A Token Engineering Process](https://medium.com/@stephen_yo/a-token-engineering-process-16687f3b9a74) - Great article that covers the basics of system mapping and diagramming in the context of token engineering. More great articles on the token engineering process [here](https://blog.oceanprotocol.com/towards-a-practice-of-token-engineering-b02feeeff7ca) and [here](https://medium.com/block-science/on-the-practice-of-token-engineering-part-i-c2cc2434e727)
- [Re-thinking decentralized governance](https://thedefiant.substack.com/p/we-need-to-re-think-decentralized-5df) - Blake West has some great points on why you want to minimize governance to maximize protocol decentralization and autonomy.
- [Linux permissions](https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-permissions) can provide a simple way to think about rights, roles, and access at a system level.
- [Original position](https://en.wikipedia.org/wiki/Original_position) describes how to think through desigining a system that is fair and egalitarian.
- [Exit, voice, and loyalty](https://en.wikipedia.org/wiki/Exit,_Voice,_and_Loyalty) are important concepts to think about as you're designing the available action space for stakeholders.
- [Token Engineering community](https://tokenengineeringcommunity.github.io/website/) - A community working to further the discipline of token engineering through education and outreach. Check out their [Library](https://tokenengineeringcommunity.github.io/website/docs/library-te-101) for more resources.
- [CommonsStack](https://commonsstack.org/) - A community working to create templates and best practices to realign incentives around public goods.
- [cadCAD Edu](https://www.cadcad.education/) is a great resource to learn about the token engineering process. While it's focused on cadCAD, the Complete Foundations Bootcamp is a great intro to the token engineering design process as a whole.

<br />

## Mechanism Design 102

> Primitives and patterns.

Depending on your use case you might want to use or modify a popular system or roll your own. That being said, being able to think about system design from [first principles](https://waitbutwhy.com/2015/11/the-cook-and-the-chef-musks-secret-sauce.html) can help you understand, modify, and optimize your token system to achieve your goals. Given how outcomes in community economies are non-linear, a small nudge in the right direction could have a large impact. You might also want to roll your own token system from scratch and design something completely new! That's cool too, and if so, you'll definitely want to have all the tools available at your disposal.

To explore system design from first principles it helps to think of it as a language. Shared language and ideas make it easier to coordinate. System design is an expression of ideas. As a language it might look something like:

- concepts => words
- patterns => sentences
- systems => paragraphs

With a shared system design grammar we can read and write in that language. This allows us to reason about systems from first principles. Rather than relying on blog posts or hand wavey statement, we can actually understand what systems do and why. We can also start to explore how we might modify systems to solve new problems. This can be helpful for system design as well as community engagement and governance.

Let's explore what we mean by concepts, patterns, and systems.

### Concepts

This section explores core concepts token system design. If you imagine a tree, these would be the trunk that branches and leaves build on.

There are many concepts more fundamental than the ones we describe here. Those are often called [primitives](https://en.wikipedia.org/wiki/Primitive). They're the roots of the tree. The simplest form of an idea that cannot be broken down further. These are very useful to understand!

Some core token design concepts could be thought of as primitives, but others as compositions. While classification is important, that's not the focus here as it varies from field to field. Context is important. This section is to explore core concepts in the context of token systems.

**[Cryptography](https://en.wikipedia.org/wiki/Cryptographic_primitive):**

- [One-way hash function](https://en.wikipedia.org/wiki/One-way_hash_function) — compute a reduced hash value for a message (e.g., SHA-256)
- [Symmetric key encryption](https://en.wikipedia.org/wiki/Private_key_cryptography) — Compute a ciphertext decodable with the same key used to encode (e.g., AES)
- [Public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) — encrypt data with a public key that is then only decodable with the corresponding private key (e.g., RSA)
- [Digital signatures](https://en.wikipedia.org/wiki/Digital_signatures) — cryptographically sign data with a private key in a way that's verifiable via a public key.
- [Mixers](https://en.wikipedia.org/wiki/Mix_network) — pool data from many users to anonymize what came from whom
- [Zero knowledge proofs](https://en.wikipedia.org/wiki/Zero-knowledge_proof) — verify the integrity of a request or computation without revealing any information about the data being requested or processed.
- [Commitments](https://en.wikipedia.org/wiki/Commitment_scheme) — commit to a chosen value while keeping it hidden to others, with the ability to reveal it later
- [Pseudorandom number generation](https://en.wikipedia.org/wiki/Cryptographically_secure_pseudorandom_number_generator) - generate a number that is as good as random within the context in which it's being used.
- [More cryptographic primitives](https://en.wikipedia.org/wiki/Category:Cryptographic_primitives)

**Economics:**

- linear functions
- exponential functions
- quadratic functions
- payments (send money)
- payment requests (invoices)
- markets (places where buyers and sellers can exchange assets if they agree on a price)
- exchange rate (the price buy/sell one asset for another according to a policy - can be algorithmic or based on market activity)
- options (a contract that gives the holder the option to buy or sell an asset at a specific price at a specific time - they are financial assets that can be bought and sold just like anything else)
- insurance (a contract that provides payouts dependent on a policy)
- interest rates (time dependent payments)
- lending (give assets for an IOU, often with interest payments)
- borrowing (get assets for an IOU, often with interest payments)
- collateral (assets locked until the IOU is paid or forfeit in order to pay off the IOU)
- credit scores (risk assessment for undercollateralized lending)
- supply schedule (the rate of inflation or deflation of a currency)

**Blockchains:**

- gas
- block number
- addresses (pub/priv key crypto, hold/send/receive tokens, create cryptographic signatures)
- fungible tokens
- non-fungible tokens
- mint/burn tokens
- stake tokens (lockup)
- constant function market makers

**Game theory:**

- credible commitments
- small vs large games
- zero sum vs positive sum games
- cooperative or individual games
- fixed vs iterated games
- sequential vs simultaneous games
- pareto optimal outcomes
- dominant strategies
- game warping (changing player's available action set and/or incentives)
- games with complete vs incomplete information

**Governance:**

- simple majority policy
- super majority policy
- X of Y policy
- quadradic
- conviction
- ranked choice
- wait for quiet (vote, time delay, quiet policy)
- time boxed or continuous
- simple or super majority
- direct or delegated

### Patterns

> Things that do things

Design patterns compose primitives into mechanisms that perform a function. How these mechanisms are then used varies. Patterns can be said to be neutral as they are abstract ideas. Instances, however, are opinionated based on the context and purpose of each unique instance IRL.

**Examples of patterns:**

- send (check balance, change balance)
- tipping (send)
- swap (token, vault, check balance, exchange policy, send)
- voting (check balance, voting policy)
- commit/reveal (check balance, commit, reveal)
- auction (bid, escrow, commit/reveal, auction policy, swap)
- conviction voting (check balance, stake, vesting policy, voting policy)
- time delay (que action, check time, action execution policy)
- redemption (token, vault, check balance, redemption policy)
- rage-quit (time delay, redemption)
- discount tokens (check balance, discount policy, swap)
- dividends (tokens, vault, distribution policy, send)
- escrow (vault, send)
- membership (check balance, membership policy)
- vesting (check balance, check time, vesting policy)
- airdrop (airdrop policy, send)
- poison pill (check balance, poison policy, mint tokens)
- token curated registry (ledger, proposal policy, voting)
- proportional redemption policy
- simple membership policy (1 token 1 membership)
- tiered membership policy (multiple permissions for multiple balance levels)
- identity
- identity verification (kyc or sybil resistance)
- bonding curves (cfmm, mint/burn)

**Discount tokens:**

- A discount token gives the holder a discount on a product or service.
- The discount token yield (aggregate and user-level) grows proportionally to network usage (demand for products/services).
- The discount yield returns more benefits to users than passive token holders. Users will rationally acquire discount tokens to get a discount on services they use (think Amazon Prime). This would be more relevant if we develop services that resemble a SaaS model (community analytics, ongoing consultations/support, etc..)
- The denomination of fees may be in any form, such as a utility token or stablecoin. This makes pricing much easier.
- Learn more about discount tokens via this [overview](https://blog.coinfund.io/the-fundamentals-of-discount-tokens-cc400c66198e) and the [Sweetbridge discount token paper (PDF)](https://sweetbridge.com/assets/docs/WP-Sweetbridge-Discount-Tokens.pdf).

### Systems

> Lots of things that enable a goal

Systems are like patterns in they compose things into larger things. They're also similar in that at the design level they can be abstract and neutral, but in practice each instance is opinionated. As far as levels of abstraction go, primitives are maximally generic whereas systems are maximally opinionated.

Examples of systems:

- Gardens (conviction voting, issuance policy, agent, etc..)
- Moloch (voting, delegation, rage quit, minion, etc..)
- Uniswap (check balance, approve spend, swap)

<br />

## Mechanism Design 103

If you really want to get into mechanism design there are some papers we recommend reading.

### From Curved Bonding to Configuration Spaces

**Description:** Bonding curves are continuous liquidity mechanisms which are used in market design for cryptographically-supported token economies. Tokens are atomic units of state information which are cryptographically verifiable in peer-to-peer networks.Bonding curves are an example of an enforceable mechanism through which participating agents influence this state. By designing such mechanisms, an engineer may establish the topological structure of a token economy without presupposing the utilities or associated actions of the agents within that economy. This is accomplished by introducing configuration spaces, which are proper subsets of the global state space representing all achievable states under the designed mechanisms. Any global properties true for all points in the configuration space are true for all possible sequences of actions on the part of agents. This paper generalizes the notion of a bonding curve to formalize the relationship between cryptographically enforced mechanisms and their associated configuration spaces, using invariant properties of conservation functions. We then proceed to apply this frame-work to analyze the augmented bonding curve design, which is currently under development by a project in the non-profit funding sector.
**Paper:** https://epub.wu.ac.at/7385/1/zargham_shorish_paruch.pdf
**Code:** TBD.

### Economic Games as Estimators

**Description:** Discrete event games are discrete time dynamical systems whose state transitions are discrete events caused by actions taken by agents within the game. The agents’ objectives and associated decision rules need not be known to the game designer in order to impose structure on a game’s reachable states. Mechanism design for discrete event games is accomplished by declaring desirable invariant properties and restricting the state transition functions to conserve these properties at every point in time for all admissible actions and for all agents, using techniques familiar from state-feedback control theory. Building upon these connections to control theory, a framework is developed to equip these games with estimation properties of signals which are private to the agents playing the game. Token bonding curves are presented as discrete event games and numerical experiments are used to investigate their signal processing properties with a focus on input-output response dynamics.
**Paper:** https://epub.wu.ac.at/7433/
**Code:** https://github.com/cadCAD-org/demos/blob/master/demos/Multiscale/bonding_curve/Bonding_Curve.ipynb

### Translating Commons-Based Peer Production Values into Metrics: Towards Commons-Based Crypto-Currencies

Commons-based peer-production (CBPP) constitutes today an important driver for innovation, social and cultural development, both online and offline, through the establishment of an alternative, commons-based ecosystem, relying on peer-production and collaboration amongst peers contributing towards a common good. Yet, to the extent that it operates outside of the market economy, the value of CBPP cannot be understood by relying exclusively on traditional market mechanisms (such as pricing). Based on empirical research on emerging value forms in the context of CBPP, we seek to achieve a better understanding of the value produced by CBPP communities, so as to come up with an alternative, universal, denominator of value that could act as an interface between the commons-based ecosystem and the market economy.

**Paper:** https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2725415

<br />

## Diagramming

Diagramming can help you refine your understanding of the system and it's components. It's also useful when you want to communicate your vision to others. There are many types of diagrams and charts, but what's best for your use case and audience may vary.

[Causal loop diagrams](https://en.wikipedia.org/wiki/Causal_loop_diagram) can help you see the relationships between components of your system. These types of diagrams are generally very high level, but great for quickly illustrating things (like the network effects of your token system). As such they're great for blog posts and outward facing communications. There's even a [causal loop syntax developed by Systemic](https://systemic2016.wordpress.com/system-dynamics-causal-loop/).

[Stock and flow diagrams](https://systemic2016.wordpress.com/system-dynamics-stock-and-flow-modelling/) also show the relationship between things, but often in more detail than a causal loop.

[The cadCAD differential specification template](`https://community.cadcad.org/t/differential-specification-syntax-key/31`) is a good exercise to help you think through all the variables at play in your system and how they relate to each other. There's a [Figma template](https://www.figma.com/file/yBgOopbmcdkYxo2jDNmua1/cadCAD-Diff-Spec-Syntax?node-id=0%3A1) or you can create your own in your favorite diagramming software.

cadCAD diagrams can be generated for any cadCAD model. It's often as simple as adding a single line of code after you run the model. The [cadCAD Diagram repo](https://github.com/cadCAD-org/cadCAD_diagram) has more information on how to set that up.

Solidity contract diagrams can be generated via [Surya](https://github.com/ConsenSys/surya) and/or the [VSCode Soldity Visual Developer extension](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor). You can also manually create diagrams that show each function, it's inputs, and outputs. This can help you (and your community) understand the boundaries of your contract and the permissions and relationships between functions.

**Questions to ask:**

- What are the key components of your system that you want to understand and communicate?
- What are the relationships between those things and/or what things affect them?
- Is the organization of your diagram intuitive (color coding, labels, use of space, etc..)?

**Examples:**

> Actual diagrams of systems go here.

**Resources:**

- [Figma](https://www.figma.com/) - Proprietary (but atm free to use) design platform that has become the standard for designers. Great if you want to share designs/diagrams with a larger audience and/or make them look pretty.
- [Lucid chart](https://www.lucidchart.com/) - Diagramming software for engineers. Proprietary: free to try, but you'll have to pay if you want to use it on a real project.
- [Whimsical](https://whimsical.com/) - Super simple diagramming software. Also proprietary, free to try, and you'll have to pay for extra features if you want to use it on a real project.
- [cadCAD](https://github.com/cadCAD-org/cadCAD_diagram) - cadCAD (free and open source) has diagramming built in, but it's only for the cadCAD model. The [cadCAD Diagram repo](https://github.com/cadCAD-org/cadCAD_diagram) can help you generate cadCAD diagrams.
- [Surya](https://github.com/ConsenSys/surya) - Free and open source tool to visualize Solidity contracts.
- [Solidity Visual Developer](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor) - [Visual Studio Code](https://code.visualstudio.com/) extension that uses Surya and other things to visualize your Solidity code.

<br />

## Modeling

![Digital twin](https://camo.githubusercontent.com/0b80439a010c3a2d11217c381f39138a8bbd05dd48242200b2f4f684747ea051/68747470733a2f2f692e696d6775722e636f6d2f6b6234546e68362e6a7067)

A good model provides insights into how your token system would function under various conditions. This can help you check to see if your design goals are likely to hold as usage, price, and other important parameters change. Before you start modeling it's important to know what you want to have happen as well as what are the unknowns you're trying to understand. Ideally these unknowns can be stated as concrete questions. This way you have a clear goal, but also others who contribute to and/or review your model have something concrete to orient around.

Modeling Checklist:

- state variables
- system parameters
- helper functions
- policy functions
- state update functions
- state update configuration
- runtime configuration
- execution
- output formatting
- output visualization

**Questions to ask:**

- What are the design goals of your system?
- What are the unknown states or variables of your system?
- What questions are you trying to build intuition around via your model?

**Examples:**

- The [cadCAD GitHub org](https://github.com/cadCAD-org) has many [demos](https://github.com/cadCAD-org/demos).
- The [Gitcoin cadCAD model](https://github.com/gitcoinco/gitcoin_cadcad_model) is open source.
- Ocean Protocol created a python model called [TokenSpice](https://github.com/oceanprotocol/tokenspice2).
- 1Hive created a [cadCAD model for conviction voting](https://github.com/1Hive/conviction-voting-cadcad) which they use to inform their governance parameters as well as the token supply schedule.

**Resources:**

- [Python](https://www.python.org/) - You can create your modeling framework in python like Ocean Protocol did with [TokenSpice](https://github.com/oceanprotocol/tokenspice2).
- [cadCAD](https://cadcad.org/) is a python based library for modeling complex systems. There's free and open source [demos and tutorials](https://github.com/cadCAD-org/demos). There's also some [templates](https://github.com/cadCAD-org/snippets) to help you get started with your own models. If you have questions there's a [community forum](http://community.cadcad.org/) and [Discord](https://discord.gg/cewBa9zsxS).
- [Machinations](https://machinations.io/) - A platform and graphical interface for designing and simulating games.

<br />

## Whitepaper

Once you've identified a problem to solve, people who have that problem, and how you're going to solve it for them you should write it down! This will help you clarify your thinking. It will also help you communicate your vision to others. Then they might join you on your quest and/or point out ways that you might improve things.

To start, keep it simple. Just create a single page that describes what you're trying to do, why, and how. Eventually this might evolve into a formal specification, but right now we just want a rough sketch that's simple and intuitive. You can then update this as you design, develop, and deploy your token system. Then share it as a blog post or white paper. For now, keep it in a format (Google docs, HackMD, GitHub repo, etc..) that people can easily read, review, and comment on. This can help catch errors early on as well as engage your community.

The paper should describe the various components that are composed to achieve your goal, the properties of each mechanism, and the properties of your system as a whole.

It should also talk about why anyone could/should/would care about your token. You should explain why your token is useful (aka provide value) and how that will drive demand (resulting in a high token price). Supply and demand 101, with tokens. It ain't much, but it's honest work.

**Questions to ask:**

- Who is the audience?
- What are you trying to communicate to them?
- What is the action you'd like them to take as a result of reading your paper (provide feedback, contribute, etc..), and how can they do that (comments, GitHub Issues, community chat, etc..)?

**Examples:**

- For an excellent example of a specification, look at [Signal’s breakdown of their Double Ratchet Algorithm](https://signal.org/docs/specifications/doubleratchet/).
- The [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf) is a well known example of a paper that changed the world.

**Resources:**

- [HackMD](https://hackmd.io/) - A free and simple web based Markdown editor.
- [VSCodium](https://vscodium.com/) - The 100% open source no telemetry version of VSCode.

<br />
