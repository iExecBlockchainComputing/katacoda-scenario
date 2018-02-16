# Define your application
As the Ffmpeg application [already has a Docker image](https://hub.docker.com/r/jrottenberg/ffmpeg/), this step is super easy: Simply rename the docker image name in the ```iexec.js``` to the one you want:

`sed -i "s/docker-image-name/jrottenberg\/ffmpeg:scratch/g" iexec.js`{{execute}}


# Test your application
Before deploying to iExec, we need to make sure our applications is working properly, locally.

First, let's download a movie sample to encode:

`curl -OL http://techslides.com/demos/sample-videos/small.mp4`{{execute}}

You can then test locally the Ffmpeg binary with the following command:

`docker run --rm  -v $(pwd):/iexec-project -w /iexec-project jrottenberg/ffmpeg:scratch -i small.mp4 small.avi`{{execute}}

You should have a new ```small.avi``` file.

We are now confident that our app is working fine locally, and so we can deploy it to iExec.


# Deploy your application
This step will do 2 things:
1. deploy the smart contract on Ethereum blockchain
2. deploy the application description to iExec server

`iexec deploy`{{execute}}
