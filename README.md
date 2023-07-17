# SolidityAssessment

This is how you create your OWN Token in Solidity. The purpose of this program is to help other beginner programmers that are currently learning and expanding its idea about Solidity.

# Description

This is a simple program coded in Solidity. This serves as a guide for beginner programmers and gives them an idea of how Solidity works.

# How to run the Program?

To run this program, you need to access Remix, Remix is an online Solidity Compiler, that won't consume your device's storage.
Here is the link for Remix - https://remix.ethereum.org/

After clicking the link, you need to create a New File, just click "Create New File" name it on your preferences and save it with a .sol extension. Last, copy and paste the code provided down below:

Source code:

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
    string public tokenName = "Tokenens";
    string public tokenAbbrv = "TKNS";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
}
    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

}


# Compiling and Deploying

To COMPILE it, you need to click the "Solidity Compiler" button located on the left sidebar. Make sure to compile it the same as the version used in the code provided to avoid errors. Then, click "Compile Token.sol".

To DEPLOY it, just simply click the "Solidity Deploy & Run Transactions" button located on the left sidebar. Once you've successfully deployed it, you can now interact with it by calling its functions i.e. (totalSupply, tokenName, tokenAbbv, balances, mint, burn).

# Authors

Daniel II Burgos
[8210825@ntc.edu.ph]

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
