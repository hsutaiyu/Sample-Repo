---
description: Mobile wallet QR code functionality
---

# QR code mechanism

This section aims at assisting the developer with integrating the QR code protocol `dAPI` into a dApp. This would allow the user to carry out services like login, invoke smart contracts, and more by scanning QR codes.

The parties involved in the process are:

* `dApp` side: Providing `dApps` for the users who are a part of the Ontology ecosystem is an important priority at Ontology.
* `Provider` side: Implementing `dAPI mobile` standard wallets.

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

## Interaction Process

The following charts illustrate the login and smart contract invocation process.

**Login**

![](../../../../.gitbook/assets/dappintegration-qrcode-login.jpg)

1. dApp end submits the QR code
2. The dApp server executes the login method
3. The dApp back end verfies the signature

**Smart Contract Invocation**

\*\*\*\*

