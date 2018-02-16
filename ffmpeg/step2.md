# Define your application
As the Ffmpeg application [already has a Docker image](https://hub.docker.com/r/jrottenberg/ffmpeg/), this step is super easy: Simply rename the docker image name in the ```iexec.js``` to the one you want:

`sed -i "s/docker-image-name/jrottenberg\/ffmpeg:scratch/g" iexec.js`{{execute}}


# Deploy your application
This step will do 2 things:
1. deploy the smart contract on Ethereum blockchain
2. deploy the application description to iExec server

`iexec deploy`{{execute}}
