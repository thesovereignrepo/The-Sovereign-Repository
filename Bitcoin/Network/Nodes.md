## Running your own bitcoin node
Running your own bitcoin node is a key part of becoming more fully self sovereign using bitcoin. First you'll need to start with self-custody. If bitcoin you've obtained is held on an exchange like CashApp, Coinbase or Kraken, you don't hold the keys. Holding the keys gives you access to your address sets and transaction keys, that in the modern era, are derived from HD wallets. See [bip-32](https://en.bitcoin.it/wiki/BIP_0032), [bip-39](https://en.bitcoin.it/wiki/BIP_0039), [bip-44](https://en.bitcoin.it/wiki/BIP_0044).

Using self-custody hot wallet apps allow you to manage your bitcoin privately. The wallets can be thought of as *key rings* as they don't actually hold bitcoin. Bitcoin is represented as transactions on the blockchain. Some good hot wallets are covered [here](url). 

You can use your self-custody wallet in conjunction with running your own node. Running your own node can take some technical fortitude to get things up and running safely and properly. 
Two ways of achieving this combination are:

* Dojo technology
* BTCPay Server technology

The best and easiest way is to purchase and install RoninDojo technology at your home or office.

### [RoninDojo](https://web.archive.org/web/20240426061333mp_/https://wiki.ronindojo.io/en/home)
RoninDojo is turnkey bitcoin node technology including hardware, software and support. 

