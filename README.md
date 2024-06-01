# ETH Proof (Beginner): Creating A Token

A simple Ethereum smart contract for managing a custom token, including minting and burning functionalities.

## Description

ETH Proof (Beginner): Creating A Token
 is an Ethereum-based smart contract that defines a custom token with basic functionalities such as minting and burning tokens. This project demonstrates fundamental concepts of token management on the Ethereum blockchain, including maintaining a total supply and balances for each address.

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., RVC.sol). Copy and paste the following code into the file:

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
   string public tokenName = "REVCOIN";
   string public tokenAbbrv = "RVC";
   uint public totalSupply = 0;

   // mapping variable here
   mapping(address => uint) public balances;
    
   // mint function
   function mint(address _addr, uint _val) public {
      totalSupply += _val;
      balances[_addr] += _val;
   }
    
    // burn function
   function burn(address _addr, uint _val) public {
      if (balances[_addr] >= _val){
         totalSupply -= _val;
         balances[_addr] -= _val;
      }
   }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile RVC.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken - contracts" from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the MyToken function. Click on the drop-down of the "MyToken" contract in the left-hand sidebar,

and then click on the "mint" function and copy the account address at the top right after the environment on the sidebar and add the value that you want to add to your token supply (e.g. 500),

then click the TotalSupply button to see if the value adds up and also click on "burn" function, same process copy the account address and input the value that you want to deduct to your TotalSupply (e.g. 100),

then click the TotalSupply to if the value that you'd input deduct on the  previous value that has been minted.

## Authors

Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
