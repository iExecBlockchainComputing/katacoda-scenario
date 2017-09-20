#Wallet 


Before deploying and testing iexec, you need to get some ETH to pay for the gaz and the transaction fees. 

First, we'll create a  wallet on the ropsten network
`iexec wallet create`{{execute}}

Ropsten is a test network, where ETH has no value. Let's get some from a faucet

`iexec wallet getETH`{{execute}}

You can check how many ETH you have on your wallet:
`iexec wallet show`{{execute}}

If you have not been able to get ETH, this might because of ropsten instability. In this
case, join our slack, and we'll explain you how to proceed with a different test network.

As soon as your balance is positive, you can deploy you Dapp.

# I deploy

This migrate the dapp on a blockchain:

`iexec migrate`{{execute}}

This will use informations from the iexec and truffle config file to deploy the contract on ethereum: This is the iexec configuration file:
```
// iexec.js
module.exports = {
    name: 'Factorial',  // the name of the contract to be deployed
    constructorArgs: ['0xe6b658facf9621eff76a0d649c61dba4c8de85fb'],  // the constructor arguments for contract deployment logic
};
```
