# Interact with a public node

## Overview

The [`RPC`](rpc-api.md) interface, [`RESTful`](restful-api.md) interface, and [`WebSocket`](websocket-api.md) interface of the Ontology node follow a set of public interface specifications.

By default, the `RESTful` interface listens on `port 20334`, the `WebSocket` interface listens on `port 20335`, and the `RPC` interface listens on `port 20336`.

## Using public nodes

It is inconvenient for developers to run their own nodes. Therefore, the Ontology blockchain provides the `Polaris` test network node and the `Ontology` main network node for developers to use, all supporting `RPC`, `RESTful`, and `WebSocket` calls, and using the default port number.

{% hint style="success" %}
HTTPS is supported in `port 10334` of Polaris TestNet node "[http://polaris1.ont.io](http://polaris1.ont.io)" and Ontology MainNet node "[http://dappnode1.ont.io](http://dappnode1.ont.io)".
{% endhint %}

### Polaris TestNet

* `Polaris` test network node
  * [http://polaris1.ont.io](http://polaris1.ont.io)
  * [http://polaris2.ont.io](http://polaris2.ont.io)
  * [http://polaris3.ont.io](http://polaris3.ont.io)
  * [http://polaris4.ont.io](http://polaris4.ont.io)
  * [http://polaris5.ont.io](http://polaris5.ont.io)

{% hint style="info" %}
If you want to develop on a `Polaris` test network, you can apply for test tokens `ONT` and `ONG` [here](https://developer.ont.io/applyOng).
{% endhint %}

### Ontology MainNet

* `Ontology` main network node
  * [http://dappnode1.ont.io](http://dappnode1.ont.io)
  * [http://dappnode2.ont.io](http://dappnode2.ont.io)
  * [http://dappnode3.ont.io](http://dappnode3.ont.io)
  * [http://dappnode4.ont.io](http://dappnode4.ont.io)

{% hint style="info" %}
According to the needs of developers, we also provide a way to \[Node deployment\]
{% endhint %}

