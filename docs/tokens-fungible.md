## Fungible Tokens

> Tags: tokens, erc20, 0to1

### About

The most common form of fungible Ethereum tokens is the ERC-20 token standard. ERC-20 allows for the implementation of a standard API for tokens within smart contracts. This standard provides basic functionality to transfer tokens, as well as allow tokens to be approved so they can be spent by another on-chain third party. A standard interface allows any tokens on Ethereum to be re-used by other applications: from wallets to decentralized exchanges.

An ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

Often times people will use the ERC-20 template as a base, but then add additional features and functionality on top. This ensures that the token will have the standard ERC-20 interfaces required to work with wallets, protocols, and exchanges while also incorporating additional features needed for the tokens use case.

### Resources

- [Ethereum.org Developer Docs: ERC-20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) - A high level overview of fungible tokens and how ERC-20 works.
- [Ethereum EIP repo Issue 20](https://github.com/ethereum/EIPs/issues/20) - The original discussion and specification for ERC-20.
- [Ethereum Improvement Proposal 20](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md) - The final technical specification for ERC-20.

### Examples

- [OpenZeppelin Safe ERC-20](https://docs.openzeppelin.com/contracts/3.x/erc20-supply) - A guide on how to use the [OpenZeppelin ERC-20 implementation](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/SafeERC20.sol).
- [TORN token](https://github.com/tornadocash/torn-token/blob/master/contracts/TORN.sol) - The [TornadoCash](https://tornado.cash/) token uses the OpenZeppelin Safe ERC-20 as a base, then extends additional functionality on top.
