---
description: Synchronizing your local database with the data on the chain
---

# Data Synchronization

Every time a `dApp` needs to fetch the data stored on the chain \(i.e., transaction records and such\), it can do so by querying the public **Explorer API /add link/.** But this would only be feasible for the `dApps` that have a low query rate, or execute queries at a lower frequency. 

`dApps` with higher query requirements both in terms of number and frequency cannot work at optimum efficiency when using the Explorer interface. Therefore, to target this specific issue, Ontology introduced a new method which allows the application's local database to synchronize its data with the data on the chain.

{% hint style="warning" %}
Synchronizing the local database with the chain is an option, and not a requirement for `dApp` development. Developers are advised to analyze the specific requirements for their respective applications to make this judgement.
{% endhint %}

## Connecting to Ontology's Nodes

Connecting to Ontology's nodes is the first step of data synchronization process. This can be performed in two different ways-

### 1. Connecting to Ontology's Consensus nodes

Generally speaking, personally deploying and running a node is a very tedious task for developers. And that is why Ontology made Polaris tes



