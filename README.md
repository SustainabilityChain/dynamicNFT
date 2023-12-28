# dynamicNFT

In our project, we've created a flexible system with two main parts, along with an additional user-friendly interface.

Customizable Features: In the first part of our system, the user, who typically owns a digital asset eg a certificate, has the ability to make changes to its characteristics. While we haven't yet defined what these characteristics are, we're planning to align them with IBEX categories and indicators. This means that these features will be easy to implement and understand.

Conditional Access: The second part allows for the application of certain rules or conditions. For instance, a user or the original owner of the digital asset might need to meet specific requirements, such as owning a certain number of tokens or fulfilling other criteria, to access or utilize the asset. The fulfilment will be validated by IUCN.

These settings are designed to be user-friendly and adaptable, ensuring that even those without a technical background can easily understand and use our system. This approach could be particularly relevant for environmental projects, where clear and accessible technology can play a crucial role in conservation efforts."



*** Test Environment for IUCN
----------------

***Test 1
----------------
First test done with dNFT-IUCN-test.sol

https://github.com/SustainabilityChain/dynamicNFT/blob/main/dNFT-IUCN-test.sol

deployed on mumbai

https://mumbai.polygonscan.com/address/0x12b935250e3204a2ac1dacc01dca68a3c3404cfd

***Test 2
----------------
This test represent a more dynamic incorporating upgradability only if a condition is met in the same way the dNFT could be downgraded under certain conditions.This means for example that an external investor can foster a certain IBEX category through an onchain escrow that is released by IUCN.

contract here https://github.com/SustainabilityChain/dynamicNFT/blob/main/dNFT-final.sol

Deployed here https://mumbai.polygonscan.com/tx/0x23417e51dd26e8d65f8d3dcc54f3fe6c4d31bc924ac64bc0e07824747caf0571

***Front end Test 3
----------------

npm init

npm install -s create-react-app

npm install -s ethers

npx create-react-app frontend

cd frontend

npm start dev


and creating an frontend/src/App.js file along the lines of App.js in this very directory


