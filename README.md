

# Course Completion Badges - Smart Contract

## Vision

The Course Completion Badges project is designed to modernize the way educational achievements are recognized by issuing verifiable and immutable digital badges on the blockchain. This smart contract allows educational institutions to award students with course completion badges that are securely stored on the blockchain, providing a transparent and tamper-proof method of acknowledging academic success.

## Features

- **Decentralized Badge Management**: Course completion badges are securely stored on the blockchain, ensuring that they cannot be altered or deleted.
- **Owner-Only Badge Issuance**: Only the contract owner has the authority to award badges, ensuring control and authenticity.
- **Student Badge Records**: Each student's badges are stored in a decentralized ledger, making it easy to retrieve and verify their achievements.
- **Event Emission**: Whenever a badge is awarded, an event is emitted, allowing external applications to track badge issuance.

## Diagram

```plaintext
+-------------------------+
|      Admin (Owner)       |
+------------+-------------+
             |
             v
  +----------+------------+
  |        awardBadge()       |
  +----------+------------+
             |
             v
  +----------+------------+      +-------------------+
  |   Badge Struct Creation  |----| Event: BadgeAwarded |
  +----------+------------+      +-------------------+
             |
             v
  +----------+------------+
  |   Store Badge in Mapping   |
  +----------+------------+
             |
             v
  +-------------------------+
  |  Retrieve Badges via View |
  |      Functions (for users)|
  +-------------------------+
```

## Deployment Details

### Prerequisites

1. **Solidity Compiler**: Ensure you have a Solidity compiler (version ^0.8.0) installed.
2. **Ethereum Test Network**: Prepare a deployment environment on an Ethereum test network like Ropsten, Rinkeby, or Goerli.
3. **Ethereum Wallet**: Use an Ethereum wallet (e.g., MetaMask) to manage contract deployment and interactions.

### Deployment Steps

1. **Compile the Contract**: Use a Solidity compiler (e.g., Remix, Truffle) to compile the `CourseCompletionBadges.sol` file.

2. **Deploy the Contract**:
   - Deploy the contract to an Ethereum test network using your wallet.
   - After deployment, note the contract address for future interactions.

3. **Interact with the Contract**:
   - As the contract owner, you can award badges to students by calling the `awardBadge()` function.
   - Students and other users can view their badges using the `getStudentBadges()` and `getBadgeDetails()` functions.

4. **Contract Address**:
   - **Contract Address:** `0x64d6049e9e2934b00bcbf096e6fbeef62479bb65`

   Replace `0x64d6049e9e2934b00bcbf096e6fbeef62479bb65` with the actual contract address once deployed.

## Future Enhancements

- **Custom Badge Designs**: Introduce support for custom badge designs and metadata to enhance the personalization of badges.
- **Badge Revocation**: Implement a feature that allows the contract owner to revoke badges if necessary.
- **Cross-Institution Recognition**: Develop standards for recognizing badges across multiple educational institutions.
- **Mobile Integration**: Create a mobile app for managing and displaying badges on-the-go.

## Contact

- **Developer**: Ayan Hussain
- **Email**: empknox@gmail.com

## Deployment Address:
https://opencampus-codex.blockscout.com/tx/0xa5d3f1fde5bbcb786598719a0dadceeea0aed3cc5c88f6ff5d2273213869055e
![image](https://github.com/user-attachments/assets/cdf65d98-6894-4805-ad94-6d661ab89b61)
