# WebSocket API



* Introduction
* Websocket Api List
* Error Code

## Overview

This document describes the Websocket API format for the ws/wss used in Ontology.

### Response parameters

| Field | Type | Description |
| :--- | :--- | :--- |
| Action | string | action name |
| Desc | string | description |
| Error | int64 | error code |
| Result | object | execute result |
| Version | string | version information |
| Id | int64 | req Id |

## WebSocket API List

| Method | Parameter | Description |
| :--- | :--- | :--- |
| heartbeat |  | send heart beat info |
| subscribe | \[ConstractsFilter\],\[SubscribeEvent\],\[SubscribeJsonBlock\],\[SubscribeRawBlock\],\[SubscribeBlockTxHashs\] | subscribe service |
| getconnectioncount |  | get the current number of connections for the node |
| getblocktxsbyheight | height | return all transaction hash contained in the block corresponding to this height |
| getblockbyheight | height | return block details based on block height |
| getblockbyhash | hash | return block details based on block hash |
| getblockheight |  | return the current block height |
| getblockhash | height | return block hash based on block height |
| gettransaction | hash,\[raw\] | get transaction details based on transaction hash |
| sendrawtransaction | data,\[PreExec\] | Send transaction. Set PreExec=1 if want prepare exec smart contract |
| getstorage | hash,key | return the stored value according to the contract script hashes and stored key |
| getbalance | address | return the balance of base58 account address |
| getcontract | hash | According to the contract address hash, query the contract information |
| getsmartcodeeventbyheight | height | return smart contract event list by height |
| getsmartcodeeventbyhash | hash | return contract event by transaction hash |
| getblockheightbytxhash | hash | return block height of transaction hash |
| getmerkleproof | hash | return merkle proof of given hash |
| getsessioncount |  | return gas price |
| getgasprice |  | return the state of transaction locate in memory |
| getallowance | asset, from, to | return the allowance from transfer-from accout to transfer-to account |
| getunboundong | address | get unbound ong of this address |
| getmempooltxstate | hash | query the transaction state in the memory pool |
| getmempooltxcount |  | query the transaction count in the memory pool |
| getversion |  | get the version information of the node |
| getnetworkid |  | get the network id |
| getgrantong |  | get grant ong |

## Sample code

#### 1. heartbeat

If don't send heartbeat, the session expire after 5min.

{% code-tabs %}
{% code-tabs-item title="REQUEST" %}
```text
{
    "Action": "heartbeat",
    "Id":12345, //optional
    "Version": "1.0.0"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="RESPONSE" %}
```
{
    "Action": "heartbeat",
    "Desc": "SUCCESS",
    "Error": 0,
    "Result": {
        "SubscribeEvent":false,
        "SubscribeJsonBlock":false,
        "SubscribeRawBlock":false,
        "SubscribeBlockTxHashs":false
    }
    "Version": "1.0.0"
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