**Tanto** by RoninDojo is a plug-and-play bitcoin node in a rugged premium aluminum case. The Tanto contains a ROCKPro64 single board computer with ARM microprocessor, 
memory, 1TB or 2TB SSD, Ethernet port and power supply. Preinstalled with software and optionally - recent snapshot of the blockchain database to minimize the time required to complete the Initial Blockchain Download (IBD) process, to get up and running. Support is provided on [RoninDojo website](https://web.archive.org/web/20240421123402mp_/https://wiki.ronindojo.io/en/support) and on Telegram - [Dojo by Samourai Wallet](t.me/RoninDojoNode/1)

[How to setup Tanto - Bitcoin Magazine](https://bitcoinmagazine.com/guides/set-up-ronindojo-for-private-bitcoin#gid=ci029c5f461008272a&pid=tanto04_1)

[Why I Chose RoninDojo?](https://blog.ronindojo.io/why-choose-ronindojo/)

`NOTE: New Tanto nodes are temporarily unavailable for purchase at the RoninDojo store.`

### [MyDojo](https://github.com/Dojo-Open-Source-Project/samourai-dojo/blob/develop/doc/DOCKER_ubuntu_setup.md) 
MyDojo by Samourai Wallet is open source software that lets you build a do-it-yourself node on your own computer hardware or virtual machine using the same open source code base used on RoninDojo Tanto. This path is much more challenging and requires your own hardware, technical expertise and extra time and patience. If you have background in Linux, you can get a node up and running MyDojo. (MyDojo is sometimes referred to as vanilla dojo to distinguish it from RoninDojo Tanto.) Setting up a node with MyDojo lacks the smooth user experience and addition premium user interface components provided RoninDojo Tanto. Detailed instructions are provided [here](https://github.com/Dojo-Open-Source-Project/samourai-dojo/blob/develop/doc%2FDOCKER_ubuntu_setup.md). Support is provided on Telegram - [Dojo by Samourai Wallet](https://t.me/samourai_dojo) 

### Attaching wallets to your Dojo node
Self-custody wallets are attached/paired or *imported* to your node by taking steps in the wallet. Your node's onion address ([tor](https://www.torproject.org/)) is used to provide a secure, anonymous connection from your wallet to your node over the Internet.

[Pairing Samourai Wallet](https://web.archive.org/web/20240214172859mp_/https://wiki.ronindojo.io/en/setup/samourai-wallet)

[Connecting Sparraw Wallet](https://web.archive.org/web/20240502010028mp_/https://wiki.ronindojo.io/en/setup/sparrow-wallet)


### [BTCPay Server](https://btcpayserver.org/)
BTCPay Server is a free, open-source & self-hosted bitcoin payment gateway that contains a full bitcoin node. You can install the software on your own server hardware, a virtual machine, Virtual Private Server (VPS) or cloud server. See [deployment methods](https://docs.btcpayserver.org/Deployment/) to decide which method best fits you. Difficulty of installing and maintaining, intended use, features and cost are key factors to consider. [Hardware deployment](https://docs.btcpayserver.org/Deployment/Hardware/) provides absolute control over your infrastructure. Running a BTCPayServer can be a great experience, but requires deep technical skills with Linux, Docker and networking. 

### Attaching wallets to your BTCPay Server

[Fully Noded](https://fullynoded.app/) is a mobile app that can be used in conjunction with your BTCPayServer. Fully Noded works connects to your BTCPayServer over [tor](https://www.torproject.org/) and provides a hot wallet and monitor of the server, providing a fully self-sovereign bitcoin experience. The payment gateway of BTCPayServer requires a static IP and your own domain name. It's recommended to operate over a VPN and not use your home router's IP address.

## Bitcoin Node Operations

### Public vs Private Operation
You have the option to operate your node publicly or privately. Setting up to use a [tor hidden service](https://en.bitcoin.it/wiki/Setting_up_a_Tor_hidden_service) only will allow your node to make only outbound connections to other bitcoin network nodes. This is the default for dojo nodes. BTCPayServer nodes, on the other hand, require a static IP and a publically registered domain name. Running a node behind a static IP address is not recommended for home use. This will disclose identity information regarding your personal residence to the bitcoin network since your home IP is typically owned by your ISP and fully KYC info is readily obtainable. It's certainly possible to set up a VPN with a static IP to run a public node. Technology such as Linode, pfSense/opnSense and OpenVPN can be used for this purpose. However, for first time node runners, it's recommended to stick with a private tor-only setup.

### Initial Block Download (IBD)
Initial block download refers to the process where nodes synchronize themselves to the network by downloading blocks that are new to them. This will happen when a node is far behind the tip of the best block chain. In the process of IBD, a node does not accept incoming transactions nor request mempool transactions.

If you are trying to set up a new node following the instructions below, you will go through the IBD process at the first run, and it may take a considerable amount of time since a new node has to download the entire block chain (which is roughly 340 gigabytes now). During the download, there could be a high usage for the network and CPU (since the node has to verify the blocks downloaded), and the client will take up an increasing amount of storage space (reduce storage provides more details on reducing storage). 

### Selecting an Address Indexer
In order to quickly and efficiently lookup bitcoin addresses in transactions already on the blockchain, your node run an indexer. There are several types of address indexers.  

[Indexer](https://web.archive.org/web/20240214172902mp_/https://wiki.ronindojo.io/en/setup/indexer)

Electrum Rust Server (electrs)

Fulcrum 

TODO: pros and cons

### Network and Power
Running your own node requires 365/24/7 uptime to remain efficient and reliabile. The bitcoin blockchain is constantly being updated as transactions occur and blocks are added. Your node is constantly communicating with other nodes in the bitcoin network verifying and storing the data on its internal hard drive or SSD. Block indexers run on your node to provide fast access to the transactions. These processes can be costly to re-sync if they're interrupted by power or network outages. Use a good Uninterruptible Power Supply (UPS) to power your node and networking equipment (router, switches, etc) to keep your system up should you lose power from your electric service provider. Also, consider subscribing to a backup Internet service to use if your primary Internet service becomes unavailable.


### Summary
The combination of a self-custody wallet and running your own node provides a level of privacy that can't be obtained by using wallets connected to nodes other than your own. When your wallet accesses bitcoin blockchain addresses and transactions strictly from your own node, the communication messages between the wallet and the bitcoin network can't be surveilled (logged) by an outside node provider. Running your own node requires more resources and responsibility on your part, but will take you to another level of self sovereignty using bitcoin.

## Some interesting sites to view public live network nodes

### [Bitnodes](https://bitnodes.io)
Bitnodes is a site listing reachable bitcoin nodes. Nodes configured with a static IP address appear in the list. Privately nodes communicating with tor only don't appear. This list however can give you insights into the size and detail of the publically visible nodes in the network.

### [Bitcoin Testnet Explorer](https://live.blockcypher.com/btc-testnet/)
An explorer for testnet.

### [1ML](https://1ml.com/)
Lightning Network Search and Analysis Engine

## Full Node Links
Use these links for informational purposes only. Some are dated and aren't necessarily best practices, yet contain useful information and background.

### [Running a Full Node](https://bitcoin.org/en/full-node#what-is-a-full-node)

### [Full node](https://en.bitcoin.it/wiki/Full_node)

### [How to deploy Bitcoin Core Full-node](https://www.blockmeadow.com/bitcoin-how-to-deploy-full-node/)

### [The Bitcoin Network - saylor.org](https://learn.saylor.org/mod/book/view.php?id=36307&chapterid=18899)




