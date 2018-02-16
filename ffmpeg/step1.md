# Pre-requisites
Let's install the [iExec SDK](https://github.com/iExecBlockchainComputing/iexec-sdk) using Nodejs:

`npm -g install iexec`{{execute}}

# Init a base project

Let's start your iExec project with the bare minimum:

`iexec init`{{execute}}

Rename and enter the project:

`mv iexec-init iexec-ffmpeg && cd iexec-ffmpeg`{{execute}}

Your iExec dapp is composed of:

* an ```app``` directory: In case you have a binary app, put it here. If you are already using Docker (and you should!) then this directory is not used.

* a ```contracts``` directory: A smart contract that interfaces with your iExec dapp from Ethereum to the offchain app.

* an ```iexec.js``` file: This is where you describe your project **name**, your **app**, and your **work**.

# setup your wallet

`iexec wallet create`{{execute}}

`iexec wallet getETH`{{execute}}

`iexec account login`{{execute}}

`iexec wallet show`{{execute}}
