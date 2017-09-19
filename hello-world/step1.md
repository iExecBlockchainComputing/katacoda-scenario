
# Install the iexec-sdk


Pre-requisite: You need to have [node.js](https://nodejs.org/en/) installed on your machine.

`npm -g install iexec`{{execute}}

check iexec help:

`iexec --help`{{execute}}

and iexec version:

`iexec --version`{{execute}}

Let's get started!

# Install and run your first application with iexec


This initializes a basic iexec dapp for you. For this tutorial, we'll work with the iexec factorial dapp:

`iexec init factorial`{{execute}}


Your iexec Dapps is composed at the minimum of two parts:

* an offchain app, which can be any kind of legacy application. The offchain app will be executed by the iexec decentralised cloud.
* a smart contract that interfaces your iexec Dapp from Ethereum to the offchain app.


Factorial offchain app is already installed and deployed in the iexec network. 

Go into the created directory :

`cd iexec-factorial`{{execute}}


