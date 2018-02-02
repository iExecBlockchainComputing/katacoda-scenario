# Dapp address from iExec Dapp Store
In order to use a dapp, you need to know its ethereum address.

Go to https://dapps.iex.ec and copy the address of the factorial dapp on Ropsten network.

# Submit a work on the dapp
Let's suppose you just copied the address of the factorial dapp from https://dapps.iex.ec, here is how to submit a work on it:

`iexec submit 10 --dapp 0x31407014cd396e87c3938260C110A97450ab0b92`{{execute}}

# Check the result
Use the submission transaction hash to check the status of your work:
`iexec result <submit_tx_Hash>`{{execute}}

If it's completed, you can now download the result by adding the --save flag:
`iexec result <submit_tx_Hash> --save`{{execute}}
