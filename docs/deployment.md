# Deployment

## TL;DR:

- Open up a beta version for early community testing.
- Determine if you need a scaling solution, and if so, what's the best fit.
- Ship.
- Monitor your token system to ensure everything is working as intended.
- Engage in governance to update and modify the system over time.

---

## Beta Testing

Once you've designed your system and gotten a review you can start to test it out! Remember, with enough eyes all bugs are shallow. With an incentivized test the community and traders can interact with your token system and potentially profit from it. Here the risk and rewards are real, but contained. This caps your downside in the event of an unexpected outcome.

If things don't go as planned, find out why and fix it. If things go smoothly, learn from your data top see if there's anything you want to change before deploying in production.

When creating incentivized tests, there's a few ways to go about it:

- [Ethereum](https://ethereum.org/) is another great place to test out your token system. You can create a beta version of your contracts for the community to test before transitioning to the full version. This beta version might have limits on the amount of tokens that can be processed or it might have a limited conversion to new tokens once you're out of beta.
- You can also deploy contracts anonymously and then test them out to ensure they function as intended before redeploying an official version.
- [xDAI](https://www.xdaichain.com/) is an EVM based blockchain. Gas fees, transaction times, and security are lower on xDAI than Ethereum mainnet. This makes it great for non-financial use cases and incentivized testing. Deploying contracts to xDAI is often as simple as switching the chainID from mainnet to xDAI.
  - `https://xdaichain.com/`
  - `https://defipulse.com/xdai`
  - `https://bridge.xdaichain.com/`
  - `https://omni.xdaichain.com/`
  - `https://www.xdaichain.com/for-users/get-xdai-tokens`
- Beyond the Ethereum ecosystem, there are also other networks that have created incentivized testnets for developers such as Polkadot's [Kasuma](https://kusama.network/).

---

## Shipping

Once you've decided what your contracts look like, then you have to deploy them. There are many options. You can deploy on mainnet, a sidechain, or a layer 2 solution.

As of the summer of 2020 deploying contracts on mainnet is often $100 or more (USD) in gas fees. It can then be $10 or more to interact with the contract. This makes many use cases too expensive for mainnet. If your token project falls into that category you might want to explore one of the many scaling solutions available.

**Questions to ask:**

- Is the security of Ethereum mainnet (and it's associated cost) a feature or a bug for your use case? Would you benefit from a faster/cheaper settlement layer, and if so, is a sidechain, L2, or optimistic solution best for your use case?
- Who is the target user?
- What do you want them to do?
- Have you talked to them to ensure that they understand what to do?
- Are there guides and incentives to encourage them to do that thing?

**Examples:**

- [Aragon.1Hive.org](https://aragon.1hive.org/#/) - Aragon on xDAI thanks to 1Hive.
- [xDAI.DAOhaus.Club](https://xdai.daohaus.club/) - Easily spin up Moloch DAOs (V1 or V2) on xDAI via DAOhaus.
- [Aragon](https://medium.com/brightid/introducing-idchain-392c76c31d73) - Aragon on IDchain!
- [IDchain.DAOhaus.Club](https://idchain.daohaus.club/) - DAOhaus on IDchain!
- While [Snapshot](https://github.com/balancer-labs/snapshot) isn't necessarily a scaling solution, it does allow token holders to create a signalling vote off-chain for free. Then a community multi-sig can pay the gas to enact the wishes of the community. [Create your Snapshot page here](https://docs.snapshot.page/guides/create-a-space)!
- Token launch case studies go here.

**Resources:**

- ethereum.org: https://ethereum.org/en/developers/docs/layer-2-scaling/
- xDAI
- If you're using an L2 solution make sure that exits are permissionless and trustless so that if the operator becomes malicious you can always exit with your tokens.
- Deployment tips and tools (remix, buidler, etc..) go here.
- stuff about verifying the integrity of deployed contracts (local and Etherscan) and also releases: `https://wiki.debian.org/Creating%20signed%20GitHub%20releases`
- How to [create a bug bounty](https://consensys.github.io/smart-contract-best-practices/software_engineering/#bug-bounty-programs) goes here (even if it's only in your native token1)
- tips on documentation and user guides
- onboarding support
- community marketing/outreach

---

## Monitoring

> What gets measured gets managed!

Depending on the use case of your token the velocity/hodl ratio might be a feature or a bug. For example: if your token is supposed to be used to access services velocity is good and hodl is bad. If you token is supposed to be used for governance then hold would show long term engagement/interest whereas velocity might point to traders/investors acquiring tokens to support their short term interests.

The token analysis governance loop:

- Tokenisation: capitalising the network via token distribution.
- Automation: reducing the effort required by stakeholders to understand and participate in the network.
- Analysis: understanding the network and the impact of decisions in order to make better decisions moving forward.
- Governance: updating software and/or distributing common pools of tokenized assets to support the network.

**Questions to ask:**

- How can people quickly and easily find data on your app/protocol/project?
- How much is the token being used? (if your token is used to acquire goods or services)
- What is the token supply (esp important if dynamic)
- What is the liquid vs locked up supply (if you have vesting, staking, etc..)
- What is the current token price?
- What is the token velocity?
- What do the hodl waves look?
- If you have a DeFi protocol, what is the churn rate of capital (lending, borrowing, staking, etc..)? (note: this is usage of the product/service vs just token hodling)
- How much development activity is there on the codebase from developers? (git)
- How much social activity is there in the chats/forum from the community?
- How much governance activity is there from token holders? (if you have governance)
- How much search activity is there on the web from speculators? (may or may not be available/reliable)
- How are all these metrics correlated with each other? Is the price higher when there's more search activity and/or usage? Are any of these metrics a leading indicator for other metrics?
- What is the volatility of these metrics?
- What is the 30, 60, and 90 day averages of these metrics?

**Examples:**

- `https://www.hodlwave.com/` - hodl waves example
- `https://charts.woobull.com/bitcoin-hodl-waves/` - Bitcoin hodl waves
- `https://ethgasstation.info/` - usage of ETH to pay for gas
- `https://etherscan.io/charts` - lots of Ethereum stats

**Resources:**

- How to [quantify decentralization](https://news.earn.com/quantifying-decentralization-e39db233c28e).
- 16 ways to [measure network effects](https://a16z.com/2018/12/13/16-metrics-network-effects/)
- [Apiary Explorer](https://apiary.1hive.org/orgs)
- [DAO Dashboard](https://mydaodashboard.com/)
- [DAO Metrics](https://daometrics.com/)
- [Deep DAO - Insights for a Decentralized World](http://deepdao.world/#/app/dashboard)
- [How to monitor your Aragon Organization using Tenderly](https://blog.tenderly.dev/how-to-monitor-your-aragon-organization-using-tenderly/)

---

## Governance

> Management is work.

It's very very important, esp in the early days, that you curate a strong group of value aligned members. They set the foundation for the rest of the project's evolution.

- have a clear direction with strong goals (meme)
- curate members (onboarding)
- ensure that everyone know what the token system is about and how to participate

As a project decentralizes management functions do not go away. They get shifted to the community. Management is work. This work needs to be accounted for and rewarded, otherwise the only people who do the work are those with incentives to gain control, often due to corporate or egotistical motivations rather than to serve the community. This will create a [tyranny of structurelessness](https://www.jofreeman.com/joreen/tyranny.htm). It doesn't have to be this way.

Often gov is less about finding a right answer, but aggregating preferences into an action. Good governance systems allow for diverse inputs to inform an outcome (wisdom of the crowds).

**Progressive Decentralization:**

Decentralized => community owned and controlled.

Progressive decentralization is when you start centralized, then iteratively give control to the community. Often times this involves distributing a token to users of a protocol to allow them to govern that protocol.

[How and Why to Decentralize Your Project: A Deep Dive](https://www.youtube.com/watch?v=rW8GrxQYPbI) is a great resource to start to explore these ideas if you don't want to be decentralized from day 1.

TL;DR:

- Build something people want.
- Build a community.
- Give ownership of the thing to the community.

Great product needs opinionated leadership. Don't design by committee! Build it, *then* give governance to the community.

Don't launch a token too early. Thinking about SEC compliance is a huge distraction from product-market fit.

Faking decentralization is a great way to undermine trust and bork community development. Be transparent about power and trust lie. Create a roadmap for decentralization. Then stick to it.

Great docs
Developer evangelism
Limit core team control over contracts

Ensure the community has very clear and real incentives to contribute and care.

PMF, then tokens to contributors, then to broader community.

Communicating about incentives and power is important and a great way to engage people.

Enable your users to succeed and celebrate their success.

Be focused on something simple. Keep it simple. Improve it over time.

Successful products are not designed by committees. PMF, then decentralization - not the other way around.

Tokens are great for aligning incentives and governance. They don't have to be fundraising mechanisms.

Focusing on security and de-risking contracts for users is a great way to get (long term) adoption and usage, esp if you want people to build on your protocol.

Note: if the core team retains too many tokens, and is formed as a company, it's likely that they'll (consciously or subconsciously) want to retain control and may take actions that prevent other parties from meaningfully participating.

Notes:

- This section will talk about why you might need governance (managing shared resources) and the tools you might use to do so (Snapshot, dApps, etc..).
- We'll also talk about the difference between global governance and local governance, and when you might want to use one vs the other. For example, allowing decisions about how to organize Discord be managed via Discord polls but decisions on the inflation rate of your token to be managed by token holders directly.
- Governance is the process of applying any design feature or control mechanism that maintains and steers a system.
- Talk about how analysis informs governance and governance informs what we analyze.
- Create a place for the community to discuss things and mechanisms for them to express their sentiments to affect change.
- Also talk about how hard it is to balance divergent ideas/projects from the community while also having a clear focus and mission.
- General community best practices
- Discord server organization
- Token permissioned chats
- Giving people a reason to stay engaged
- Recognize and reward community contributors
- Governance and governance minimization

**Questions to ask:**

- What kinds of decisions will need to be made to keep your token system functional?
- Do these decisions affect all token holders, or only a subset of the system?
- Who (if anyone) is responsible for making (or leading) those decisions?
- How are those contributors recognized and rewarded?
- What percentage of tokens should be allocated to the initial team and cap table?
- How will you reward different types of contributors to the product or service, historically and in the future?
- How will technology leadership be rewarded going forward?

**Examples:**

- Example: Curve and TornadoCash creating valuable apps, then open sourcing all the contracts and deployment scripts for their tokens, then letting the community launch it.
- Compound
- Uniswap

**Resources:**

- [How and Why to Decentralize Your Project: A Deep Dive](https://www.youtube.com/watch?v=rW8GrxQYPbI) is a great resource to start to explore these ideas if you don't want to be decentralized from day 1.
- https://news.earn.com/quantifying-decentralization-e39db233c28e
- https://a16z.com/2020/01/09/progressive-decentralization-crypto-product-management/

---

## Communities

Giving people invites to apps can create social sharing and scarcity. This can constrain supply while also driving demand (and reducing server costs if you have a Web2 server). Curates an early community and creates some exclusivity.

Free for open source. Pay for private/proprietary. Great for marketing and developer engagement. Corps always have cash to pay for features.

User/people first models create stickiness.

Stay focused on solving a concrete problem. Make it as easy as possible to do the thing you're enabling. Ex: GitHub => get code online as fast as possible (“We were trying to reduce the barrier to entry as much as possible. Just strip every possible thing away that we could think of to make it easy for you to get code online. And the social elements came from that.“).

- Dogfood the product and use it as much as possible. All day. Every day. If you're not your product's biggest user then you're not the right person to build it.
- Then things like having the README presented right away to make it easier to go to code online and understand what's going on.
- Have a 10X better product and focus on supporting your users, esp super fans. Make engagement a priority. Find the people who care a lot about a topic.

Having a non-exploitive business model is essential for sustainability. Also helps with adoption so that people know where your incentives are. Private/proprietary data and/or support is a common way to do this.

Note: fully distributed requires advanced level management skills. Requires next level communication *and* autonomy - but usually those who communicate need feedback and those who are autonomous don't communicate.

Branding isn't about you. It's about what you're providing for your customer. It's not about being cool to be cool, it's about helping your customers kick ass. When your customers succeed you succeed, and in a way that feels genuine and builds true fans/community.

If you have no values no one will care about your brand. You have to believe in and communicate something that people care about. Then people will amplify that message to create a community of people with shared values.

Often value is an opinion of what is valuable - but that's based on supply and demand. Ideally your token system allows for localized contextual value vs a global sense of value (same w governance - push it to the edges). Different people like different things. Create systems that give everyone room to innovate and explore.

You don't get to pick your communities. They reflect the values of the project.

Every community is it's own kitchen. Often similar ingredients, but you need someone there tasting things as you go not just blindly following a recipe.

Build something people want and want to be part of.

The culture and values should be reflected in the community as well as the mechanism design.

**Examples:**

- GitHub wanted to make it as fast as possible for people to get code online. They stripped away everything in the way of that. This created immediate value for every new user. Everything else grew from that.

**Questions to ask:**

- What is the value you are creating for people? Another way to frame that is what is the core problem you're solving?
- Is everything focused on solving that problem and creating value for users? If not, what could change or be removed to enhance that.
- What are your values? Why should people care? Beyond solving a concrete problem, does your project align with people's world view? Are you enabling people to create the changes they want to see in the world?

**Resources:**

- [a16z's crypto startup school](https://a16z.com/2020/12/28/crypto-users-guide/) has a great talk with [Chris Dixon](https://cdixon.org/) (a16z crypto) and [Tom Preston-Werner](https://tom.preston-werner.com/) (GitHub) about [Building Companies and Developer Communities](https://www.youtube.com/watch?v=gK-7GUS8G-Q).

---

## Upgrades

It's likely that you'll want to upgrade and add on to your token system. This might involve sketching out a design, developing it, and deploying it. This is similar to the process described in this workbook for a full token system, but likely less intensive as it's a smaller update and you've (hopefully) gone through the process before.

Depending on your token system and the update it might involve a token holder vote or it might be permissionless. Often changes to the core structure are permissioned as they affect all token holders. Ancillary components that are optional can often be permissionless as they only affect those who choose to interact with them. This is often better as it encourages innovation, decentralizes development, and pushes governance of mechanisms to the edges.

The simpler your core token system is, the easier it will be to incorporate new things in an opt-in permissionless way. The easiest way to do this is to start with a simple token contract, then add on more things that use that token.

**Examples:**

- [1UP](https://1up.world/) - 1UP allows you to `/1UP` your friends to award them community tokens. Atm it only awards tokens in a single DAOstack DAO, but in the future it might get expanded to work with more token systems.
- [CommonsStack PraiseBot](https://wiki.commonsstack.org/contributors-guide#what-is-commons-stack-praise) - The CommonsStack praise bot is similar to 1UP in that people give each other praise to receive tokens, however unlike 1UP there's no backend. A group of community members then gives people tokens (or just points) based on praise nominations.
- [1Hive nominations](TBD) - Not sure if they still do this, but if there's a link to the old protocol that would be awesome.
- [DAOnuts tipping app](https://github.com/daonuts/tipping-app) - An Aragon app that allows you to tip others with DAO tokens.
- [yGifts](https://ygift.to/)
- [Gittron](https://gittron.me/)
- Bounties
- [BountiesNetwork](https://bounties.network/) - Free and open source, but not very maintained.
- [Gitcoin](https://gitcoin.co/bounties/funder) - Proprietary platform that helps create grants and bounties for open source projects. There are fees, but it's updated regularly with new features and has lots of users (hackers and funders).
- [Transmutation](https://github.com/HausDAO/wc/blob/develop/contracts/Transmutation.sol)
- Token curated lists
- Staking on things to boost them and earn future profits from them: `https://discourse.sourcecred.io/t/boosting-a-prediction-market-on-ideas/306`
- Signalling/polling mechanisms (soft governance)
- Voting mechanisms (hard governance)
- Token bounties/rewards/challenges mechanisms (both for fans and creators)
- Prediction markets (on challenges fans can create for creators)
- Secondary bonding curves (aka derivative tokens)

**Questions to ask:**

- What problem will this mechanism solve?
- How will a new mechanism contribute to the core value prop of the community/project?
- Will governance of this mechanism be local (contained with the mechanism itself or those who use it) or global (determined by all token holders or stakeholders in a system)?

**Resources:**
