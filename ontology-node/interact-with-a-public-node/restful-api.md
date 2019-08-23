# RESTful API



* Introduction
* [RESTful API](doc:restful-api) 
* Error Code

## Overview

This document describes the RESTful API format for the HTTP/HTTPS used in Ontology.

### Response parameters

| Field | Type | Description |
| :--- | :--- | :--- |
| Action | string | action name |
| Desc | string | description |
| Error | int64 | error code |
| Result | object | execute result |
| Version | string | version information |

## Restful API List

| Method | URL | Description |
| :--- | :--- | :--- |
| get\_conn\_count | GET /api/v1/node/connectioncount | return the number of node connect to the network |
| get\_blk\_txs\_by\_height | GET /api/v1/block/transactions/height/:height | return whole transaction hash of the block |
| get\_blk\_by\_height | GET /api/v1/block/details/height/:height?raw=0 | return block info of the height |
| get\_blk\_by\_hash | GET /api/v1/block/details/hash/:hash?raw=1 | return block info of the block hash |
| get\_blk\_height | GET /api/v1/block/height | return current block height of main net |
| get\_blk\_hash | GET /api/v1/block/hash/:height | return block hash of the height |
| get\_tx | GET /api/v1/transaction/:hash | return transaction info by transaction hash |
| get\_storage | GET /api/v1/storage/:hash/:key | return the stored value according to the contract address hash and stored key |
| get\_balance | GET /api/v1/balance/:addr | return balance of the account address |
| get\_contract\_state | GET /api/v1/contract/:hash | return contract state according to the contract address hash |
| get\_sc\_event\_by\_height | GET /api/v1/smartcode/event/transactions/:height | return the smartcode event in the block at the height |
| get\_smtcode\_evts | GET /api/v1/smartcode/event/txhash/:hash | return smartcode event by transaction hash |
| get\_blk\_hgt\_by\_txhash | GET /api/v1/block/height/txhash/:hash | return the block height where transaction at |
| get\_merkle\_proof | GET /api/v1/merkleproof/:hash | return merkle proof of the transaction |
| get\_gasprice | GET /api/v1/gasprice | return gas price |
| get\_allowance | GET /api/v1/allowance/:asset/:from/:to | return the allowance from transfer-from accout to transfer-to account |
| get\_unboundong | GET /api/v1/unboundong/:addr | return the number of unbound ong of given address |
| get\_mempooltxcount | GET /api/v1/mempool/txcount | return the number of transaction locate in memory |
| get\_mempooltxstate | GET /api/v1/mempool/txstate/:hash | return the state of transaction locate in memory |
| get\_version | GET /api/v1/version | return the version of ontology |
| post\_raw\_tx | post /api/v1/transaction?preExec=0 | send transaction to ontology network |
| get\_networkid | GET /api/v1/networkid | return the networkid |
| get\_grantong | GET /api/v1/grantong/:addr | get grant ong |

## Sample  code

#### 1 get\_conn\_count

Get the number of connected node.

**Example**:

{% api-method method="get" host="/api/v1/node/connectioncount" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
Get the number of connected nodes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "Action": "getconnectioncount",
    "Desc": "SUCCESS",
    "Error": 0,
    "Result": 0,
    "Version": "1.0.0"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

