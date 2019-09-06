# Mobile Wallet Integration

## Fundamental concepts

Let us take a look at the processes that distributed technologies such as `dApps` and mobile wallets carry out.

### Role of dApps

The `dApp` back end primarily carries out the following tasks:

* `dApp` operations, i.e., generating the relevant login parameters, or the parameters for invoking smart contracts.
* Synchronizing with the on-chain data, and fetching the results of login, or smart contract invocation.

### Role of mobile wallets

A mobile wallet acts as a `provider`. It carries out the roles that involve interacting with the chain, such as providing the signature data, pre-executing and executing transactions, etc.

{% hint style="info" %}
The above description is with respect to the wallets that can serve as providers. Currently, the following are supported:

* \*\*\*\*[**ONTO**](https://onto.app/) ****
* \*\*\*\*[**Cyano Wallet**](http://101.132.193.149/files/app-debug.apk)\*\*\*\*
* \*\*\*\*[**O-Wallet**](https://github.com/ontio/OWallet/releases)\*\*\*\*
* \*\*\*\*[**Math Wallet**](http://www.mathwallet.org/en/)\*\*\*\*
* \*\*\*\*[**Banko**](http://bankowallet.com/pc.html)\*\*\*\*
* \*\*\*\*[**Huobi Wallet**](https://www.huobiwallet.com/)\*\*\*\*
{% endhint %}

