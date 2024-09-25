## Running your own bitcoin node
Running your own bitcoin node is a key part of becoming more fully self sovereign using bitcoin. First you'll need to start with self-custody. If bitcoin you've obtained is held on an exchange like CashApp, Coinbase or Kraken, you don't hold the keys. Holding the keys gives you access to your address sets and transaction keys, that in the modern era, are derived from HD wallets. See [bip-32](https://en.bitcoin.it/wiki/BIP_0032), [bip-39](https://en.bitcoin.it/wiki/BIP_0039), [bip-44](https://en.bitcoin.it/wiki/BIP_0044).

Using self-custody hot wallet apps allow you to manage your bitcoin privately. The wallets can be thought of as *key rings* as they don't actually hold bitcoin. Bitcoin is represented as transactions on the blockchain. Some good hot wallets are covered [here](url). 

You can use your self-custody wallet in conjunction with running your own node. Running your own node can take some technical fortitude to get things up and running safely and properly. One of the best ways to run your own node is to purchase a RoninDojo.

### [RoninDojo](https://web.archive.org/web/20240426061333mp_/https://wiki.ronindojo.io/en/home)
RoninDojo is turnkey bitcoin node technology including hardware, software and support. TODO: Add better description...


### [MyDojo](https://github.com/Dojo-Open-Source-Project/samourai-dojo/blob/develop/doc/DOCKER_ubuntu_setup.md) 
MyDojo by Samourai Wallet is open source software that lets you build a node on your own computer hardware or virtual machine. This path is much more challenging and requires technical expertise and much more time. If you have background in Linux, you can get a node up and running MyDojo. (MyDojo is sometimes referred to as *vanilla dojo* to distinguish it from RoninDojo.) TODO: Add better description...

## Attaching your wallet to your node
A self-custody wallet gets attached or *imported* to your node by taking steps in the wallet. Your node's onion address (tor) is used to provide a secure, anonymous connection from your wallet to your node over the Internet. Details of how to attach Samourai Wallet or Sparraw Wallet follow...TODO

The combination of your wallet and your node provides privacy that can't be obtained using someone else's node. Your wallet accesses addresses and transactions that can be surveilled (logged) by someone else's node. Having your own node is key to more privacy. Also, transactions initiated from your wallet will be sent to the bitcoin network through your node, so no logging can be done that may identify you.

## Some interesting sites to view live network nodes

### [Bitnodes](https://bitnodes.io)
Bitnodes is a site listing publicly reachable bitcoin nodes with their own static IP address. You would *not* normally setup your own node to have it's own IP address, so your node won't appear in the list. You normally configure your node to participate privately on the bitcoin network over tor. The list however can give you insights into the size and detail of the publically visible nodes in the network.

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




