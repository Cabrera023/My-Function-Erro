# My-Function-Erro
The require(), assert(), and revert() statements are implemented in this Solidity smart contract. Users can add and remove balance with it, and it will handle any problems graciously and make sure certain requirements are met.

# Get Started 

# Prerequisites
To interact with the smart contract, you'll need:

* A web browser
* An internet connection
# Running in Remix IDE

1.Launch your internet browser and go to  Remix IDE.

2.In Remix IDE, create a new file and give it a name. MyContract.sol

3.Duplicate the text of MyContract.sol from this repository and paste it into the newly created file.


// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract MyContract {
    uint256 public value;
    address public owner;

    constructor() {
      owner = msg.sender;

    }
    
    function setValue(uint256 _newValue) public {

      require(msg.sender == owner, "Only the owner can set the value");

      assert(_newValue != 0);

      if(_newValue < value) {
          revert("New value must be greater than or equel to current value");
      }
      
      value = _newValue;
    }
}







4.Click the "Compile" button after selecting the "Solidity Compiler" tab in the Remix IDE to begin compiling the smart contract.

5.Go to the "Deploy & Run Transactions" page after the contract has properly compiled.

6.Make sure the right environment (e.g., JavaScript VM, Injected Web3, etc.) is selected.

7.Click the "Deploy" button to make the contract operational.

8.The deployed contract can now be interacted with through the Remix IDE's provided user interface.
