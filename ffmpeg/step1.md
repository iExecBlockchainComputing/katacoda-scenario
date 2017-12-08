



Pre-requisite: You need to have [node.js](https://nodejs.org/en/) installed on your machine.

`npm -g install iexec`{{execute}}


#Prepare your ffmpeg project


 For this tutorial, we'll first scaffold the iexec dapp project template
 Factorial is compute-intensive and thus  better executed off-chain.
 The following command initializes a basic iexec Dapp template for you.

`iexec init`{{execute}}


Your iexec Dapp is composed at the minimum of two parts:

* an offchain app, which can be any kind of legacy application. The offchain app will be executed by the iexec decentralized cloud.
* a smart contract that interfaces your iExec Dapp from Ethereum to the offchain app.


You will deploy those 2 parts in this tutorial, the ffmepg off-chain app in the iExec network and the dapp smart contract in ethereum testnet.


A new directory iexec-init have been created. Let's rename it for our need :

`mv iexec-init iexec-ffmpeg`{{execute}}

Go into the created directory:

`cd iexec-ffmpeg`{{execute}}


# Name your project


In iexec.js, The field name must be the same for  :
  - the name of your dapp smart contract in the contract directory.
  - the name of your binary in apps 'Ffmpeg'
  
  We choose the following name : Ffmpeg. Rename MyContract to Ffmpeg in iexec.js :
  
  `sed -i "s/.*name:.*/name:'Ffmpeg',/g" iexec.js`{{execute}}
  

# Name your smart contract dapp

  Rename the contract file MyContract.sol to Ffmpeg.sol
  
  `mv contracts/MyContract.sol  contracts/Ffmpeg.sol`{{execute}}
  
  
  Rename the contract  MyContract to Ffmpeg in Ffmpeg.sol
  
  `sed -i "s/MyContract/Ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
  
  Rename the init name to ffmpeg in Ffmpeg.sol
  
  `sed -i "s/init/ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
  
  
