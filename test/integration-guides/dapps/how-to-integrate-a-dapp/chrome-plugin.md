---
description: Integrating the Google Chrome Cyano wallet plugin
---

# Chrome Plugin

Before using the [dAPI for Chrome](https://github.com/ontio/ontology-dapi), it is necessary to first install and implement a wallet that has the `dAPI provider` functionality built into it, for e.g., [Cyano Wallet for Chrome](https://github.com/OntologyCommunityDevelopers/cyano-wallet).

The `dAPI` can be implemented using `TypeScript`, and can also be used in `JavaScript` programs.

Some of the more popular usage channels for `dApps`, apart from opening the `dApp` in the `Chrome` browser, also support launching it in the mobile wallet. The access scheme for opening the `dApp` in the wallet is illustrated [here](https://dev-docs.ont.io/#/docs-cn/dApp-Integration/01-DAppDocking-Wallet-Opens-DApp).

Here is a step by step guide to assist developers with the integration process:

## 1. Development environment set-up and Installation

Before starting with the actual development process, do ensure that the following tools are installed and set-up on your local machine.

* _**Node.js v6+  \(LTS with npm\) -**_ [Download link](https://nodejs.org/en/download/)
* _**Google Chrome -**_ [Download link](https://www.google.com/chrome/)
* _**Cyano Wallet Chrome Plugin -**_ [Download link](https://chrome.google.com/webstore/detail/ontology-web-wallet/dkdedlpgdmmkkfjabffeganieamfklkm)
* _**Git -**_ [Download link](https://git-scm.com/downloads)

Next, we can install Ontology's `dAPI`. While building `dApps`, this `dAPI` serves as one of the core APIs that allow us to communicate with the chain. The source code can be downloaded [here](https://github.com/ontio/ontology-dapi). To carry out the installation using `npm`, use the following shell command:k

```bash
npm install ontology-dapi
```

## 2. Creating a dAPI instance

Creating a `dAPI` instance involves importing and registering the client-side, as such:

```javascript
import { client } from 'ontology-dapi';
client.registerClient({});
```

## 3. Deploying dAPI methods

Once a `dAPI` instance is created successfully, `dAPI` methods can be used in a given `dApp`.

### Fetching account or identity information

```javascript
account = await client.api.asset.getAccount()
res = await client.api.identity.getIdentity();
```

### **Smart contract methods**

```javascript
const result = await client.api.smartContract.invoke({contract,method,parameters,gasPrice,gasLimit,requireIdentity});
const result = await client.api.smartContract.invokeRead({ contract, method, parameters });
const result = await client.api.smartContract.deploy({code,name,version,author,email,description,needStorage,gasPrice,gasLimit});
```

### **Communication methods that assist interaction with the chain**

```javascript
const network = await client.api.network.getNetwork();
const height = await client.api.network.getBlockHeight();
const block = await client.api.network.getBlock({ block: 1 });
const transaction = await client.api.network.getTransaction({txHash: '314e24e5bb0bd88852b2f13e673e5dcdfd53bdab909de8b9812644d6871bc05f'});
const balance = await client.api.network.getBalance({ address: 'AcyLq3tokVpkMBMLALVMWRdVJ83TTgBUwU' });
```

### **Account transfer method**

```javascript
const result = await client.api.asset.makeTransfer({ recipient, asset, amount });
```

### Data signature methods

```javascript
const message: string = values.message;
const signature: Signature = {
  data,
  publicKey
};
const result = await client.api.message.signMessage({ message });
const result = await client.api.message.verifyMessage({ message, signature });
```

For a comprehensive list of all the available `dAPI` methods, please refer to the [dAPI Specification](https://github.com/backslash47/OEPs/blob/oep-dapp-api/OEP-6/OEP-6.mediawiki). 

## 4. dAPI demonstration

Follow the link below to refer to a demo `dApp` that utilizes the `dAPI` methods mentioned above.

{% page-ref page="../../../untitled-1-1/untitled/untitled-1.md" %}

### How to set the gaslimit and gasprice

Every transaction that takes place on the chain includes a `gaslimit` and `gasprice`.

`gasprice` has a correlation with the amount of standby time while the given transaction is packaged. Currently, the lowest value of `gasprice` is 500 units on the test net and main net.

The `gaslimit` of deployment contracts is set based on the complexity of smart contract's execution process. The minimum `gaslimit` value of a contract can be determined before deploying it by carrying out a pre-execution. The default `gaslimit` value of `native` contracts is 20000, while that of deployment contracts is usually higher than 20000000 units, generally speaking.

### How to handle addresses

The Chrome plugin Cyano wallet only accepts addresses in ByteArray format when importing addresses. While testing smart contracts in SmartX, the IDE automatically converts addresses to ByteArray format. So, there will be no address related issues during the deployment phase. However, in the developer's local environment, if the conversion is not carried out manually, the system will return an error.

The following method can be used to convert addresses to ByteArray format in JavaScript:

```javascript
import {Crypto} from 'ontology-ts-sdk';
var address = new Crypto.Address(account).serialize() //The "address" assigned here is in ByteArray format
```



