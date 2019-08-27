# How to integrate a dApp

## Basic functionalities

From a developer's point of view, the functions that facilitate interaction with Ontology's chain can be broadly categorized as follows:

* _**Login:**_  Allows user identity verification, and querying account or identity related information
* _**Payment:**_  The transaction service for both `ONT` and `ONG`, or the other `OEP` token related transactions can be carried out by deploying smart contracts.
* _**Smart contract development:**_  As far as the vast majority of `dApps` are concerned, smart contracts are used either completely, or in part to implement the necessary logic. Considering games, for instance, functions such as buying, selling, renting, or generating random numbers, etc. can conveniently be implemented using smart contracts. For more details on smart contracts, feel free to check [this](../../untitled-1/smart-contract.md) out.
* _**Tokenizing assets:**_  Developers always have the option to tokenize and issue many different types of assets, such as `OEP4`, `OEP5`, `OEP8`, etc. For a more detailed explanation of the aforementioned assets, refer to [this](../../untitled-1/tokens-and-assets.md).

### Integration options

Keeping in mind the different circumstances and scenarios that the developers might be working with, Ontology provides multiple ways to integrate the platform into a `dApp`.

* The multiple decentralized methods that use the `dAPI`, including the option to open a `dApp` from within the wallet, and the `Cyano` wallet chrome plugin, all allow the `dApp` to interact with the chain.
* Integrating using one of the multiple `SDKs`,  a method which is also decentralized at its core. For example, games that use the `Unity 3D` engine and `C#`. would encounter the need to integrate through the respective `SDKs`.
* Making the application open-platform using the ONT ID. Though, this method is not completely decentralized.

No matter which one of the above methods you choose to integrate your dApp,  the login feature and the ability to deploy smart contracts remains constant and unaffected. Therefore, developers can freely choose any of the method to integrate `dApps`.

This section lays out the general methods that the dApp developers using Ontology can employ to swiftly carry out the integration process.

