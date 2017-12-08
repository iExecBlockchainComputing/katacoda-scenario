



Pre-requisite: You need to have [node.js](https://nodejs.org/en/) installed on your machine.

`npm -g install iexec`{{execute}}


# scaffolded and prepare your ffmpeg project


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


# Named your project


In iexec.js, The field name must be the same for  :
  - the name of your dapp smart contract in the contract directory.
  - the name of your binary in apps 'Ffmpeg'
  
  We choose the following name : Ffmpeg. Rename MyContract to Ffmpeg in iexec.js :
  
  `sed -i "s/.*name:.*/name:'Ffmpeg',/g" iexec.js`{{execute}}
  

# Renamed your smart contract

  Rename the contract file MyContract.sol to Ffmpeg.sol
  
  `mv contracts/MyContract.sol  contracts/Ffmpeg.sol`{{execute}}
  
  
  Rename the contract  MyContract to Ffmpeg in Ffmpeg.sol
  
  `sed -i "s/MyContract/Ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
  `sed -i "s/init/ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
  
  
# Prepare your binary

Find a static build version of ffmpeg. For instance here :

  `mkdir apps`{{execute}}
  `cd apps`{{execute}}
  `wget https://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz`{{execute}}

  `tar xvfJ ffmpeg-release-64bit-static.tar.xz`{{execute}}

  `cp -f ffmpeg-3.4-64bit-static/ffmpeg ./Ffmpeg`{{execute}}
  
  
# Test your binary before deployment

First download a sample movie 


 `wget http://techslides.com/demos/sample-videos/small.mp4`{{execute}}


To your Ffmpeg command locally :

 `./Ffmpeg -i small.mp4 small.avi`{{execute}}


# Deploy your smart contract and Ffmpeg binary in iexec network

Make sure you have enought ether to deploy it. See our first hello world tutorial for more details.

`iexec wallet create`{{execute}}


`iexec wallet getETH`{{execute}}


`iexec wallet show`{{execute}}

When you have some ether. You are ready to deploy it.

With the deploy command you will :
- Deploy the Dapp smart contract into Ethereum.
- Login to iexec network thanks to your ethereum addresss and obtain an access token.
- Deploy the ffmpeg binary app in iexec network thanks to your access token.

`iexec deploy`{{execute}}


To the following question:
`? You are not logged in yet, log in?`

Answer `Y`{{execute}} 


# Ask for ffmpeg encoding thanks to your new deployed dapp :

`iexec submit {“dirinuri”:“http://techslides.com/demos/sample-videos/small.mp4“,“cmdline”:”small.mp4 small.avi”}`{{execute}}

`iexec submit "{ \"cmdline\": \"-i demos/sample-videos/small.mp4 small.avi\", \"dirinuri\": \"http://techslides.com/demos/sample-videos/small.mp4\" }"`{{execute}}

# Get your ffmpeg result 

Use the txHash from the submit to check the result of your submit with:

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528`{{execute}}



