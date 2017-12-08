


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

`iexec submit "{ \"cmdline\": \"-i demos/sample-videos/small.mp4 small.avi\", \"dirinuri\": \"http://techslides.com/demos/sample-videos/small.mp4\" }"`{{execute}}

# Get your ffmpeg result 

Use the txHash from the submit to check the result of your submit with:

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528`{{execute}}

When you see that your task is completed and the result uri :

`
resuri:   "xw://xw.iex.ec/1f038f8a-6b2d-4f5d-a184-30402c44c437"
`

Download the result with --save option :

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528 --save`{{execute}}

Unzip the result :

`unzip 0x*`{{execute}}

You must see your new encoded video small.avi result !:
`
  inflating: stderr.txt
  inflating: small.avi
`


