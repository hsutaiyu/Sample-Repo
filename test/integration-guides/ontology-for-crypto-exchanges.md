# Exchange API



## Ontology Exchange Docking Document

There are two kinds of assets in ONT: native assets and contract assets. Native assets are ONT and ONG. When docking with the exchange, it mainly processes deposit and withdrawal of these two assets.

The outline of this document is as follows:

* Ontology Exchange Docking Document
  * 1.Deploy Ontology Synchronization Node
    * Get from source code
    * Get from release
    * Server deployment
      * Create wallet
      * Start up node
  * 2. Use CLI Client
    * Security policy
    * CLI instruction
      * Create wallet
      * Generate deposit address
  * 3. Process Asset Transactions
    * Transaction docking program the exchange needs to develop
    * User deposit
    * Deposit record
    * Process user withdrawal request
      * Create account based on private key
      * Use wallet management
    * Address generation
    * ONT and ONG transfer
      * 1. Initialization
      * 2. Query
        * Query ONT, ONG Balance
        * Query whether the transaction is in the transaction pool
        * Query whether the transaction is successful
        * The list of chain interaction interfaces
      * 3. ONT transfer
        * Construct transfer transaction and send
        * Multiple signatures
        * One to multiple or multiple to multiple
        * Use signature server to sign
      * 4. ONG transfer
        * ONG transfer
        * Withdraw ONG
  * 4. Distribute ONG to Users
    * What is ONG
    * Calculate the amount of ONG that can withdraw
    * Distribute ONG to users
    * Users withdraw ONG
  * 5. Signature service
  * Native contract address
  * FAQ
  * Mainnet update note



### 1.Deploy Ontology Synchronization Node

There are two ways to deploy Ontology synchronization nodes:

#### Get from source code

Clone ontology repository to **$GOPATH/src/github.com/ontio** directory

```text
$ git clone https://github.com/ontio/ontology.git
```

Or

```text
$ go get github.com/ontio/ontology
```

Use the third-party package management tool glide to manage the dependent libraries

```text
$ cd $GOPATH/src/github.com/ontio/ontology
$ glide install
```

Compile source code with make

```text
$ make
```

An executable program will be generated after a successful compilation \(using `make all` command will generate sig server under 'tools' directory ）

* `ontology`: Node program/node control program provided by command line

#### Get from release

[release page](https://github.com/ontio/ontology/releases)

#### Server deployment

1. **Create wallet\(not mandatory for sync node\)**
   * Create the wallet file - wallet.dat that is required for nodes running through the CLI

     ```text
     $ ./ontology account add -d
     Use default setting '-t ecdsa -b 256 -s SHA256withECDSA' 
         signature algorithm: ecdsa 
         curve: P-256 
         signature scheme: SHA256withECDSA 
     Password:
     Re-enter Password:

     Index: 1
     Label: 
     Address: AWVNFw74G8Sx9vcxGbmh4gT54ayuwb3bcm
     Public key: 02c17cd91acf618d497f65f1fc4f52de7952c8b2337883f898dda887953cd29dd7
     Signature scheme: SHA256withECDSA

     Create account successfully.
     ```

     ​

   * Directory Structure

     ```text
        $ tree
        └── ontology
            ├── ontology
            └── wallet.dat
     ```



