### What is Solidity?

* Solidity is an object-oriented, high-level language for implementing smart contracts. It is designed to taget EVM.
* It is statically typed, supports inheritance, libraries and complex user-defined types among other features.



### Building in SOlidity

#### initializing smart contracts

```solidity
pragma solidity ^0.8.19;  // must specify a version
// SPDX-License-Identifier: MIT  if don't specify License, compiler will warn(not a error)

contract HeeloWorld {}
```



#### Variables and types

1. Local

   * Definition: Temporary variables declared inside a function, not stored on the blockchain.
   * Scope: Exists only within the function
   * Gas Cost: Does not cost gas unless used in transactions.

2. State

   * Definition: Variables that store data permanently on the blockchain. (stored in storage.)
   * Scope: Accessible within the entire contract.
   * Gas Cost: Writing to state variables is expensive as it modifies blockchain state.

3. Global

   * Definition: Built-in variables that provide information about the blockchain, transactions, and contracts.
   * Scope: Available globally in any function.

   - Common Global Variables

     | **Variable**      | **Description**                            |
     | ----------------- | ------------------------------------------ |
     | `msg.sender`      | Address of the caller (transaction sender) |
     | `msg.value`       | Amount of ETH sent in a transaction        |
     | `block.timestamp` | Current block timestamp                    |
     | `block.number`    | Current block number                       |
     | `tx.gasprice`     | Gas price of the transaction               |



#### Value Type

   	1. Integer Type (uint, int)
       * Unsigned Integers: Non-negative numbers
       * Signed Integers: Can be negative
       * Size Variants: uint8, uint16, unit256(defalut)
  	2. Boolean (bool)
  	3. Address
  	4. Fixed-Size Bytes (bytes1 to bytes32)



#### Reference Type

 1. Strings and bytes: string stores text, bytes similar to string but more gas-efficient

 2. Arrays(uint[], string[]):

 3. Mappings: key-value store, like a dictionary

 4. Structs: Custom data types

    

#### Special Type

       1. enum: Used to define a list of options
       2. function: Can store function references.





### Visibility specifiers

#### public

Accessible from:

* Inside the contract
* Other contracts
* External transactions



#### private

Accessible from:

* Only within the same contract



#### internal

Accessible from

* The same contract
* Derived (child) contracts



#### external

Accessible from

* Only externally (cannot be called from within the same contract)
* Not accessible internally