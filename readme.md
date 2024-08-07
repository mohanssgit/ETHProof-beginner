# Creating a Token in Solidity
## Description
This Solidity code is the solution to the assessment of the "ETH PROOF: Beginner EVM Course" by Metacrafters. The requirements of the assessment are:

1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).
2. Your contract will have a mapping of addresses to balances (address => uint).
You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
3. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint function. It will then deduct the value from the total supply and from the balance of the address.
4. Lastly, your burn function should have conditionals to make sure the balance of the account is greater than or equal to the amount that is supposed to be burned.

## Getting Started
### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ETHProof.sol). Copy and paste the following code into the file:

```solidity
pragma solidity ^0.8.18;

contract ETHProof {
    string public tokenName = "YourTokenName";
    string public tokenAbbrv = "YTN";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile ETHProof.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "ETHProof" contract from the dropdown menu, and then click on the "Deploy" button.

### Authors
Mohan Singh
@mohanssgit

### License
This project is licensed under the MIT License - see the LICENSE.md file for details.
