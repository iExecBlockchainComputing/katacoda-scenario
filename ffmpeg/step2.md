
For the example, we take the ffmpeg tool to illustrate that you can use existing application or build new one and monitized it thanks to the RLC Token and iExec netxork

# Prepare your ffmpeg binary app

We take the static build version of ffmpeg here https://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz.

The uncompress version is on the ffmpeg branch of iexec-dapp-samples.

We will download it on the apps directory of our new iexec-ffmpeg project :
  
`cd apps`{{execute}}

`curl -o Ffmpeg -L https://raw.githubusercontent.com/iExecBlockchainComputing/iexec-dapp-samples/ffmpeg/apps/Ffmpeg && chmod +x Ffmpeg`{{execute}}

  
# Test your ffmpeg before deployment

First download a sample movie to encode :


 `curl -OL http://techslides.com/demos/sample-videos/small.mp4`{{execute}}


Then test locally your Ffmpeg binary with the following command  :

 `./Ffmpeg -i small.mp4 small.avi`{{execute}}
 
Your new small.avi must be present in apps directory.

Go back to the main directory for the next step:

 `cd ..`{{execute}}