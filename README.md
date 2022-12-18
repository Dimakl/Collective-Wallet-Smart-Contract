# Collective Wallet Smart Contract
This is a smart contract that can be used as a multi-user wallet with approvals required for transactions. The contract allows for the creation of a list of approvers and specifies the number of approvals required for a transaction. The contract also keeps track of the transactions that have been submitted and the number of approvals they have received. When a transaction has received the required number of approvals, it is executed and the appropriate amount of tokens is transferred to the recipient.


Collective wallet smart contract example is deployed at address in Etherium Goerli network [ 0x55F776969622b8c455EAE2996216bb6b9002e0A1](https://goerli.etherscan.io/address/0x55f776969622b8c455eae2996216bb6b9002e0a1)

## Example
Suppose we have deployed the Collective Wallet contract to the Ethereum blockchain and specified that 3 approvals are required for a transaction. We have also added 3 users as approvers: `Alice`, `Bob`, and `Charlie`.

 - `Alice` wants to transfer 100 tokens to `Bob`. She calls the `submitTransaction` function with the transaction ID `"tx1"`, the recipient address `Bob`, and the amount of tokens to be transferred 100. The number of approvals for `"tx1"` is now 1.
 - `Bob` wants to approve `"tx1"`. He calls the `approveTransaction` function with the transaction ID `"tx1"`. The number of approvals for `"tx1"` is now 2.
 - `Charlie` also wants to approve `"tx1"`. He calls the `approveTransactionfunction` with the transaction ID `"tx1"`. The number of approvals for `"tx1"` is now 3.

Since the required number of approvals has been reached, the transaction is executed and the appropriate amount of tokens is transferred to `Bob`. The transaction is added to the list of approved transactions and the `TransactionApproved` event is emitted.



## Features
 - The contract owner can add approvers to the wallet by calling the `addApprover` function.
 - Users can submit transactions for approval by calling the `submitTransaction` function and specifying the transaction ID, recipient address, and the amount of tokens to be transferred.
 - Users can approve transactions by calling the `approveTransaction` function and specifying the transaction ID.
 - When a transaction has received the required number of approvals, it is executed and the appropriate amount of tokens is transferred to the recipient. The transaction is then added to the list of approved transactions and the `TransactionApproved` event is emitted.
 - The contract keeps track of the transactions that have been submitted, the number of approvals they have received, and which users have approved them.

## Usage
To use this contract, follow these steps:

1. Deploy the contract to the Ethereum blockchain and specify the address of the ERC20 token contract and the number of approvals required for a transaction.
2. Add approvers to the wallet by calling the `addApprover` function.
3. Submit a transaction for approval by calling the `submitTransaction` function and specifying the recipient address and the amount of tokens to be transferred.
4. Approve the transaction by calling the `approveTransaction` function and specifying the transaction ID.
5. When the required number of approvals has been reached, the transaction will be executed and the appropriate amount of tokens will be transferred to the recipient.

## Requirements
 - An Ethereum blockchain and an ERC20 token contract.
 - Solidity compiler version ^0.8.0.

## Note
 - The `is_in` and `is_not_in` functions are helper functions that check if a given value is or is not in an array, respectively.
 - The `calldata` keyword is used to specify that the transaction ID is passed as a variable length byte array. This allows for the use of any type of data as the transaction ID, not just strings.
 - The `require` statements in the contract serve as checks to ensure that certain conditions are met before executing the rest of the function. If the condition is not met, the transaction will fail and no changes will be made to the blockchain.

## License
This contract is licensed under the MIT license. See the `LICENSE` file for details.
