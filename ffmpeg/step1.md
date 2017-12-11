


Pre-requisite: You need to have [node.js](https://nodejs.org/en/) installed on your machine.

`npm -g install iexec`{{execute}}


# Scaffold the iExec dapp template 

 For this tutorial, we'll first scaffold the iExec dapp project template with the following command:

`iexec init`{{execute}}


Your iExec dapp is composed of:

* an under app directory:
the off-chain app, which can be any kind of legacy application, either created by you or by someone else. The offchain app will be executed by the iExec decentralized cloud.

* an under contracts directory:
a smart contract that interfaces with your iExec dapp from Ethereum to the offchain app.


You will deploy those 2 parts in this tutorial: the ffmepg off-chain app in the iExec network, and the dapp smart contract on the Ethereum testnet.


## Name your ffmpeg project

A new directory iexec-init has been created. 

Let's rename it:

`mv iexec-init iexec-ffmpeg`{{execute}}

Now go into the created directory:

`cd iexec-ffmpeg`{{execute}}


In iexec.js, the field name must be the same for :
  - the name of your dapp smart contract in the contract directory
  - the name of your binary in apps 'Ffmpeg'
  
Let's choose the following name: Ffmpeg.

Rename MyContract to Ffmpeg in iexec.js:
  
`sed -i "s/.*name:.*/name:'Ffmpeg',/g" iexec.js`{{execute}}
  
  
Rename the contract file MyContract.sol to Ffmpeg.sol
  
`mv contracts/MyContract.sol  contracts/Ffmpeg.sol`{{execute}}
  
  
Rename the contract name 'MyContract' to 'Ffmpeg' in Ffmpeg.sol
  
`sed -i "s/MyContract/Ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
  
Rename the 'init' dapp name to 'ffmpeg' in Ffmpeg.sol
  
`sed -i "s/init/ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}

 
