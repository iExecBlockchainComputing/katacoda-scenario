# Prepare your binary app

We take the static build version of ffmpeg find here https://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz.

The uncompress version has been pushed on the ffmpeg  branch of iexec-dapp-samples.

  `mkdir apps`{{execute}}
  
  
  `cd apps`{{execute}}
  
  
  `curl -o Ffmpeg -L https://raw.githubusercontent.com/iExecBlockchainComputing/iexec-dapp-samples/ffmpeg/apps/Ffmpeg && chmod +x Ffmpeg`{{execute}}
  

 
  
# Test your ffmpeg before deployment

First download a sample movie 


 `curl -OL http://techslides.com/demos/sample-videos/small.mp4`{{execute}}


To your Ffmpeg command locally :

 `./Ffmpeg -i small.mp4 small.avi`{{execute}}
 

Go back to the main directory:

 `cd ..`{{execute}}