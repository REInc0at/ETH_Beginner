# ETH Beginner Assessment (Solidity)

This Solidity program demonstrates how to create, mint, and burn tokens. The purpose of this program is to act as a final challenge for the students learning Solidity thru Metacrafters. It serves as a proof for the student's learning progress in their journey with Solidity.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a two functions: mint and burn. 

The following are the requirements for this project that is shown in this program:
* Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
* Your contract will have a mapping of addresses to balances (address => uint)
* You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
* Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
* Lastly, your burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned

## Getting Started

### Installing

To run this program, you can use Remix, an online Solidity IDE. https://remix.ethereum.org/

### Executing program

* Once on the Remix website, create a new file and name it 'Create_My_Token.sol' or anything you want. Then paste the code below:
  
```
pragma solidity 0.8.18;

contract MyToken {

    // public variables here

    string public myToken = "REInc0at";
    string public tokenAbbrv = "REI";
    uint public totalSupply = 0;

    // mapping variable here

    mapping (address => uint) public balances;

    // mint function

    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] +=_value;
    }

    // burn function

    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

* To execute the file, go to the left navigation side and press 'solidity compiler', then press 'Create_My_Token.sol'. You can also use CTRL + S to compile the file.

* Then go back to the left navigation side and press 'Deploy & run transactions', then press 'Deploy'.

* Then scroll down to 'Deployed contracts' >> 'MYTOKEN' >> then you will see our two functions which are the 'burn' and 'mint'. Ypu can also see your balance, myToken, tokenAbbrv, and totalSupply.

* to try the functions, you can copy the account above the gas limit then paste it in the _address

## Authors

Marielle Lapeña

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
