# Solidity Project Assessment

This Solidity program is a simple program that illustrates the basics of the Solidity programming language. Solidity project for Metacrafters.

## Description

Simple contract developed in Solidity makes up this software. On the Ethereum blockchain, smart contracts are created using the programming language Solidity. The contract contains three public variables that store details about my coin: tokenName, tokenAbbrv, and totalSupply. The contract also contains a mapping of balances. The program also contains a mint and a burn function. Both functions take in two parameters: address and value. The mint function then increases the balance of the address by that amount and increases the total supply by that sum. In contrast, the burn function reduces the address's balance while taking both the value of the address's balance and the value to be subtracted into account. The function will subtract the value from the balance if the account balance is more than the amount to be subtracted. If not, it will ignore the function's code and do nothing.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the code from the mtToken.sol file from the repository or the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "TURTLE";
    string public tokenAbbrv = "TRTL";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
   function mint (address _address, uint _value) public {
      totalSupply += _value;
      balances[_address] += _value;
   } 

    // burn function
   function burn (address _address, uint _value) public {
      if (balances[_address ] >= _value) {
      totalSupply -= _value;
      balances[_address]-= _value;
      }
   } 

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile SolidityProject.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "SolidityProject" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the all the functions and interacting with the variables.

# Authors

Rodelit Bernil

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
