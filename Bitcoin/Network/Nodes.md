## Running your own bitcoin node
Running your own bitcoin node is a key part of becoming more fully self sovereign using bitcoin. First you'll need to start with self-custody. If bitcoin you've obtained is held on an exchange like CashApp, Coinbase or Kraken, you don't hold the keys. Holding the keys gives you access to your address sets and transaction keys, that in the modern era, are derived from HD wallets. See [bip-32](https://en.bitcoin.it/wiki/BIP_0032), [bip-39](https://en.bitcoin.it/wiki/BIP_0039), [bip-44](https://en.bitcoin.it/wiki/BIP_0044).

Using self-custody hot wallet apps allow you to manage your bitcoin privately. The wallets can be thought of as *key rings* as they don't actually hold bitcoin. Bitcoin is represented as transactions on the blockchain. Some good hot wallets are covered [here](url). 

You can use your self-custody wallet in conjunction with running your own node. Running your own node can take some technical fortitude to get things up and running safely and properly. 
Two ways of achieving this combination are:

* Dojo technology
* BTCPay Server technology

The best and easiest way is to purchase and install RoninDojo built technology at your home or office.

### [RoninDojo](https://web.archive.org/web/20240426061333mp_/https://wiki.ronindojo.io/en/home)
RoninDojo provides turnkey bitcoin technology including hardware, software and support. See [What is RoninDojo?](https://blog.ronindojo.io/what-is-ronindojo)

RoninCLI and the RoninUI graphical user interface make setting up and using your own node smooth and enjoyable.

**Tanto** hardware offerings by RoninDojo are plug-and-play bitcoin nodes. The Tanto Gen2 contains a [ROCKPro64](https://pine64.org/devices/rockpro64) single board computer with ARM microprocessor, 
memory, 1TB or 2TB SSD, Ethernet port and power supply. Preinstalled with software and optionally - a recent snapshot of the blockchain database to minimize the time required to complete the Initial Blockchain Download (IBD) process, to get up and running faster. Support is provided on [RoninDojo website](https://web.archive.org/web/20240421123402mp_/https://wiki.ronindojo.io/en/support) and on Telegram - [Dojo by Samourai Wallet](t.me/RoninDojoNode/1)

[How to setup Tanto - Bitcoin Magazine](https://bitcoinmagazine.com/guides/set-up-ronindojo-for-private-bitcoin#gid=ci029c5f461008272a&pid=tanto04_1)

[Why I Chose RoninDojo?](https://blog.ronindojo.io/why-choose-ronindojo/)

`NOTE: Tanto nodes are temporarily unavailable for purchase at the RoninDojo store.` See [RoninDojo Status Update](https://blog.ronindojo.io/ronindojo-update-2024)

### [MyDojo](https://github.com/Dojo-Open-Source-Project/samourai-dojo/blob/develop/doc/DOCKER_ubuntu_setup.md) 
MyDojo by Samourai Wallet is open source software that lets you build a do-it-yourself node on your own computer hardware or virtual machine using the same open source code base used on RoninDojo Tanto. This path is much more challenging and requires your own hardware, technical expertise and extra time and patience. If you have background in Linux, you can get a node up and running MyDojo. (MyDojo is sometimes referred to as _vanilla dojo_ to distinguish it from RoninDojo Tanto.) Setting up a node with MyDojo lacks the smooth user experience and additional premium user interface components (RoninCLI and RoninUI) provided with RoninDojo Tanto. Detailed instructions are provided [here](https://github.com/Dojo-Open-Source-Project/samourai-dojo/blob/develop/doc%2FDOCKER_ubuntu_setup.md). Support is provided on Telegram - [Dojo by Samourai Wallet](https://t.me/samourai_dojo) 

### Attaching wallets to your Dojo node
Self-custody wallets are attached/paired or *imported* to your node by taking steps in the wallet and on your node. Your node's onion address ([tor](https://www.torproject.org/)) is used to provide a secure, anonymous connection from your wallet to your node over the Internet.

[Pairing Samourai Wallet](https://web.archive.org/web/20240214172859mp_/https://wiki.ronindojo.io/en/setup/samourai-wallet)

[Connecting Sparraw Wallet](https://web.archive.org/web/20240502010028mp_/https://wiki.ronindojo.io/en/setup/sparrow-wallet)


### [BTCPay Server](https://btcpayserver.org/)
BTCPay Server is a free, open-source & self-hosted bitcoin payment gateway that contains a full bitcoin node. You can install the software on your own server hardware, virtual machine, Virtual Private Server (VPS) or cloud server. See [deployment methods](https://docs.btcpayserver.org/Deployment/) to decide which method best fits you. Difficulty of installing and maintaining, your intended use cases, features and cost are key factors to consider. [Hardware deployment](https://docs.btcpayserver.org/Deployment/Hardware/) provides absolute control over your infrastructure. Running a BTCPayServer can be a great experience, but requires technical skills with Linux, Docker and networking. The payment gateway of BTCPayServer requires a static IP and your own domain name. It's recommended to operate over a VPN with static IP and not use your home router's IP address. The payment gateway is accessible from a browser from desktop, laptop, tablet or mobile. It's recommended to use 2FA for logins. The payment gateway can create a soft wallet and can also import a zpub for a watch-only wallet.

### Attaching wallets to your BTCPay Server

[Fully Noded](https://fullynoded.app/) is a mobile app that can be used in conjunction with your BTCPayServer. Fully Noded connects to your BTCPayServer over [tor](https://www.torproject.org/) and provides a hot wallet and monitors the server, providing a fully self-sovereign bitcoin experience.

## Bitcoin Node Operations

### Public vs Private Operation
You have the option to operate your node publicly or privately. Setting up to use a [tor hidden service](https://en.bitcoin.it/wiki/Setting_up_a_Tor_hidden_service) will allow your node to make outbound connections while hiding your node from inbound connections to other bitcoin network nodes. This is the default for dojo nodes. BTCPayServer nodes, on the other hand, require a static IP and a publicly registered domain name. Running a node behind your ISP static IP address is not recommended for home use. This can disclose identity and location information regarding your personal residence to the bitcoin network since your home IP is typically owned by your ISP and fully KYC info is readily obtainable. A better way is to use a VPN with a static IP if you wish to run a public node. Technologies such as Linode, pfSense/opnSense and OpenVPN can be used for this purpose. For first time node runners, it's best to stick with a private tor-only setup.

### Firewall
If you run your node using tor-only, you won't need to provide any special firewall rules. Your node will initiate outbound connections to other nodes in the bitcoin network. However, if you want to make your node accessible publicly from the Internet, you'll need to open inbound port 8333 for bitcoin (mainnet). This normally is done by setting up a port forwarding rule in your router/firewall. When your router receives a TCP connection from the Internet on port 8333, it should forward it to your node's local IP address. You'll also need to use a firewall on your node, such as [Uncomplicated Firewall (UFW)](https://help.ubuntu.com/community/UFW) for full protection. 

### Initial Block Download (IBD)
_Initial block download (IBD)_ refers to the process of downloading the entire bitcoin blockchain. The node stores the blocks to disk (HDD or SSD) and verifies them. During the process, a node does not accept incoming transactions nor request mempool transactions. After the IBD completes, the node is ready to be used. Depending on your Internet connection and the tor network, this can take several days. Be patient and be sure to only run your node using a UPS. Losing power to the node may result in database corruption and requiring you to delete the bad database files and restart the IBD process.

### Selecting an Address Indexer
In order to quickly and efficiently lookup bitcoin addresses in transactions already on the blockchain, an indexer program (daemon) runs on your node. There are several types of address indexers.  

[RoninDojo Indexer setup](https://web.archive.org/web/20240214172902mp_/https://wiki.ronindojo.io/en/setup/indexer)

This [article](https://sparrowwallet.com/docs/server-performance.html) provides an analysis of the pros and cons of the available indexers that con install on your node to choose from. 

`TLDR; For this reason, Fulcrum emerges as a clear winner in this benchmark`

While Fulcrum is best, it is not the default indexer on dojos. Additional configuration and a restart of your node is required to run Fulcrom. One downside of using the Fulcrum indexer is that it's sensitive to node power loss. If your node abruptly loses power, the Fulcrum index can be corrupted and require your to delete and rebuild the index database which can take several days to complete.

### Network and Power Backup
Running your own node requires 365/24/7 uptime to remain efficient and reliabile. The bitcoin blockchain is constantly being updated as transactions occur and blocks are added. Your node is constantly communicating with other nodes in the bitcoin network verifying and storing the data on its internal hard drive or SSD. The address indexer runs on your node and continuously indexes new blocks to provide fast access to the transactions. These processes take time to re-sync to blockchain data if they're interrupted by power or network outages. Use an Uninterruptible Power Supply (UPS) to provide backup power to your node and networking equipment (router, switches, etc). Also, consider subscribing to a secondary backup Internet service to use in case your primary Internet service is temporarily unavailable.


### Summary
The combination of a self-custody wallet and running your own node provides a level of privacy that can't be obtained by using wallets connected to nodes other than your own. When your wallet accesses bitcoin blockchain addresses and transactions strictly from your own node, messages and requests between the wallet and the bitcoin network can't be surveilled (logged) by an outside node provider. Running your own node requires more resources and responsibility on your part, but will take you to another level of self sovereignty using bitcoin.

## Some interesting sites to view public live network nodes

### [Bitnodes](https://bitnodes.io)
Bitnodes is a site listing reachable bitcoin nodes. Nodes configured with a static IP address appear in the list. Private nodes communicating with tor-only don't appear. This list however can give you insights into the size and detail of the publicly visible nodes in the network.

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




