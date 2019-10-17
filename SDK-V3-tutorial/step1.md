# Install and Init you iExec project

## Install SDK

Pre-requisite: You need to have [node.js](https://nodejs.org/en/) installed on your machine. 
Then let's install iexec CLI tool:

`npm -g install iexec`{{execute}}

Check iexec help:

`iexec --help`{{execute}}

Check iexec version (should be 3.1.0):

`iexec --version`{{execute}}

## Init you iExec project

`iexec init`{{execute}}

Your iexec Dapp is composed at the minimum of 4 files:

* `iexec.json` the main config file.
* `chain.json` the network config file, to set ethereum chain for example.

A wallet has been created; please refer to [wallet management](https://github.com/iExecBlockchainComputing/iexec-sdk#wallet).


## Load your wallet

`iexec wallet show`{{execute}}

let's get some ETH:

`iexec wallet getETH`{{execute}}

As the default chain is Kovan, you have to manually request for kovan ETH by sending your wallet public address in this gitter chat group: https://gitter.im/kovan-testnet/faucet

Now let's get some RLC:

`iexec wallet getRLC`{{execute}}

If you have ETH and RLC on you wallet, you can now deposit RLC on you iExec account:

`iexec account deposit 50`{{execute}}

You are good, now that you have RLC on you iExec account, you can go to next step.
