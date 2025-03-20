# Solidity Smart Contract - Binary Voting

## Overview
This is a Solidity-based binary voting smart contract that allows registered voters to cast votes on proposals for either 'Yes' or 'No'. The contract ensures controlled access through modifiers and allows only permitted users to participate in the voting process. The owner has control over voter registration, proposal creation, and voting permissions.

!!Warning!! : as this was a learning project gas is not optimised , use a testnet if you want to try this contract.
## Prerequisites
To run and test this smart contract, you will need:
- A web browser
- Internet access
- [Remix IDE](https://remix.ethereum.org/)
- A MetaMask wallet (optional for deploying on a testnet)

## Running the Smart Contract on Remix
Follow these steps to run the contract in the Remix IDE:

### 1. Open Remix IDE
Go to [Remix IDE](https://remix.ethereum.org/) in your browser.

### 2. Create a New Solidity File
1. In the Remix file explorer, click the `+` button to create a new file.
2. Name the file `BinaryVoting.sol`.
3. Copy and paste the Solidity smart contract code into the file.

### 3. Compile the Smart Contract
1. Go to the **Solidity Compiler** tab in Remix.
2. Select the correct Solidity version (0.8.18) to match the pragma version in the contract.
3. Click the **Compile BinaryVoting.sol** button.

### 4. Deploy the Smart Contract
1. Navigate to the **Deploy & Run Transactions** tab.
2. Select the **Environment**:
   - Choose **Remix VM (London)** for a local blockchain simulation.
   - Alternatively, select **Injected Web3** if using MetaMask with a test network.
3. Click **Deploy** to deploy the contract.

### 5. Interacting with the Contract
Once deployed, the contract will appear under **Deployed Contracts**. You can interact with it using the provided UI:

#### Owner Functions:
- **registerVoter(address _newVoter)**: Registers a new voter.
- **addProposal(string memory _name , uint _durationInDays)**: Adds a new proposal for voting.
- **endVoting()**: Ends the voting process and determines whether the proposal passed.
- **allow(address _allowed)**: Grants voting permission to a registered voter.
- **revoke(address _revoked)**: Revokes voting permission from a registered voter.
- **allowAll()**: Grants voting permission to all registered voters.
- **revokeAll()**: Revokes voting permission from all registered voters.
- **listRegisteredVoters()**: Returns the list of registered voters.

#### Voter Functions:
- **vote(bool _vote)**: Casts a vote (true for 'Yes', false for 'No').
- **getResult()**: Retrieves the result of the last proposal after voting ends.

## Notes
- Only registered voters with explicit permissions can vote.
- The contract automatically revokes all voting permissions after a proposal ends.
- The contract is deployed only in memory when using the Remix VM. If you refresh the page, you will need to redeploy it.
- If deploying on a testnet, ensure you have test Ether in your MetaMask wallet.

## License
This project is open-source under the MIT License.

