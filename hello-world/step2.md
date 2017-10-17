# Managing your ETH Wallet


Before deploying and testing iExec, you need to get some ETH to pay for the transaction fees (gas).

First, we'll create a  wallet on the ropsten network:

`iexec wallet create`{{execute}}

Ropsten is a test network, where ETH has no value. Let's get some from a faucet:

`iexec wallet getETH`{{execute}}

You can now check how many ETH you have on your wallet:

`iexec wallet show`{{execute}}

If you have not been able to get ETH, this might be because of ropsten instability. In this
case, join our slack and we'll explain how to proceed with a different test network.

As soon as your ETH balances are positive, you can deploy your Dapp.

# Understanding the Dapp contract

The contract Factorial.sol interfaces the off-chain application with Ethereum. It extends the IexecOracleAPI smart contract.

Dapp Provider can set the DAPP_PRICE that a user will have to pay in RLC for the usage.

If it is a free Dapp, he can set 0.


<pre class="file" data-filename="iexec-factorial/contracts/Factorial.sol" data-target="replace">
pragma solidity ^0.4.11;
import "./IexecOracleAPI.sol";
contract Factorial is IexecOracleAPI{

  uint public constant DAPP_PRICE = 1;

  function Factorial (address _iexecOracleAddress) IexecOracleAPI(_iexecOracleAddress,DAPP_PRICE){

  }

}
</pre>
|

# I deploy

This migrates the Dapp on the blockchain:

`iexec migrate`{{execute}}

This will use information from the iexec and truffle config files to deploy the contract on Ethereum.

You can see your new deployed dapp in  :
https://explorer.iex.ec in the "last dapp registrations" tab.
