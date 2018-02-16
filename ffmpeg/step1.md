# Pre-requisites
Let's install the [iExec SDK](https://github.com/iExecBlockchainComputing/iexec-sdk) using Nodejs:

`npm -g install iexec`{{execute}}

# Init a base project

Let's start your iExec project with the bare minimum:

`iexec init`{{execute}}

Enter the project:

`cd iexec-init`{{execute}}

Your iExec dapp is composed of:

* an ```app``` directory: In case you have a binary app, put it here. If you are already using Docker (and you should!) then this directory is not used.

* a ```contracts``` directory: A smart contract that interfaces with your iExec dapp from Ethereum to the offchain app.

* an ```iexec.js``` file: This is where you describe your project **name**, your **app**, and your **work**.

# setup your wallet

`iexec wallet create`{{execute}}

`iexec wallet getETH`{{execute}}

`iexec account login`{{execute}}

`iexec wallet show`{{execute}}

## Name your ffmpeg project

A new directory iexec-init has been created.

Let's rename it:

`mv iexec-init iexec-ffmpeg`{{execute}}

Now go into the created directory:

`cd iexec-ffmpeg`{{execute}}


In ```iexec.js```, the field name must be the same for :
  - the name of your dapp smart contract in the contract directory
  - the name of your binary in apps 'Ffmpeg'

Let's choose the following name: **Ffmpeg**.

Rename **MyContract** to **Ffmpeg** in ```iexec.js```:

`sed -i "s/.*name:.*/name:'Ffmpeg',/g" iexec.js`{{execute}}


Rename the contract file ```MyContract.sol``` to ```Ffmpeg.sol```:

`mv contracts/MyContract.sol  contracts/Ffmpeg.sol`{{execute}}


Rename the contract name **MyContract** to **Ffmpeg** in ```Ffmpeg.sol```:

`sed -i "s/MyContract/Ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}

Rename the **init** dapp name to **ffmpeg** in Ffmpeg.sol

`sed -i "s/init/ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}
