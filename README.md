# SwapFeeReward Contract

The `SwapFeeReward` contract is a Solidity smart contract designed to facilitate swapping tokens and rewarding users based on the swap fees incurred. It is integrated with a liquidity provision mechanism and a whitelist feature to allow for efficient and controlled token swaps while incentivizing liquidity providers.

## Contract Overview

The contract consists of the following main components:

1. **Whitelist Management**: The contract maintains a whitelist of tokens that are eligible for swapping and reward distribution. The whitelist can be managed by the contract owner.

2. **Token Swapping and Rewarding**: Users can swap tokens through the contract, and based on the swap fees incurred, they receive rewards in a designated token. Rewards are calculated based on the swap fees, user's swap amount, and predefined reward percentages.

3. **Pair Management**: The contract allows the owner to manage pairs of tokens eligible for swapping and reward distribution. Each pair is associated with a specific reward percentage.

4. **Oracle Integration**: The contract integrates with an Oracle contract to fetch exchange rates and calculate reward quantities for different token pairs.

5. **Ownership and Permission Control**: The contract owner has exclusive control over critical functions such as setting the whitelist, managing pairs, and adjusting reward percentages.

## Contract Functions

### Whitelist Management

- `addWhitelist`: Adds a token to the whitelist.
- `delWhitelist`: Removes a token from the whitelist.
- `isWhitelist`: Checks if a token is whitelisted.
- `getWhitelist`: Retrieves the tokens in the whitelist.
- `getWhitelistLength`: Retrieves the length of the whitelist.

### Token Swapping and Rewarding

- `swap`: Initiates a token swap and distributes rewards to the user based on the swap fees and reward percentages.
- `rewardBalance`: Retrieves the reward balance of a user.

### Pair Management

- `addPair`: Adds a new token pair with a specified reward percentage.
- `setPair`: Updates the reward percentage for an existing token pair.
- `setPairEnabled`: Enables or disables reward distribution for a specific token pair.

### Ownership and Configuration

- `setRouter`: Updates the router address.
- `setOracle`: Updates the Oracle contract address.
- `setFactory`: Updates the factory contract address.
- `setInitCodeHash`: Updates the initialization code hash for pair creation.
- `setPhase`: Updates the current phase of reward distribution.
- `withdraw`: Allows users to withdraw their accumulated rewards.

## Contract Deployment

The contract should be deployed with the following parameters:

- `_factory`: Address of the token factory contract.
- `_router`: Address of the router contract.
- `_INIT_CODE_HASH`: Initialization code hash for pair creation.
- `_bswToken`: Address of the BSW token contract.
- `_Oracle`: Address of the Oracle contract.
- `_targetToken`: Address of the target token for reward distribution.

## Security Considerations

- Ensure that only trusted addresses have permission to modify critical contract parameters.
- Validate inputs and ensure proper error handling to prevent unexpected behavior.
- Regularly review and audit the contract code to identify and address any potential security vulnerabilities.

## Disclaimer

This README serves as a high-level overview of the `SwapFeeReward` contract functionality and deployment considerations. It is essential to thoroughly understand the contract logic and conduct comprehensive testing before deploying it in a production environment. Additionally, consider consulting with security experts and legal professionals to ensure compliance with regulations and best practices.
