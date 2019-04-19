# Lightning Node Management

## Monitoring software

### [RTL - Ride The Lightning](https://github.com/ShahanaFarooqui/RTL)

RTL is a web UI for Lightning Network Daemon.  
https://medium.com/coinmonks/introducing-rtl-a-web-ui-for-lnd-d0bb0d937e91


### [ZeusLN](https://zeusln.app/)

A mobile Bitcoin app for Lightning Network Daemon (lnd) node operators. Android and iOS.

###  [Joule](https://lightningjoule.com/)

Bring the power of lightning to the web with in-browser payments and identity, all with your own node.   
https://medium.com/lightning-power-users/bitcoin-lightning-joule-chrome-extension-ac149bb05cb9

### [Zap](https://zap.jackmallers.com/)

A lightning wallet for desktop and iOS.


### [lndash](https://github.com/djmelik/lndash)

lndash is a simple read-only web dashboard for lnd - Lightning Network Daemon.  
Demonstration: https://lightninglayer.com/ 

Features:

* Peer view
* Channel view
* Forwarding Events (routed payments) view
* Looking Glass Tool (route/path lookup)
* Lightning Network Graph

### Spark wallet for C-Lightning(https://github.com/shesek/spark-wallet)

Spark is a minimalistic wallet GUI for c-lightning, accessible over the web or through mobile and desktop apps (for Android, Linux, macOS and Windows). It is currently oriented for technically advanced users and is not an all-in-one package, but rather a "remote control" interface for a c-lightning node that has to be managed separately.

---
## Get inbound liquidity

Open a channel to exchange/merchant accepting Lightning, make a LN payment, and withdraw on-chain

### LightningTo.me
Opens a channel for free funded with 2 000 000 satoshis. Need to have 10 channels open already to use this service.

### [LightningPowerUsers.com](https://lightningpowerusers.com/home/)

Request inbound capacity for small fee

Recommended channel size: Between 500,000 satoshis (~$20) and 16,500,000 satoshis (~$600).

### [Thor: Lightning Channel-Opening Service by Bitrefill.com](https://www.bitrefill.com/thor-lightning-network-channels/?hl=en)
pay with Lightning for an inbound channel of up to 16 000 000 satoshis.

### Tippin.me
Tip yourself via LN and withdraw onchain.

### zigzag.io
An exchange that accepts Lightning payments

### [Lightning Loop](https://github.com/lightninglabs/loop)

Lightning Loop is a non-custodial service offered by Lightning Labs to bridge on-chain and off-chain Bitcoin using submarine swaps. 

In the current iteration of the Loop software, only off-chain to on-chain swaps are supported, where the Loop client sends funds off-chain in exchange for the funds back on-chain. This is called a Loop Out.

https://lightning.engineering/loop/index.html#lightning-loop-grpc-api-reference

## Pass around Lightning Torches

### [LNTrustChain - now finished](https://www.youtube.com/watch?v=89TSOayiqtA&feature=youtu.be)
Find out on twitter who holds the torch.
every participant adds 10000 satoshis

### [LNTinyTorch](http://lntinytorch.com/)
Every participant adds 1 satoshi


## Reduce the routing fees for more inbound channels

https://api.lightning.community/#updatechannelpolicy

Lightning fees are related to the amount routed.
There are two fee components:
* base fee (base_fee_msat). The default is 1000 millisat, which means 1 satoshi fee per every routed payment.
* proportional fee (fee_rate) which is set to the minimum by default in lnd: 0.000001. This means there is an additional 1 sat charged for every million satoshis in the routed payment.

`lncli updatechanpolicy 0 0.000001 144`

the default is:  
 `lncli updatechanpolicy 1000 0.000001 144`

---
## Managing channels

Rebalance your channels regularly to keep the inbound liquidity.

### rebalance-lnd

Using this script you can easily rebalance individual channels of your lnd node.

https://github.com/C-Otto/rebalance-lnd


---
## Resources:
* https://github.com/bcongdon/awesome-lightning-network  
A curated list of awesome Lightning Network resources, apps, and libraries

* Elaine Ou - Bootstrapping and maintaining a Lightning node [38 mins video](https://www.youtube.com/watch?v=qX4Z3JY1094)
and [slides](https://lightningresidency.com/assets/presentations/Ou_Bootstrapping_and_Maintaining_a_Lightning_Node.pdf)

* https://medium.com/lightningto-me/practical-solutions-to-inbound-capacity-problem-in-lightning-network-60224aa13393

* Alex Bosworth - Lightning channel Management [35 mins video](https://www.youtube.com/watch?v=HlPIB6jt6ww&feature=youtu.be)

* A list about How to get Channel Liquidity fast? https://github.com/rootzoll/raspiblitz/issues/395

* https://wiki.ion.radar.tech/tutorials/troubleshooting/bootstrapping-channels

* https://en.wikipedia.org/wiki/Dijkstra's_algorithm