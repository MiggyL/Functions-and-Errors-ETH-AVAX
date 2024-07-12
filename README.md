# Functions-and-Errors-ETH-AVAX

## Description

This Solidity program includes a contract that implements the require(), assert() and revert() statements.

## Getting Started

### Executing program

- To get started with the `Functions&Errors` contract, you'll need to use the [Remix's Solidity IDE](https://remix.ethereum.org/).
- Create a workspace, choose a template, and come up with a name for the workspace.
- Once your workspace have been created, create a new file named `Functions&Errors` and it must be saved as a .sol file extension (Functions&Errors.sol).
- Copy and paste the `Functions&Errors` contract code into the `Functions&Errors.sol` file.
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract ErrorHandling {

    uint public value1 = 10;
    uint public value2 = 20;

    // Function demonstrating require() for input validation
    function setValue1(uint newValue) public {
        require(newValue > 0, "New value must be greater than zero");
        value1 = newValue;
    }

    // Function demonstrating assert() for internal invariants
    function addValues() public view returns (uint) {
        assert(value1 + value2 == 30); // Should always be true
        uint sum = value1 + value2;
        return sum;
    }

    // Function demonstrating revert() for unexpected conditions
    function divideByZero() public view {
        require(value2 > 0, "Cannot divide by zero"); // Use require for expected errors

        // uint result = value1 / value2;  // This line would cause division by zero error in older Solidity versions
        revert("Unexpected division by zero"); // Explicitly revert to prevent undefined behavior
    }
}
```
- Compile the contract by selecting the Solidity compiler and clicking the "Compile" button. (Make sure to choose the right compiler in order to do so.)

### Deploying the Contract

1. In Remix, go to the "Deploy & Run Transactions" tab.
2. Select the `Functions&Errors` contract from the dropdown menu.
3. Choose the appropriate environment (e.g., JavaScript VM, Injected Web3 for MetaMask, etc.).
4. Click the "Deploy" button to deploy the contract.

### Interacting with the Contract

1. Once deployed, you can interact with the contract using the Remix interface.
2. Use the input fields and buttons provided by Remix to call several functions.
3. Example:
   - To set a value, enter a value, then click the `setValue1` button. This will change the value of value1 to your inputted value.
   - To add values, click the `addValues` button. This will add value1 and value2 together only if it equals to 30.
   - To divide by 0, click the `divideByZero` button. This will divide the value by 0, but it will revert with a message displaying a division error.
   - To view the values, click the `value1` button or the `value2` button.

## Authors

Miguel Lacanienta
[@MiguelLacanienta](https://www.facebook.com/miguel.lacanienta.16/)
