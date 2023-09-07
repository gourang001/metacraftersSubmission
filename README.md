# Metacrafters Getting  Started with Solidity Submission
# Hello World

This is the solidity program submission for the final module of Metacrafters Getting Started with  Solidity course. In this I've created a simple contract with 2 basic function : minting and burning and also balance mapping. 

## Description

This contract allows the user to maintain a track of total Supply as well a balance map that contains mapping of the value of each address/ account owner. The user can either mint tokens, increasing the total supply or burn the tokens that will derease the value from total supply but only if the user has enough tokens. This is checked using an if statement. 

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

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
    string public name = "GToken";
    string public abbreviation = "GT";
    uint public supply = 0;

    // mapping variable here

    mapping (address => uint) public balancemap;

    // mint function

    function mint(address add, uint val) public {
        balancemap[add] += val; 
        supply += val;
    } 

    // burn function

    function burn(address add, uint val) public {
        if(balancemap[add] >= val){
        balancemap[add] -= val;
        supply -= val;
        }
    }

}

```

You can compile this code using Remix Online IDE and compiling this smart contract and deploying it. 
## Authors

Gourang  


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
