---
description: Smart Contract development using Ontology's dAPI
---

# Using the dAPI

The `dAPI` supports browser \(currently limited to Google Chrome\) and mobile based development \(implemented using `Cyano` wallet that employs `dAPI` interface\).

The mobile version of `dAPI` provides a limited number of the more significant interfaces only. The interfaces that query block transactions, or other interfaces that perform similar functions can directly invoke the `explorer` API interface. The `dAPI` interface set of the `chrome` plug-in is overall more comprehensive.

{% hint style="warning" %}
The code written in the two different environments is not mutually interchangeable currently. For compatibility related information, please refer: [dapi-universal](https://github.com/ontio-cyano/dapi-universal)
{% endhint %}

This guides aims at providing a surface level introduction for some of the more commonly used interfaces- login, signature data, contract query, and contract invocation.

{% hint style="info" %}
Note: The data returned by the dAPI interface is referred to as "Promise"
{% endhint %}

## Configuration Process

![dAPI Installation Flowchart](../../.gitbook/assets/dapi-intro.svg)

### 1. Installing dAPI

The first step is to install and set-up `dAPI`. 

{% hint style="info" %}
Ensure that Node.js is configured properly. The installation process uses `npm` commands.
{% endhint %}

#### Chrome version-

```bash
npm install ontology-dapi
```

#### Mobile version-

```bash
npm install cyanobridge
```

### 2. Initialization

A contract must be initialized before it is invoked.

#### Chrome version

```javascript
import {client} from 'ontology-dapi'
client.registerClient({})
```

#### Mobile version

```javascript
import {client} from 'cyanobridge'
client.registerClient();
```

### 3. Login

There are two ways to implement the login mechanism in a `dApp`:

* Use the `dAPI` to directly fetch the user's account address or `ONT ID`. If the information can be retrieved successfully, it indicates the logged in state with respect to the `dApp`.
* The dApp backend generates a string and sends it to the frontend, and the frontend invokes the dAPI requesting it to assign a signature to it, and then returning it to the backend. If the backend can successfully verify this signature, the user can be considred to have logged in successfully. Next, the backend can issue `access tokens` to the user. This depends on the sevice logic of the `dApp`.

