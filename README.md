# Ethereum+AVAX Intermediate Course Project: FUNCTIONS AND ERRORS

This is the basic demonstration of Error Handling using the Solidity programming language. It serves the purpose of explaining the need of error handling using revert, require and assert statements.

## Description

This program is a simple contract written in Solidity that explains how to handle unwanted errors or to ensure uninterrupted execution of the program using the revert, require and assert statements.

Require() - takes in two parameters, first one is condition check and another is the message that is to be executed if the condition fails to be true.

Revert() - takes only one parameter that is the message that gets executed whenever the revert statement is called or the condition check is true for the same if block in which revert stmt. is lying. Also, saves unconsumed gas by reverting the state of contract to its initial state.

Assert() - takes only one parameter that is condition check which needs to be true for further execution of the program.

## Implementation

"doRequire" func. checks for the input to be less than or equal to 10 using require() stmt. If true, returns the sq. of that number else returns the message i.e. passed as second parameter.

"doRevert" func. using revert() stmt returns the message i.e. passed as parameter whenever the if stmt gets true i.e. (num1<num2).

"doAssert" func. checks for the denominator(num2) input to be non-zero using assert() stmt. and therefore allowing for further execution of program/func. iff the condition is true.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., errorHandling.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

contract errHandle {
    function doRequire(uint num) external pure returns(uint) {
        require(num<=10, "Num should be less than or equal to 10.");
        return num*num;
    }

    function doRevert(uint num1, uint num2) external pure returns(uint) {
        if(num1<num2) {
            revert("num1 should be greater than num2.");
        }
        return num1-num2;
    }

    function doAssert(uint num1, uint num2) external pure returns(uint) {
        assert(num2 != 0);
        return num1/num2;
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "Compile errorHandling.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "errHandle" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the doAssert, doRequire and doRevert functions. Click on the "errHandle" contract in the left-hand sidebar, and then click on the "doAssert/doRevert/doRequire" function. Finally, click on the "transact" button to execute the function and retrieve the uniterrupted outputs by all the functions.
## Authors
Devkinandan Garg
