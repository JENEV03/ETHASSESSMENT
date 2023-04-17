# ETHASSESSMENT
This is a contract that has public variables that store the details about my coin, this contract also has mapping of address and mint function that takes two parameters
like address and value. This function then increases the total supply by that number and increases the balance of the address by that ammount.
This also has burn function, which works the opposite of the mind function, as it will destroy tokens.
Lastly, your burn function should have conditionals to make sure the balance of account is greater than or equal of the amount that is supposed to be burned

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    // public variables here
        string public name = "JENEVIVE";
        string public abbrv = "JEN";
        uint public supply = 0;

    // mapping variable here
        mapping(address => uint) public bal;

    // mint function
        function mint(address add, uint val) public{
            supply += val;
            bal[add] += val;
        }
    // burn function
        function burn(address add, uint val) public{
            if(bal[add] >= val){
                supply -= val;
                bal[add] -= val;
            }
        }
}


