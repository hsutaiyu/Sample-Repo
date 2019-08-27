---
description: Ontology Python SDK API Reference
---

# Python SDK

## Introduction <a id="introduction"></a>

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/9078ef6584424280b8d6b75556976f94)](https://www.codacy.com/app/NashMiao/ontology-python-sdk?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=ontio/ontology-python-sdk/&amp;utm_campaign=Badge_Grade) [![Codacy Badge](https://api.codacy.com/project/badge/Coverage/9078ef6584424280b8d6b75556976f94)](https://www.codacy.com/app/NashMiao/ontology-python-sdk?utm_source=github.com&utm_medium=referral&utm_content=ontio/ontology-python-sdk/&utm_campaign=Badge_Coverage) [![Build Status](https://travis-ci.com/ontio/ontology-python-sdk.svg?branch=master)](https://travis-ci.com/ontio/ontology-python-sdk) [![pypi-w](https://img.shields.io/pypi/wheel/ontology-python-sdk.svg)](https://pypi.org/project/ontology-python-sdk/) [![pypi-pyversions](https://img.shields.io/pypi/pyversions/ontology-python-sdk.svg)](https://pypi.org/project/ontology-python-sdk/) [![pypi-v](https://img.shields.io/pypi/v/ontology-python-sdk.svg)](https://pypi.org/project/ontology-python-sdk/) [![Downloads](https://pepy.tech/badge/ontology-python-sdk)](https://pepy.tech/project/ontology-python-sdk)

The ontology-python-sdk is the official Python implementation of the Ontology SDK which contain specific functionality for the Ontology ecosystem.

## Getting Started <a id="getting-started"></a>

```text
pip3 install ontology-python-sdk
```

Installation requires a `Python 3.6` or later environment.

## Network <a id="network"></a>

This module contains functions help you to interact with an Ontology nodes by RPC, RESTful or WebSocket.

### RPC <a id="rpc"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
sdk.rpc.connect_to_main_net()
sdk.rpc.connect_to_localhost()
sdk.rpc.set_address('http://localhost:20336')
```

You can interact with Ontology network by JSON-RPC in synchronously.

* connect to polaris test net.
* connect to main net.
* connect to the node in localhost.
* connect to the user-defined node.

#### get version <a id="get-version"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = sdk.rpc.get_version()
```

Gets the current node version synchronously.

#### get networkid <a id="get-networkid"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = sdk.rpc.get_network_id()
```

Gets the current network ID synchronously.

#### get merkle proof <a id="get-merkle-proof"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = sdk.rpc.get_merkle_proof(tx_hash)
```

Gets merkle proof of specific transaction synchronously.

![Merkle tree](../../.gitbook/assets/merkle-tree.png)

### RESTful <a id="restful"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.restful.connect_to_test_net()
sdk.restful.connect_to_main_net()
sdk.restful.connect_to_localhost()
sdk.restful.set_address('http://localhost:20334')
```

You can interact with Ontology network by JSON-RPC in synchronously.

* connect to polaris test net.
* connect to main net.
* connect to the node in localhost.
* connect to the user-defined node.

#### get version <a id="get-version"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.restful.connect_to_test_net()
version = sdk.restful.get_version()
```

Gets the current node version synchronously.

#### get networkid <a id="get-networkid"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = sdk.restful.get_network_id()
```

Gets the current network ID synchronously.

#### get merkle proof <a id="get-merkle-proof"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.restful.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = sdk.restful.get_merkle_proof(tx_hash)
```

Gets merkle proof of specific transaction synchronously.

![Merkle tree](../../.gitbook/assets/merkle-tree.png)

### WebSocket <a id="websocket"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.websocket.connect_to_test_net()
sdk.websocket.connect_to_main_net()
sdk.websocket.connect_to_localhost()
sdk.rpc.set_address('http://localhost:20335')
```

You can interact with Ontology network by `WebSocket`.

* connect to polaris test net.
* connect to main net.
* connect to the node in localhost.
* connect to the user-defined node.

#### get version <a id="get-version"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.websocket.connect_to_test_net()
version = await sdk.websocket.get_version()
```

Gets the current node version asynchronously.

#### get networkid <a id="get-networkid"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = await sdk.websocket.get_network_id()
```

Gets the current network ID asynchronously.

#### get merkle proof <a id="get-merkle-proof"></a>

```text

```

Gets merkle proof of specific transaction asynchronously.

![Merkle tree](../../.gitbook/assets/merkle-tree.png)

### Async RPC <a id="async-rpc"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_rpc.connect_to_test_net()
sdk.aio_rpc.connect_to_main_net()
sdk.aio_rpc.connect_to_localhost()
```

You can interact with Ontology network by JSON-RPC in asynchronously.

* connect to polaris test net.
* connect to main net.
* connect to the node in localhost.
* connect to the user-defined node.

#### get version <a id="get-version"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_rpc.connect_to_test_net()
version = await sdk.aio_rpc.get_version()
```

Gets the current node version asynchronously.

#### get networkid <a id="get-networkid"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = await sdk.aio_rpc.get_network_id()
```

Gets the current network ID asynchronously.

#### get merkle proof <a id="get-merkle-proof"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_rpc.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = await sdk.aio_rpc.get_merkle_proof(tx_hash)
```

Gets merkle proof of specific transaction asynchronously.

![Merkle tree](../../.gitbook/assets/merkle-tree.png)

### Async RESTful <a id="async-restful"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_restful.connect_to_test_net()
sdk.aio_restful.connect_to_main_net()
sdk.aio_restful.connect_to_localhost()
```

You can interact with Ontology network by RESTful in asynchronously.

* connect to polaris test net.
* connect to main net.
* connect to the node in localhost.
* connect to the user-defined node.

#### get version <a id="get-version"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_restful.connect_to_test_net()
version = await sdk.aio_restful.get_version()
```

#### get networkid <a id="get-networkid"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
version = await sdk.aio_restful.get_network_id()
```

Gets the current network ID asynchronously.

#### get merkle proof <a id="get-merkle-proof"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.aio_restful.connect_to_test_net()
tx_hash = '12943957b10643f04d89938925306fa342cec9d32925f5bd8e9ea7ce912d16d3'
merkle_proof = await sdk.aio_restful.get_merkle_proof(tx_hash)
```

Gets merkle proof of specific transaction asynchronously.

![Merkle tree](../../.gitbook/assets/merkle-tree.png)

## Account <a id="account"></a>

### get address <a id="get-address"></a>

```text
from ontology.utils import utils
from ontology.account.account import Account

private_key = utils.get_random_bytes(32).hex()
account = Account(private_key)
address = account.get_addres()

```

### export wif <a id="export-wif"></a>

```text
from ontology.utils import utils
from ontology.account.account import Account

private_key = utils.get_random_bytes(32).hex()
account = Account(private_key)
wif = account.export_wif()

```

## Identity <a id="identity"></a>

## Wallet Manager <a id="wallet-manager"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
wm = sdk.wallet_manager
```

This module contains functions to manage Ontology digital accounts and digital identity \(named ONT ID\) which based on W3c DID protocol specification.

### create wallet <a id="create-wallet"></a>

```text
from os import path
from ontology.sdk import Ontology

sdk = Ontology()
wallet_path = path.join(path.curdir, 'wallet.json')
sdk.wallet_manager.create_wallet_file(wallet_path)
```

This interface helps us to create a wallet's KeyStore file in specify path.

### open wallet <a id="open-wallet"></a>

```text
from os import path
from ontology.sdk import Ontology

sdk = Ontology()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager.open_wallet(wallet_path)
```

We can read wallet's KeyStore by using `open_wallet` interface, which will help us load KeyStore file in JSON format from disk into memory.

### create account <a id="create-account"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
acct = sdk.wallet_manager.create_account('password')
```

### create identity <a id="create-identity"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
identity = sdk.wallet_manager.create_identity('password')
```

### get account <a id="get-account"></a>

```text
from os import path
from ontology.sdk import Ontology

sdk = Ontology()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager(wallet_path)
acct = wallet.get_account_by_b58_address('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD', 'password')
```

### get identity <a id="get-identity"></a>

```text
from os import path
from ontology.sdk import Ontology

sdk = Ontology()
wallet_path = path.join(path.curdir, 'wallet.json')
wallet = sdk.wallet_manager(wallet_path)
identity = wallet_manager.get_identity_by_ont_id('did:ont:ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

## HD Wallet <a id="hd-wallet"></a>

### get master keys <a id="get-master-keys"></a>

```text
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
```

#### get root keys <a id="get-root-keys"></a>

```text
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
root_keys = HDPrivateKey.from_path(self.master_keys[0])
```

#### get private child key <a id="get-private-child-key"></a>

```text
from ontology.crypto.hd_private_key import HDPrivateKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')

root_keys = HDPrivateKey.from_path(master_keys[0])
for i in range(10):
  child_sks = HDPrivateKey.from_path(root_keys[-1], '{change}/{index}'.format(change=0, index=i))

```

#### get public child key <a id="get-public-child-key"></a>

```text
from ontology.crypto.hd_public_key import HDPublicKey

mnemonic = 'obscure worry home pass museum toss else accuse limb hover denial alpha'
master_keys = HDPrivateKey.master_key_from_mnemonic(mnemonic, 'password')
root_keys = HDPrivateKey.from_path(master_keys[0])

root_pk = root_keys[-1].public_key
for i in range(10):
  child_pks = HDPublicKey.from_path(root_pk, '{change}/{index}'.format(change=0, index=i))

```

## Native Contract <a id="native-contract"></a>

### ONT <a id="ont"></a>

```text
from os import path

from ontology.sdk import Ontology

sdk = Ontology()
ont = sdk.native_vm.ont()
```

This module contains functions to manage Ontology digital asset Ontology Token which based on Native Contract.

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_name = sdk.native_vm.ont().name()
```

Returns the name of the token synchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_symbol = sdk.native_vm.ont().symbol()
```

Returns the symbol of the token synchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
decimals = sdk.native_vm.ont().decimals()
```

Returns the number of decimals the token uses synchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
balance = sdk.native_vm.ont().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address synchronously.

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address synchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ont().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = sdk.native_vm.ont().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address.

### ONG <a id="ong"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ong = sdk.native_vm.ong()
```

This module contains functions to manage Ontology digital asset Ontology Gas which based on Native Contract.

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_name = sdk.native_vm.ong().name()
```

Returns the name of the token synchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_symbol = sdk.native_vm.ong().symbol()
```

Returns the symbol of the token synchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
decimals = sdk.native_vm.ong().decimals()
```

Returns the number of decimals the token uses synchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
balance = sdk.native_vm.ong().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address synchronously.

#### unbound <a id="unbound"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
unbound_ong = sdk.native_vm.ong().unbound(address)
```

Unbound ONG is an amount of ONG which has not been added to your claimable ONG balance yet \(since it only updates each time you make an ONT transaction in your wallet address\). When an ONT transaction is made in your address, the claimable ONG balance will update \(adding your unbound ONG amount to your claimable ONG amount\).

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ong().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address synchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ong().approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = sdk.native_vm.ong().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = sdk.native_vm.ong().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address.

### ONT ID <a id="ont-id"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ont_id = sdk.native_vm.ont_id()
```

#### get public keys <a id="get-public-keys"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ont_id = 'did:ont:APywVQ2UKBtitqqJQ9JrpNeY8VFAnrZXiR'
pub_keys = sdk.native_vm.ont_id().get_public_keys(ont_id)
```

### Async ONT <a id="async-ont"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ont = sdk.native_vm.aio_ont()
```

### Async ONG <a id="async-ong"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ong = sdk.native_vm.aio_ong()
```

### Async ONT ID <a id="async-ont-id"></a>

```text
from os import path

from ontology.sdk import Ontology

sdk = Ontology()
sdk.native_vm.aio_ont_id()
```

### Async ONT <a id="async-ont"></a>

```text
from os import path

from ontology.sdk import Ontology

sdk = Ontology()
ont = sdk.native_vm.aio_ont()
```

This module contains functions to manage Ontology digital asset Ontology Token which based on Native Contract.

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_name = await sdk.native_vm.aio_ont().name()
```

Returns the name of the token asynchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_symbol = await sdk.native_vm.aio_ont().symbol()
```

Returns the symbol of the token asynchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
decimals = await sdk.native_vm.aio_ont().decimals()
```

Returns the number of decimals the token uses asynchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
balance = await sdk.native_vm.aio_ont().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address asynchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ont().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await sdk.native_vm.aio_ont().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address.

### Async ONG <a id="async-ong"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
ong = sdk.native_vm.aio_ong()
```

This module contains functions to manage Ontology digital asset Ontology Gas which based on Native Contract.

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_name = await sdk.native_vm.aio_ong().name()
```

Returns the name of the token asynchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
token_symbol = await sdk.native_vm.aio_ong().symbol()
```

Returns the symbol of the token asynchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
decimals = await sdk.native_vm.aio_ong().decimals()
```

Returns the number of decimals the token uses asynchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
balance = await sdk.native_vm.aio_ong().balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

#### unbound <a id="unbound"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
sdk.rpc.connect_to_test_net()
address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
unbound_ong = await sdk.native_vm.aio_ong().unbound(address)
```

Unbound ONG is an amount of ONG which has not been added to your claimable ONG balance yet \(since it only updates each time you make an ONT transaction in your wallet address\). When an ONT transaction is made in your address, the claimable ONG balance will update \(adding your unbound ONG amount to your claimable ONG amount\).

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address asynchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await sdk.native_vm.aio_ong().allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await sdk.native_vm.aio_ong().transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address.

## NEO Contract <a id="neo-contract"></a>

### OEP-4 <a id="oep-4"></a>

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
token_name = oep4.name()
```

Returns the name of the token synchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
token_symbol = oep4.symbol()
```

Returns the symbol of the token synchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
decimals = oep4.decimals()
```

Returns the number of decimals the token uses synchronously.

#### total supply <a id="total-supply"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
supply = oep4.total_supply()
```

Returns the total token supply synchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
balance = oep4.balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address synchronously.

#### init <a id="init"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
founder = sdk.wallet_manager.create_account('password')
payer = sdk.wallet_manager.create_account('password')
tx_hash = oep4.init(founder, payer, 500, 20000)
```

Contract owner uses this interface to activate oep-4 token.

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = oep4.transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address synchronously.

#### transfer multi <a id="transfer-multi"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
transfer_list = [[from_address1, to_address, 1], [from_address2, to_address, 1]]
signers = [from_acct1, from_acct2]
tx_hash = oep4.transfer_multi(transfer_list, signers, payer, 500, 20000)
```

Transfers amount of token from from-account to to-account multiple times synchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = oep4.approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
owner = 'Af1n2cZHhMZumNqKgw9sfCNoTWu9de4NDn'
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = oep4.allowance(owner, spender)
```

Returns the amount which spender is still allowed to withdraw from owner.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.oep4(contract_address)
spender = sdk.wallet_manager.create_account('password')
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = oep4.transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address.

### OEP-5 <a id="oep-5"></a>

### OEP-8 <a id="oep-8"></a>

### Async OEP-4 <a id="async-oep-4"></a>

#### name <a id="name"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
token_name = await oep4.name()
```

Returns the name of the token asynchronously.

#### symbol <a id="symbol"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
token_symbol = await oep4.symbol()
```

Returns the symbol of the token asynchronously.

#### decimals <a id="decimals"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
decimals = await oep4.decimals()
```

Returns the number of decimals the token uses asynchronously.

#### total supply <a id="total-supply"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
supply = await oep4.total_supply()
```

Returns the total token supply asynchronously.

#### balance of <a id="balance-of"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
balance = await oep4.balance_of('ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD')
```

Returns the account balance of another account with owner address asynchronously.

#### init <a id="init"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
founder = sdk.wallet_manager.create_account('password')
payer = sdk.wallet_manager.create_account('password')
tx_hash = await oep4.init(founder, payer, 500, 20000)
```

Contract owner uses this interface to activate oep-4 token asynchronously.

#### transfer <a id="transfer"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
from_acct = sdk.wallet_manager.create_account('password')
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.transfer(from_acct, to_address, 10, from_acct, 500, 20000)
```

Transfers amount of tokens to to\_address asynchronously.

#### transfer multi <a id="transfer-multi"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
to_address = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
transfer_list = [[from_address1, to_address, 1], [from_address2, to_address, 1]]
signers = [from_acct1, from_acct2]
tx_hash = await oep4.transfer_multi(transfer_list, signers, payer, 500, 20000)
```

Transfers amount of token from from-account to to-account multiple times asynchronously.

#### approve <a id="approve"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.approve(owner, spender, 10, owner, 500, 20000)
```

Allows spender to withdraw from owner account multiple times asynchronously, up to the value amount.

#### allowance <a id="allowance"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = sdk.wallet_manager.create_account('password')
spender = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
tx_hash = await oep4.approve(owner, spender, 10, owner, 500, 20000)
```

Returns the amount which spender is still allowed to withdraw from owner asynchronously.

#### transfer from <a id="transfer-from"></a>

```text
from ontology.sdk import Ontology

sdk = Ontology()
contract_address = '1ddbb682743e9d9e2b71ff419e97a9358c5c4ee9'
oep4 = sdk.neo_vm.aio_oep4(contract_address)
owner = 'ANDfjwrUroaVtvBguDtrWKRMyxFwvVwnZD'
to_address = spender.get_address_base58()
tx_hash = await oep4.transfer_from(spender, owner, to_address, 1, acct1, 500, 20000)
```

Transfers value amount of tokens from address owner to address to\_address asynchronously.

### Async OEP-5 <a id="async-oep-5"></a>

### Async OEP-8 <a id="async-oep-8"></a>

## Sig Server <a id="sig-server"></a>

## FAQs <a id="faqs"></a>

* **How do I get ONT and ONG in poloris test net?**

You can visit [here](https://developer.ont.io/applyOng) to apply test tokens.

* **Why do I need to connect to a node?**

The Ontology protocol defines a way for people to interact with smart contracts and each other over a network. In order to have up-to-date information about the status of contracts, balances, and new transactions, the protocol requires a connection to nodes on the network. These nodes are constantly sharing new data with each other. The SDK is a python library for connecting to these nodes. It does not run its own node internally.

