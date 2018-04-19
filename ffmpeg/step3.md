# Submit a work to your iExec app
Before submitting a work, we need to define it in the ```iexec.js``` file.

Here are the parameters that will describe our work:
- ```cmdline```: ffmpeg cli arguments.
- ```dirinuri```: The worker will download this URI before executing the app (this points to the video in this case).

Let's add them to ```iexec.js```:

`sed -i "s/.*cmdline:.*/cmdline:'-i /iexec/small.mp4 /iexec/small.avi', dirinuri:'http:\/\/techslides.com\/demos\/sample-videos\/small.mp4',/g" iexec.js`{{execute}}

Now just submit the work to iExec:

`iexec submit`{{execute}}


# Get your ffmpeg work result
Check the progress of the work by running:

`iexec result <tx_hash>`{{execute}}

If you job is completed, you can download the result with --save option:

`iexec result <tx_hash> --save`{{execute}}

Now unzip the result:

`unzip 0x*`{{execute}}

You should see your new encoded video small.avi!
`
  inflating: stderr.txt
  inflating: small.avi
`

The result retrieved is a zip file coming from a worker.

The zip contains all the files created or modified by the worker execution.

# Don't waste money!
Be nice and give back your RLC and ETH to the faucet by sweeping your wallet:

`iexec wallet sweep`{{execute}}

Thank you!
