
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

You can pass thoses parameters next to the command line like this :

`iexec submit "{ \"cmdline\": \"-i small.mp4 small.avi\", \"dirinuri\": \"http://techslides.com/demos/sample-videos/small.mp4\" }"`

But you can also, put them in iexec.js in the work section :

`sed -i "s/.*cmdline:.*/cmdline:'-i small.mp4 small.avi', dirinuri:'http:\/\/techslides.com\/demos\/sample-videos\/small.mp4',/g" iexec.js`{{execute}}

You iexec.js should now likes like this :

<pre class="file" data-filename="iexec-factorial/iexec.js" data-target="replace">
module.exports = {
  name: 'Ffmpeg',
  data: {
    type: 'BINARY',
    cpu: 'AMD64',
    os: 'LINUX',
  },
  work: {
    cmdline:'-i small.mp4 small.avi',
    dirinuri:'http://techslides.com/demos/sample-videos/small.mp4',
  }
};
</pre>


Now just call iexec submit, it will submit you work with args present in iexec.js :

`iexec submit`{{execute}}


# Get your ffmpeg work result

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

# Don't waste money!
Be nice and give back your RLC and ETH to the faucet by sweeping your wallet:

`iexec sweep`{{execute}}

Thank you!
