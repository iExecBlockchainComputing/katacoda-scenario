
Make sure you have enough ether to deploy your app. See our first [Hello World](https://www.katacoda.com/sulliwane/scenarios/hello-world) tutorial for more details.

`iexec wallet create`{{execute}}


`iexec wallet getETH`{{execute}}


`iexec wallet show`{{execute}}

Once you have some ether, you are ready to deploy it your app.

With the deploy command you will:
- Deploy the Dapp smart contract on Ethereum
- Login to the iExec network with your Ethereum addresss and obtain an access token
- Deploy the ffmpeg binary app on the iExec network thanks to your access token.

`iexec deploy`{{execute}}


To the following question:
`? You are not logged in yet, log in?`

Answer `Y`{{execute}} 


# Submit a task to encode your film on the iExec decentralized cloud !


You may now submit a task by sending a transaction to the dapp smart contract.

You can parameter your task in a json format.

The parameters will be useful for the worker to succesfully complete the task.

- cmdline: ffmpeg command args. The same command args as your previous local test.

- dirinuri: input file(s) needed. The worker will download it(them) before the execution.

`iexec submit "{ \"cmdline\": \"-i demos/sample-videos/small.mp4 small.avi\", \"dirinuri\": \"http://techslides.com/demos/sample-videos/small.mp4\" }"`{{execute}}

# Get your ffmpeg task result 

Use the txHash from the submit to check the result of your task with:

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528`{{execute}}

When you see that your task has been completed and that you have a result uri like this one:

`
resuri:   "xw://xw.iex.ec/1f038f8a-6b2d-4f5d-a184-30402c44c437"
`

You can download the result with --save option:

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528 --save`{{execute}}

Now unzip the result:

`unzip 0x*`{{execute}}

You must be able to see your new encoded video small.avi result!
`
  inflating: stderr.txt
  inflating: small.avi
`

The result retrieved is a zip file coming from a worker. 

The zip contains all the files created or modified by the worker execution.

