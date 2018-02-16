
# Managing your RLC Wallet
Now you leave the rôle of the Dapp Provider and take a Dapp User role.
We will used the same previous wallet already filled in ETH.
As a Dapp User you will need RLC.
You can with the wallet show command that the your RLC balances is currently null.
Let's call the RLC Faucet with :

`iexec wallet getRLC`{{execute}}

if you prefer, you have a web RLC faucet interface :
https://faucet.iex.ec/

You have to wait some time to receive your RLC from the Iexec Faucet.
After the transaction is processed, you can check your 10 nRLC received with :

`iexec wallet show`{{execute}}

Great. You account have RLC. Now you have to credit RLC for off-chain computation usage.
To do this you will call a function on the RLC Token (ERC20 approve function).

`iexec account allow 5`{{execute}}


After the transaction is processed, you can verify your credit for off-chain computation with :

`iexec account show`{{execute}}

# I exec
You now ready to go, submit your first calculation with :

`iexec submit 20`{{execute}}



While waiting for the result, you can see that you RLC balance has been used for off-chain computing.
And your RLC credit for off-chain computation has decrease.

`iexec wallet show`{{execute}}

`iexec account show`{{execute}}

Use the txHash from the submit to check the result of your submit with:

`iexec result 0x783236f489c1e4bcdfbac87475b71cd13e83266ba6d55cfb658324f281580528`{{execute}}

Be sure to replace `0x783236f...` by your txHash!  

It may take a moment for the computation to be completed. Repeat the last command until you can actually see the result.

When the computation is completed, RLC is tranfert to the Dapp Provider.
As you play Dapp Provider role and also the Dapp User Role, you will have your RLC balance with the same balance as when you start.

You can also go to the iexec explorer to see your transaction :
https://explorer.iex.ec in the "last submissions" tab.

Your smart contract is now "offchain computing ready!".

Sky is the limit for you and your smart contract!

# Don't waste money!
Be nice and give back your RLC and ETH to the faucet by sweeping your wallet:

`iexec sweep`{{execute}}

Thank you!
