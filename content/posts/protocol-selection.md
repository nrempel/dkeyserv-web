---
title: "Protocol Selection"
date: 2020-02-16T14:53:44-08:00
draft: false
---

I've been looking for a Byzantine Fault Tolerant (BFT) state replication protocol for dkeyserv. Every instance of dkeyserv should be a peer in a network of instances. As a user, you can trust whatever dkeyserv instance you like and, assuming the dkeyserv instance you control is not malicious (or that you own it), you should be able to read public keys from the network and trust that they have not been tampered with as long as the network has not been compromised. For a BFT network to be compromised, at least 1/3 of peers must be malicious or fail in some way.

Since I would like dkeyserv to be a *public* network where any person or organization can run an instance. There is some question as to whether this is feasible with some sort of BFT protocol. Would the network be too easy to attack?

There has been some difficulty in filtering out Blockchain buzzwords and marketing speak from reliable research and technology regarding Byzantine Fault Tolerant systems.

Currently I'm evaluating [Tendermint](https://tendermint.com/core/) as a platform to build dkeyserv upon. The technology seems approachable as a framework and also appears to have a strong theoretical foundation.

