# dynamicNFT

Here are two fundamental settings plus a interface

In the first setting the owner can edit features of the NFT. The features are currently not defined yet but can be implemented no sweat (IBEX categories and indicators)

In the second setting additional and external conditionality can be added. For example the another or the owner address needs to fulfil certain condition (own tokens etc)



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
Next test more dynamic incorporating upgradability only if a condition is met (here hodling a certain amount of token) in the same way the dNFT could be downgraded under certain conditions

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


