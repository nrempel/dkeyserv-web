---
title: "Paper Progress"
date: 2020-03-25T12:58:44-07:00
draft: false
---

Work has been progressing on the design of Dkeyserv. I am preparing a paper which outlines the approach and provides more information. Dkeyserv will offer a feature-rich PGP keyserver application. Each instance of Dkeyserv will connect to a running network of instances and the data will be securely replicated across the network in a decentralized manner.

Tendermint will be used as the consensus and replication framework to synchronize data between instances. The Dkeyserv application will include a comprehensive governance module that will allow administrators to make proposals and vote on changes for things such as add and removing nodes from the network as well as proposing software upgrade in order to facilitate smooth transitions. The governance framework will give instances a weighted vote with the weight being proportional to the length of time that the instance has been a part of the network. This governance method should facilitate the growth of the network while also protecting the network from malicious entities.