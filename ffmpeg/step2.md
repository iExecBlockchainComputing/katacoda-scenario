
As an example, let's take the ffmpeg tool to illustrate that you can use an already existing application, or build a new one and monitize it in RLC tokens on the iExec network.

# Prepare your ffmpeg binary app

Let's take the static build version of ffmpeg from: https://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz.

The uncompressed version is on the ffmpeg branch of iexec-dapp-samples.

Let's download it to the apps directory:
  
`cd apps`{{execute}}

`curl -o Ffmpeg -L https://raw.githubusercontent.com/iExecBlockchainComputing/iexec-dapp-samples/ffmpeg/apps/Ffmpeg && chmod +x Ffmpeg`{{execute}}

  
# Test your ffmpeg before deployment

First, let's download a movie sample to encode:


 `curl -OL http://techslides.com/demos/sample-videos/small.mp4`{{execute}}


You can then test locally the Ffmpeg binary with the following command:

 `./Ffmpeg -i small.mp4 small.avi`{{execute}}
 
Your result small.avi must be present in the apps directory.

Kindly go back to the main directory for the next step:

 `cd ..`{{execute}}
