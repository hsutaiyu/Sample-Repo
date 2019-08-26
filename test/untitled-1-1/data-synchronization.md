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

Generally speaking, personally deploying and running a node is a very tedious task for developers. And that is why Ontology made `Polaris` test net and main net nodes available for developers to employ. It supports `RPC`, `Restful`, and `WebSocket` invocation, and use default ports.

The Polaris test net nodes are-

* [http://polaris1.ont.io](http://polaris1.ont.io)
* [http://polaris2.ont.io](http://polaris2.ont.io)
* [http://polaris3.ont.io](http://polaris3.ont.io)
* [http://polaris4.ont.io](http://polaris1.ont.io)
* [http://polaris5.ont.io](http://polaris5.ont.io)

and the main net nodes are-

* [http://dappnode1.ont.io](http://dappnode1.ont.io)
* [http://dappnode2.ont.io](http://dappnode2.ont.io)
* [http://dappnode3.ont.io](http://dappnode3.ont.io)
* [http://dappnode4.ont.io](http://dappnode4.ont.io)

{% hint style="success" %}
**10334** port of the first nodes of the Polaris test net net and the main net support HTTPS
{% endhint %}

### 2. Running your own node

Depending on the architecture of the `dApp` the developer may choose to personally run a synchronization node. Fore more details and a quick walkthrough, refer to - 

{% page-ref page="../../ontology-node/untitled/node-deployment.md" %}

## Running the Synchronization Sequence

What synchronization basically does is all the data that is stored on the chain, say all the block, transaction and contract event related data, is imported to a local database that the `dApp` has direct access to, thereby increasing the efficiency with which the app can query it. 

Ontology's Explorer is a model synchronization program. The user may selectively synchronize the data that serves their purpose. For e.g., data related to the events pertaining to a smart contract that you deployed.

### 1. Synchronizing with all the blocks on the chain

There are `dApps` that needs to synchronize the information from all the blocks on the chain, a typical case of which would be Ontology's `Explorer`. Developers developing `dApps` with needs analogous to those of Explorer may find [this](https://github.com/ontio/ontology-explorer/tree/master/back-end-projects/OntSynHandler) helpful.

On the basis of the height of the given block,  the **`getblk_by_height`** interface returns the following `JSON` response.

```javascript
http://polaris1.ont.io:20334/api/v1/block/details/height/909220

{
    "Action": "getblockbyheight",
    "Desc": "SUCCESS",
    "Error": 0,
    "Result": {
        "Hash": "02f723a83eae05238481bc8b7d315cbbcd4326ccb53df6e1de35b19c496868ee",
        "Size": 1392,
        "Header": {
            "Version": 0,
            "PrevBlockHash": "b0243bd78e7368c8bed33a9e66b4a8c0a2f98fbcf18457a018f027b69ab1f7fc",
            "TransactionsRoot": "7f89aaf1ca48a8cff46493f1ca75f91fabe1ec14b8acd3ffd32acd722d398b4e",
            "BlockRoot": "e6440680fc91be58c5d41298c992cb6cd04c365a00bf6dce216ce085ce0e75cd",
            "Timestamp": 1551427384,
            "Height": 909220,
            "ConsensusData": 12174009838538082583,
            "ConsensusPayload": "7b226c6561646572223a312c227672665f76616c7565223a224249526839547a4f4e526e71766444566b565a6753624e6e533871336465344b4b59786a52686174713864394b6d3974316f7279654f426b727170502f4b6f4474674135647061492f313649536c4b643556784e4d444d3d222c227672665f70726f6f66223a222f6e7a554a54766f7959676d594a544570574938326958454b497a6c7247707870753067767239784a6231784c646c344442435831796d7372703941796f495256372f35626f2f4c572b2b36336937665553747378513d3d222c226c6173745f636f6e6669675f626c6f636b5f6e756d223a3930383432342c226e65775f636861696e5f636f6e666967223a6e756c6c7d",
            "NextBookkeeper": "AFmseVrdL9f9oyCzZefL9tG6UbvhPbdYzM",
            "Bookkeepers": ["037c9e6c6a446b6b296f89b722cbf686b81e0a122444ef05f0f87096777663284b", "03aa4d52b200fd91ca12deff46505c4608a0f66d28d9ae68a342c8a8c1266de0f9", "0205bc592aa9121428c4144fcd669ece1fa73fee440616c75624967f83fb881050", "030a34dcb075d144df1f65757b85acaf053395bb47b019970607d2d1cdd222525c", "020cc76feb375d6ea8ec9ff653bab18b6bbc815610cecc76e702b43d356f885835", "03dff4c63267ae5e23da44ace1bc47d0da1eb8d36fd71181dcccf0e872cb7b31fa"],
            "SigData": ["ded9f22792bfc4aa1e471fe05cfc68af2cd5204fd1664f3151648910f51cc531f8dc9c301ee450538e84ffa8a77b5c8141e37caab4917eb7b8c6eb11e8e1b387", "ac5b1710b50d1d35b7948d2e19a22e5f7eecbe210f09551275ca273d09ea15e1aa5198d052ef913cf51b3855955f0f89caf174ca4ffac4451d27b29dc64626e7", "121d213cf49f7c7a706e9098d2ed9ae53ead4fe41774fdccd7186fd47fffa13f60dea875794fe9bbcf5fd729a1294cc835b34ef42ae8544425b15bedca0d8e93", "8053c1fbf81f3d3c01925ad3160dec9c4751203da9a31c22448de4aa18c38d07f99e0cbb7066bb83de6e7d46720184e541bcad8e9fdd2ec18cd8cbd83f0c335c", "ffc94ae16e0ff54a922f970b3226b5e2267a1b783ff990799f536dd3f0713782c9e43d372fcd3b4596f922a222db4e3bf3fe2b84e62c3ef580ff02d46491a61a", "cf52208439275256dfe3f97af4fab5a1b6c69661d5b885f6623337a4dfc729cb6b425fe8e009fccb115e7b4626f4176806ffd323a96d4aa0866a0459cf02917a"],
            "Hash": "02f723a83eae05238481bc8b7d315cbbcd4326ccb53df6e1de35b19c496868ee"
        },
        "Transactions": [{
            "Version": 0,
            "Nonce": 1551427383,
            "GasPrice": 500,
            "GasLimit": 20000000,
            "Payer": "Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn",
            "TxType": 209,
            "Payload": {
                "Code": "016414aa57ed4be4a318fb4b88b6a25d662f7e073743aa14feec06b79ed299ea06fcb94abac41aaf3ead765853c15a14feec06b79ed299ea06fcb94abac41aaf3ead76581446b1a18af6b7c9f8a4602f9f73eeb3030f0c29b753c152c151c10e7472616e736665725f6d756c746967bed9a5a68557381d0598cfcbfb16c03334a791ca"
            },
            "Attributes": [],
            "Sigs": [{
                "PubKeys": ["02e8e84be09b87985e7f9dfa74298f6bb7f70f85515afca7e041fe964334e4b6c1"],
                "M": 1,
                "SigData": ["dd0edcbb49e77bfec7fb5dbaaeafcb309dcd2b3db940dc27a33f5738872bd25684fcbd1da140d7ec483fa2eedb9e0c520619076e45e5f43383eeef55ca36d759"]
            }, {
                "PubKeys": ["03d0fdb54acba3f81db3a6e16fa02e7ea3678bd205eb4ed2f1cfa8ab5e5d45633e"],
                "M": 1,
                "SigData": ["df6c95816a56eab350800be3ccc3a9a7794b565a47b49f53b6351a19c5e1dd8d980d32a04a97f8e933a11683b7e1fcc50fd8f91695ab0189468a7c0a5a518156"]
            }],
            "Hash": "7f89aaf1ca48a8cff46493f1ca75f91fabe1ec14b8acd3ffd32acd722d398b4e",
            "Height": 0
        }]
    },
    "Version": "1.0.0"
}
```

### 2. Synchronize specific contract related Events

Most `dApps` only need to synchronize the `events` that are generated by their own contracts. This suffices for any functionalities that `dApp` may be implementing, and so there is no need to fetch and store all the data stored in all the different blocks.

The code to synchronize the data will always be application specific, because it would also have to adhere to the logic of the application. But here's an example of how a contract specific synchronization method would look like:

* The developer defines the argument set for `Notify`

```python
Notify(["param1", "param2", "param3"])
```

* When querying a smart contract event using the block height, the reply that the `getSmartCodeEvent` interface sends would look like:

```javascript
http://polaris1.ont.io:20334/api/v1/smartcode/event/transactions/909220

{
    "Action": "getsmartcodeeventbyheight",
    "Desc": "SUCCESS",
    "Error": 0,
    "Result": [{
        "TxHash": "7f89aaf1ca48a8cff46493f1ca75f91fabe1ec14b8acd3ffd32acd722d398b4e",
        "State": 1,
        "GasConsumed": 10000000,
        "Notify": [{
            "ContractAddress": "ca91a73433c016fbcbcf98051d385785a6a5d9be",
            "States": ["7472616e736665725f6d756c7469", [
                ["46b1a18af6b7c9f8a4602f9f73eeb3030f0c29b7", "feec06b79ed299ea06fcb94abac41aaf3ead7658", "0a"],
                ["feec06b79ed299ea06fcb94abac41aaf3ead7658", "aa57ed4be4a318fb4b88b6a25d662f7e073743aa", "64"]
            ]]
        }, {
            "ContractAddress": "0200000000000000000000000000000000000000",
            "States": ["transfer", "Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn", "AFmseVrdL9f9oyCzZefL9tG6UbviEH9ugK", 10000000]
        }]
    }],
    "Version": "1.0.0"
}
```

* The composition of the `ExecuteNotify` data structure is

```go
type ExecuteNotify struct {
    TxHash      common.Uint256   //Transcation hash
    State       byte             //1 signifies that the transaction was successful, 0 signifies failure
    GasConsumed uint64
    Notify      []*NotifyEventInfo
}
```

* The composition of `NotifyEventInfo` data structure is

```go
type NotifyEventInfo struct {
    ContractAddress common.Address  //Address of the smart contract
    States          interface{}     //The message to be notified
}
```

* The method that monitors for special or specific contract events could look something like:

```java
public void run() {

    try{

        while (true) {
            //Fetch the current block height
            int remoteBlockHieght = getRemoteBlockHeight();
            logger.info("######remote blockheight:{}", remoteBlockHieght);
            //Find out the height of synchronized blocks in the database
            int dbBlockHeight = blkHeightMapper.selectDBHeight();
            logger.info("######db blockheight:{}", dbBlockHeight);
            dbBlockHeight = dbBlockHeight +1;
            //If the synchronized block height exceeds, or is equal to that of
            //the newest block added, wait for the next block to be created, then sync
            if (dbBlockHeight >= remoteBlockHieght) {
                //TODO
            }
            //For each block, determine all the corresponding events, an event is a JSONArray object
            //The data type of every element is ExecuteNotify
            Object event = sdk.getConnect().getSmartCodeEvent(dbBlockHeight);
            if (event != null) {
              for(Object obj : (JSONArray)event){
                  //Filter successful transactions
                  if (obj.get("State") ==1) {
                    for(Object notify: obj.get("Notify")) {
                        //Filter the events that we were listening for
                        if(notify.getString("ContractAddress") == contractAddress) {
                             //TODO
                        }
                    }
                  }
              }
            }
            //Update the block height in the database
            blkHeightMapper.update(dbBlockHeight);

        }
    }catch (Exception e) {
        logger.error("Exception occured，Synchronization thread can't work, error ...", e);
    }

}
```

