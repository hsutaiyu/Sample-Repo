# Ontology Oracle

```text
  OEP: 34
  Title: Ontology Oracle Standard
  Author: zhangmh<siovanus@126.com>
  Type: Standard
  Status: Accepted
  Created: 2018-12-26
```

## Table of Contents

* * [Abstract]()
  * [Motivation]()
  * [Specification]()
    * [Architecture]()
      * [Simple Oracle Contract]()
      * [Oracle Contract Platform]()
    * [Method]()
      * [CreateOracleRequest]()
      * [SetOracleOutcome]()
      * [GetOracleOutcome]()
      * [RegisterOperator]()
    * [Notify]()
      * [CreateOracleRequest]()
      * [SetOracleOutcome]()
  * [Oracle Request Format]()
  * [Contract Implementation]()
    * * [Example implementations are available at]()
  * [Operator Implementation]()
    * * [Example implementations are available at]()

## Abstract

The OEP-34 Proposal is a standard interface for Ontology Oracle, this standard allows you to get outside world data via http request in smart contracts.

## Motivation

With the development of smart contract DApp, the requirement of using outside world data is more and more intense. For example, a flight insurance smart contract depends on if the flight delayed. But for blockchain, it's hard to get outside world data in smart contracts.

Ontology Oracle play a role as data carrier and can solve this problem. It makes it possible to obtain outside world data in smart contracts.

The OEP-34 proposal is the standard specify how the oracle works.

## Specification

### Architecture

#### Simple Oracle Contract

Simple oracle contract only have single admin operator account, which used to sign the data and transaction. You can also run several operators with same admin operator account to guarantee operator's availability.

Admin operator account is defined in simple oracle contract. Oracle fee will be sent to admin and only admin can set oracle outcome. Admin is responsible for the result it provide.

Simple oracle contract is easy to use for the organization who want to provide data service and want to deploy oracle contract.

#### Oracle Contract Platform

Not all data service provider want to deploy an oracle contract. They can register their operator account and data method in some "oracle contract platform". Then listen to oracle request in oracle contract platform, obtain and serialize data, sign result and send it to oracle contract platform. Platform verify the signature and put result in contract storage. Oracle fee will be sent to the operator account whose method users invoke. Operator account is responsible for the result it provide.

Oracle contract platform is designed for someone who want to run a platform that operators can join and provide service without deploying oracle contract.

### Method

#### CreateOracleRequest

```text
public static bool CreateOracleRequest(string request, byte[] address)
```

 Create oracle request, accepts two params.

`request` string of request body, defines how to get the data and how to serilize the data.

`address` the caller's address, will verify it's signature and pay oracle fee.

#### SetOracleOutcome

```text
public static bool SetOracleOutcome(byte[] txHash, byte[] result)
```

 Set result of the oracle request, must be invoked by oracle contract admin, accepts two params.

`txHash` the txHash of oracle request

`result` result of the oracle request

#### GetOracleOutcome

```text
public static byte[] GetOracleOutcome(byte[] txHash)
```

 Returns result according to the txHash of the oracle request, accepts one param.

`txHash` the txHash of oracle request

#### RegisterOperator

```text
public static bool RegisterOperator(string method, byte[] pubKey, byte[] address)
```

 Register an operator to oracle contact, accepts three params. Only available in oracle contract platform.

`method` the method that the operator provide, users can use this method in request to get data via this operator

`pubKey` the public key of operator wallet

`address` the address of operator wallet

### Notify

#### CreateOracleRequest

```text
Notify(["createOracleRequest", request, address])
```

 MUST be invoked in CreateOracleRequest function.

#### SetOracleOutcome

```text
Notify(["setOracleOutcome", txHash, status, errMessage])
```

 MUST be invoked in SetOracleOutcome function.

## Oracle Request Format

Oracle request must satisfy OEP-34 format so that operator can recognize, for example:

```text
req = """{
		"scheduler":{
			"type": "runAfter",
			"params": "2018-06-15 08:37:18"
		},
		"tasks":[
			{
			  "type": "httpGet",
			  "params": {
				"url": "https://data.nba.net/prod/v2/20181129/scoreboard.json"
			  }
			},
			{
				"type": "jsonParse",
				"params":
				{
					"data":
					[
						{
							"type": "Array",
							"path": ["games"],
							"sub_type":
							[
								{
									"type": "Struct",
									"sub_type":
									[
										{
											"type": "String",
											"path": ["gameId"]
										},
										{
											"type": "String",
											"path": ["vTeam", "teamId"]
										},
										{
											"type": "String",
											"path": ["vTeam", "score"]
										},
										{
											"type": "String",
											"path": ["hTeam", "teamId"]
										},
										{
											"type": "String",
											"path": ["hTeam", "score"]
										}
									]
								}
							]
						}
					]
				}
			}
		]
	}"""
```

More oracle request examples see: [README](https://github.com/ontio/ontology-oracle)

## Contract Implementation

#### Example implementations are available at

OEP-34 Python Oracle Contract Template: [Python Template](https://github.com/ontio/ontology-oracle/tree/master/smartcontract)

## Operator Implementation

#### Example implementations are available at

Operator listen request of oracle contact, fetch the data via http get/post method, and serialize the data via ontology neovm standard, then send signed result to oracle contract.

OEP-34 Golang Operator Template: [Operator Template](https://github.com/ontio/ontology-oracle)

