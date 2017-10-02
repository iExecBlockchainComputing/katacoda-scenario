# Managing your Wallet 


Before deploying and testing iexec, you need to get some ETH to pay for the  transaction fees (gas). 

First, we'll create a  wallet on the ropsten network:

`iexec wallet create`{{execute}}

Ropsten is a test network, where ETH has no value. Let's get some from a faucet:

`iexec wallet getETH`{{execute}}

You can now check how many ETH you have on your wallet:

`iexec wallet show`{{execute}}

If you have not been able to get ETH, this might be because of ropsten instability. In this
case, join our slack and we'll explain how to proceed with a different test network.

As soon as your balance is positive, you can deploy your Dapp.

# Understanding the Dapp contract

The contract Factorial.sol interfaces the offchain application with Ethereum. It extends the IexecOracleAPI smart contract.

<pre class="file" data-filename="iexec-factorial/contracts/Factorial.sol" data-target="replace">
pragma solidity ^0.4.11;
import "./IexecOracleAPI.sol";
contract Factorial is IexecOracleAPI{

  function Factorial (address _iexecOracleAddress) IexecOracleAPI(_iexecOracleAddress){

  }

}
</pre>



# I deploy

This migrates the Dapp on the blockchain:

`iexec migrate`{{execute}}

This will use information from the iexec and truffle config files to deploy the contract on Ethereum.

you can see your new deployed dapp in  :
https://explorer.iex.ec in the "last dapp registrations" tab.

This is the iexec configuration file:

<pre class="file" data-filename="iexec-factorial/iexec.js" data-target="replace">
// iexec.js
module.exports = {
    name: 'Factorial',  // the name of the contract to be deployed
    // the constructor arguments for contract deployment logic :
    constructorArgs: ['0xb34406538112bd2b3036b2c417c7cff827777a11'], // oracle v0.1.2 ropsten
    // constructorArgs: ['0x98275d4b6511ef05ed063d127dd82b72588326c9'], // oracle v0.1.2 rinkeby
    // constructorArgs: ['0xb81d38d843cb526a3d0c3130d568fe09799135aa'], // oracle v0.1.2 kovan
};
</pre>
