Vogue model Smart Contract
This Solidity program is a simple contract that demonstrates the use of require(), assert(), and revert() statements in Solidity.The purpose of the contract is to demonstrate the error handling while creation and updation of vogue models and enterprise using require(), assert() and revert().

Description
This contract simulates a vogue model system Users can set their age and model enterprise, and then check if they are eligible for modelling based on these details. The contract uses Solidity's require(), assert(), and revert() statements to enforce rules and validate conditions.

Getting Started
Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at Remix Ethereum IDE.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., smart_contract.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
contract VogueModels {
    mapping(address => uint) public age;
    mapping(address => bool) public haveEnterprise;
    function setAge(uint _age) public {
        require(_age > 0 && _age < 50, "Invalid age provided.");
        age[msg.sender] = _age;
    }
    function setEnterprise(bool _haveEnterprise) public {
        haveEnterprise[msg.sender] =_haveEnterprise;
    }
    function checkEligibility() public view returns (bool) {
        uint userAge = age[msg.sender];
        bool Enterprise = haveEnterprise[msg.sender];
        require(userAge > 0, "Age is not set. Please set your age first.");
        if (userAge < 15) {
            revert("You are should wait");
        }
        assert(Enterprise == true);
        return true;
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "smartcontract.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "vogue model" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the setAge(), sethaveEnterprise(), and checkEligibility() functions. Set your age and entereprise status first, and then check your eligibility for a vogue models.

Authors
Shreya Kandpal
shreyakandpal17@gmail.com
