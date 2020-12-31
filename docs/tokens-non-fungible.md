## Non-fungible Tokens

### About

> Adapted from the [ethereum.org ERC-721 page](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/)

#### What is a Non-Fungible Token?

A Non-Fungible Tokens (NFT) is used to identify something or someone in a unique way. This type of Token is perfect to be used on platforms that offer collectible items, access keys, lottery tickets, numbered seats for concerts and sports matches, etc. This special type of Token has amazing possibilities so it deserves a proper Standard, the ERC-721 came to solve that!

#### What is ERC-721?

The ERC-721 introduces a standard for NFT, in other words, this type of Token is unique and can have different value than another Token from the same Smart Contract, maybe due to its age, rarity or even something else.

All NFTs have a uint256 variable called tokenId, so for any ERC-721 Contract, the pair contract address, uint256 tokenId must be globally unique. Said that a dApp can have a "converter" that uses the tokenId as input and outputs an image of something cool like zombies, weapons, skills, or amazing characters.

### Resources

- [Ethereum.org Developer Docs: ERC-721](https://ethereum.org/en/developers/docs/standards/tokens/erc-721/) - A high level overview of non-fungible tokens and how ERC-721 works. Also links to other non-fungible token standards at the bottom of the page.
- [Ethereum EIP repo Issue 721: non fungible token standard](https://github.com/ethereum/EIPs/issues/721) - The original discussion and specification for ERC-721.
- [Ethereum Improvement Proposal 721](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md) - The final specification for ERC-721.

### Examples

- [ERC-721 Impleimentations](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md#references) - See the "NFT Implementations and Other Projects" section.
