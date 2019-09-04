---
description: Integrating the Google Chrome Cyano wallet plugin
---

# Chrome Plugin

Before using the [dAPI for Chrome](https://github.com/ontio/ontology-dapi), it is necessary to first install and implement a wallet that has the `dAPI provider` functionality built into it, for e.g., [Cyano Wallet for Chrome](https://github.com/OntologyCommunityDevelopers/cyano-wallet).

The `dAPI` can be implemented using `TypeScript`, and can also be used in `JavaScript` programs.

Some of the more popular usage channels for `dApps`, apart from opening the `dApp` in the `Chrome` browser, also support launching it in the mobile wallet. The access scheme for opening the `dApp` in the wallet is illustrated [here](https://dev-docs.ont.io/#/docs-cn/dApp-Integration/01-DAppDocking-Wallet-Opens-DApp).

To ensure that the requirement for `dApps` to be accessible on both the browser and the mobile version, here we provide examples that involve using `dAPI` in three different scenarios. You can refer to:

* **Mobile version** `dAPI` **implementation -** [_dAPI for mobile_](https://github.com/ontio-cyano/cyano-bridge)\_\_
* **Chrome plugin wallet** `dAPI` **implementation -** [_dAPI for chrome_](https://github.com/ontio/ontology-dapi)\_\_
* **Example** `dAPI` **code compatible with both the Chrome plugin and the mobile version -** [_dAPI-universal_](https://github.com/ontio-cyano/dapi-universal)\_\_

Here is a step by step guide to assist developers with the integration process:

### 1. Development environment set-up and Installation

Before starting with the actual development process, do ensure that the following tools are installed and set-up on your local machine.

* _**Node.js v6+  \(LTS with npm\) -**_ [Download link](https://nodejs.org/en/download/)
* _**Google Chrome -**_ [Download link](https://www.google.com/chrome/)
* _**Cyano Wallet -**_ [Download link](https://chrome.google.com/webstore/detail/ontology-web-wallet/dkdedlpgdmmkkfjabffeganieamfklkm)
* _**Git -**_ [Download link](https://git-scm.com/downloads)

Next, we can install Ontology's `dAPI`. While building `dApps`, this `dAPI` serves as one of the core APIs that allow us to communicate with the chain. The source code can be downloaded [here](https://github.com/ontio/ontology-dapi). To carry out the installation using `npm`, use the following shell command:

```bash
npm install ontology-dapi
```

### 2. Creating a dAPI instance

Creating a `dAPI` instance involves importing and registering the client-side, as such:

```javascript
import { client } from 'ontology-dapi';
client.registerClient({});
```

### 3. Deploying dAPI methods

Once a `dAPI` instance is created successfully, `dAPI` methods can be used in a given `dApp`.

