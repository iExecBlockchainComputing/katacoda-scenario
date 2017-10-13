
# Install and run your first Dapp with iexec

Iexec allows Ethereum developers to create applications that can be executed off-chain. This package brings all the tools to develop, deploy and execute Dapps on Ethereum and iexec. Using these tools, you will be able to deploy any legacy applications in the iexec infrastructure and execute them through calls to Ethereum smart contracts.

In this tutorial, you will learn how to install and use the iexec Software Development Kit (iexec-sdk).

You will create your first smart contract that does a very simple off-chain computation: compute the factorial function of an integer.

First, you will take the rôle of a Dapp Provider by deploying a smart contract on the Ethereum blockchain. You will learn the basic of the IexecOracleAPI that your contract must inherit.
If desired, the dapp Provider can set a RLC price for the usage of his dapp.

Then, you will take the rôle of a Dapp User and see how the smart contract can now interact with iexec oracle to launch off-chain computations on the decentralized Cloud.
The dapp user will have to use his RLC token for this.

Let's get started!



[ INFO ] : Due to transactions delay on ethereum ropsten and rinkeby networks, you may have to wait few minutes between each steps of the scenario. The default network targeted by this tutorial is ropsten ( automatic faucet for ropsten). If you want to target  rinkeby or kovan networks or if you need help, join us on our slack.

Expected duration to complete the full scenario : <br>
Katacoda Hello World Scenario On Ropsten : 00:10:00 min to 00:30:00 min <br>
Katacoda Hello World Scenario On Rinkeby : 00:05:00 min to 00:20:00 min <br>
Katacoda Hello World Scenario On Kovan   : 00:02:00 min to 00:05:00 min
