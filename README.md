# functions-and-errors-solidity-

The purpose of the GreaterNumber contract is to find the greatest number among three input values (a, b, and c). It is implemented as a Solidity smart contract. The findGreater function takes three unsigned integer values as parameters and returns the greatest of the three.

The contract includes some validation checks to ensure that the input values are distinct and non-zero. If any of these conditions are not met, the function will revert and provide an error message.

The algorithm used to find the greatest number is based on nested if-else statements. It compares a with b and c to determine the greatest value and returns it. If c is the greatest number, the function will revert and provide an error message indicating that.
## Description

The provided Solidity code represents a smart contract called "GreaterNumber" that is designed to find the greatest number among three input values. The contract contains a single function called "findGreater" which takes three unsigned integer parameters (a, b, and c).

The purpose of this contract is to determine the largest number among the three inputs while ensuring that the values provided are distinct and non-zero. If any of the input values are the same or equal to zero, the contract will throw an error.

The function uses a series of if-else statements to compare the values. It starts by comparing "a" with "b" and then with "c". If "a" is greater than both "b" and "c", it is returned as the result. If "a" is not the greatest, it proceeds to check if "b" is greater than "c". If it is, "b" is returned as the result. If neither "a" nor "b" is the greatest, the function reverts with an error message stating that "c" is the greater number.

This contract can be deployed on a compatible blockchain network, such as Ethereum, and interacted with through transactions. Users can call the "findGreater" function and pass in three values to determine the greatest among them. The contract includes validation checks to ensure the inputs meet the required conditions.
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., module_project.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract GreaterNumber {
    function findGreater(uint256 a, uint256 b, uint256 c) external pure returns (uint256) {

        require(a != b && b != c && a !=c, " Input values must be distinct");

        assert(a != 0 && b != 0 && c != 0);

        if (a > b) {
            if(a > c) {
                return a;
            } else {
                revert("Input 'c' is the greater number");
            }
        } else if (b > c) {
            return b;
        } else {
            revert("Input 'c' is the greater number");
        }
    }
}   

```

The contract named "GreaterNumber" is defined.

The function "findGreater" is declared as an external function that takes three unsigned integers (a, b, and c) as parameters and returns an unsigned integer.

The "require" statement is used to validate that the input values are distinct (i.e., not equal to each other). If any of the input values are equal, the execution will stop, and the error message "Input values must be distinct" will be returned.

The "assert" statement is used to ensure that none of the input values are zero. If any of the input values are zero, it indicates an invalid state, and the execution will stop.

The function enters the conditional statements to determine the greater number among a, b, and c.

If "a" is greater than "b," it checks whether "a" is also greater than "c" using an inner conditional statement.

If "a" is indeed greater than "c," it returns the value of "a" as the greater number.

If "a" is not greater than "c," it reverts the execution with the error message "Input 'c' is the greater number."

If "a" is not greater than "b," it means that "b" is greater than or equal to "a." In this case, it checks whether "b" is greater than "c" using the outer conditional statement.

If "b" is greater than "c," it returns the value of "b" as the greater number.

If "b" is not greater than "c," it means that "c" is the greatest number. In this case, it reverts the execution with the error message "Input 'c' is the greater number."


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
