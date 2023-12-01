# dynamicNFT
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
Next test more dynamic incorporating upgradability only if a condition is met (here hodling a certain amount of token)

***Front end Test 3
----------------
npm init
npm install -s create-react-app
npm install -s ethers
npx create-react-app frontend
cd frontend
npm start dev


and creating an frontend/src/App.js file along the lines 

import { useState } from "react";
import './App.css';

import tokenABI from './tokenABI.json';
import nftABI from './nftABI.json';
import { ethers } from "ethers";

let provider, signer, address, token, nft, tokenId;

function App() {
  const [msg, setMsg] = useState('');

  const tokenContractAddress = '0xCONTRACTADDRESS';
  const nftContractAddress = '0xNFTCONTRACTADDRESS';
  
  const connect = async () => {
    provider = new ethers.providers.Web3Provider(window.ethereum);
    await provider.send("eth_requestAccounts", []);
    signer = provider.getSigner();
    token = new ethers.Contract(tokenContractAddress, tokenABI, signer);
    nft = new ethers.Contract(nftContractAddress, nftABI, signer);
    address = await signer.getAddress();
    setMsg(`Connected: ${address}`);  
  }
  
  const mint = async () => {
    const tx = await nft.mint();
    setMsg(`Processing transaction...`);
    await tx.wait();
    tokenId = await nft.tokenId();
    tokenId -= 1; // previous tokenId is ours
    const b64 = await nft.tokenURI(tokenId);
    const json = atob(b64.split(',')[1]);
    const imageURL = JSON.parse(json).image;
    setMsg(`You own IUCN NFT #${tokenId}`);
    document.getElementById('image').innerHTML = `<img src="${imageURL}" />`;
  }
  
  const earn = async () => {
    const tx = await nft.earnTokens();
    setMsg(`Sending you some tokens...`);
    await tx.wait();
    const balance = await token.balanceOf(address);
    setMsg(`Your balance is now: ${balance}`);
  }
  
  const alien = async () => {
    const tx = await nft.makeAlien(tokenId);
    setMsg(`Something strange is happening...`);
    await tx.wait();
    const b64 = await nft.tokenURI(tokenId);
    const json = atob(b64.split(',')[1]);
    const imageURL = JSON.parse(json).image;
    setMsg(`You own IUCN updated Alien NFT #${tokenId}`);
    document.getElementById('image').innerHTML = `<img src="${imageURL}" />`;
    
  }

  return (
    <div className="App">
      <header className="App-header">
        <h1>WomenWhoCode</h1>
        <h2>Dynamic NFT</h2>
        <div id="image"></div>
        <div id="buttons">
          <button onClick={connect}>Connect</button>
          <button onClick={mint}>Mint</button>
          <button onClick={earn}>Earn</button>
          <button onClick={alien}>Alien</button>
        </div>
        <div id="msg">{msg}</div>
      </header>
    </div>
  );
}

export default App;
