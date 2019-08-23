# RPC API



* Introduction
* Rpc Api List
* Error Code

## **Overview**

This document provides the remote process call \(RPC\) specifications on Ontology.

Here are some description of parameters used in RPC:

### **Request parameter**

| Field | Type | Description |
| :--- | :--- | :--- |
| jsonrpc | string | jsonrpc version |
| method | string | method name |
| params | string | method required parameters |
| id | int | any value |

### **Response parameter**

| Field | Type | Description |
| :--- | :--- | :--- |
| desc | string | response description |
| error | int64 | error code |
| jsonrpc | string | jsonrpc version |
| id | int | any value |
| result | object | program execution result |

{% hint style="info" %}
The type of result varies with the request.
{% endhint %}

#### **Block field**

| Field | Type | Description |
| :--- | :--- | :--- |
| Header | \*Header |  |
| Transactions | \[\]\*Transaction |  |
| hash | \*Uint256 |  |

#### **Header field**

| Field | Type | Description |
| :--- | :--- | :--- |
| Version | uint32 | version number |
| PrevBlockHash | Uint256 | The hash of the previous block |
| TransactionsRoot | Uint256 | The root of the Merkle tree for all transactions in this block |
| BlockRoot | Uint256 | blockroot |
| Timestamp | int | block timestamp,uinix timestamp |
| Height | int | block height |
| ConsensusData | uint64 |  |
| NextBookkeeper | Address | bookkeeper of the next block |
| Bookkeepers | \[\]\*crypto.PubKey |  |
| SigData | \[\]\[\]byte |  |
| Hash | Uint256 | Script to verify the block |

#### **Transaction field**

| Field | Type | Description |
| :--- | :--- | :--- |
| Version | byte | version number |
| TxType | TransactionType | transaction type |
| Payload | Payload | payload |
| Nonce | uint32 | random number |
| Attributes | \[\]\*TxAttribute |  |
| Fee | \[\]\*Fee | transaction fees |
| NetworkFee | Fixed64 | network fees |
| Sigs | \[\]\*Sig | signature array |
| Hash | \*Uint256 | transaction hash |

## **RPC API list**

| Method | Parameters | Description | Note |
| :--- | :--- | :--- | :--- |
| getbestblockhash |  | get the hash of the highest height block in the main chain |  |
| getblock | height or blockhash,\[verbose\] | get block by block height or block hash | verbose can be 0 or 1,response is different |
| getblockcount |  | get the number of blocks |  |
| getblockhash | height | get block hash by block height |  |
| getconnectioncount |  | get the current number of connections for the node |  |
| getrawtransaction | transactionhash | Returns the corresponding transaction information based on the specified hash value. |  |
| sendrawtransaction | hex,preExec | Broadcast transaction. | Serialized signed transactions constructed in the program into hexadecimal strings |
| getstorage | script\_hash, key | Returns the stored value according to the contract address hash and stored key. |  |
| getversion |  | Get the version information of the node |  |
| getcontractstate | script\_hash,\[verbose\] | According to the contract address hash, query the contract information. |  |
| getmempooltxcount |  | Query the transaction count in the memory pool. |  |
| getmempooltxstate | tx\_hash | Query the transaction state in the memory pool. |  |
| getsmartcodeevent |  | Get smartcode event |  |
| getblockheightbytxhash | tx\_hash | get blockheight of transaction hash |  |
| getbalance | address | return balance of base58 account address. |  |
| getmerkleproof | tx\_hash | return merkle proof |  |
| getgasprice |  | return gasprice |  |
| getallowance | asset, from, to | return the allowance from transfer-from account to transfer-to account |  |
| getunboundong | address | return unbound ong |  |
| getblocktxsbyheight | height | return transaction hashes |  |
| getnetworkid |  | Get the network id |  |
| getgrantong |  | Get grant ong |  |

## Sample code

**1. getbestblockhash**

Get the hash of the highest height block on the Ontology main chain.

**Example**

{% api-method method="get" host="" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "desc":"SUCCESS",
  "error":0,
  "jsonrpc": "2.0",
  "id": 1,
  "result": "773dd2dae4a9c9275290f89b56e67d7363ea4826dfd4fc13cc01cf73a44b0d0e"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

