## Name your project

Let's say you want to name your new project: **Ffmpeg**, here are the required steps:

Rename **MyContract** to **Ffmpeg** in ```iexec.js```:

`sed -i "s/.*name:.*/name:'Ffmpeg',/g" iexec.js`{{execute}}


Rename the contract file ```MyContract.sol``` to ```Ffmpeg.sol```:

`mv contracts/MyContract.sol  contracts/Ffmpeg.sol`{{execute}}


Rename the contract name **MyContract** to **Ffmpeg** in ```Ffmpeg.sol```:

`sed -i "s/MyContract/Ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}

Rename the **init** dapp name to **ffmpeg** in Ffmpeg.sol

`sed -i "s/init/ffmpeg/g" contracts/Ffmpeg.sol`{{execute}}

# Describe your application
As the Ffmpeg application [already has a Docker image](https://hub.docker.com/r/jrottenberg/ffmpeg/), this step is super easy: Simply rename the docker image name in the ```iexec.js``` to the one you want:

`sed -i "s/docker-image-name/jrottenberg\/ffmpeg:scratch/g" iexec.js`{{execute}}


# Deploy your application
This step will do 2 things:
1. deploy the smart contract on Ethereum blockchain
2. deploy the application description to iExec server

`iexec deploy`{{execute}}
