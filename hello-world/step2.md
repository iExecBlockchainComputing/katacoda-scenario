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

This is the iexec configuration file:

<pre class="file" data-filename="iexec-factorial/iexec.js" data-target="replace">
// iexec.js
module.exports = {
    name: 'Factorial',  // the name of the contract to be deployed
    constructorArgs: ['0xe6b658facf9621eff76a0d649c61dba4c8de85fb'],  // the constructor arguments for contract deployment logic
};
</pre>
