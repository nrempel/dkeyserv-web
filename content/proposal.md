---
title: "Proposal"
date: 2020-01-25T11:44:09-08:00
type: docs
---

# Distributed PGP Keyserver

## Author

**dkeyserv** is a research project by Nicholas Rempel.

## What Is the Problem?

PGP is a ubiquitous encryption mechanism commonly used to encrypt email messages and other forms of communication. In order for two individuals to encrypt their communications, they must first exchange keys. For this reason, keyservers exist to facilitate key exchange and discovery between individuals. However, current keyserver implementations do not all run the same software, some servers support a gossip protocol but it is non-standard, servers are susceptible to downtime, and it is possible for keyservers to become compromised and for incorrect key information to be shared. 

To overcome these shortcomings, the goal of **dkeyserv** is to create a distributed and decentralized solution using state machine replication or "blockchain" protocols. By doing this, the keyserver network will be resilient to failure and the data provided by the network will be immutable and trustworthy assuming the network protocol has been implemented correctly and that the network contains a majority of good actors.

## Current Solutions

Current keyserver software exists but there are some problems with the existing model. Existing PGP keyservers are centralized. Because of this, it is possible for a server to become compromised and for key data to tampered with. Or in some cases, the entity running the keyserver could itself be malicious. Additionally, centralized keyservers are susceptible to failure and downtime.

The two most popular keyserver softwares are:

- [SKS Keyserver](https://bitbucket.org/skskeyserver/sks-keyserver/wiki/Home)
- [Hagrid Keyserver](https://gitlab.com/hagrid-keyserver/hagrid)

SKS appears to have a longer history and has some support for peering and propagation of keys between servers. However, it could still be possible to receive bad keys from a peer and peers are inherently trusted without consensus from other peers. In fact, the SKS [keyserver network](https://sks-keyservers.net/status/) was [attacked](https://gist.github.com/rjhansen/67ab921ffb4084c865b3618d6955275f) recently.

Hagrid is a more modern and well-maintained implementation of a PGP keyserver. It does not support any form of gossip protocol and it requires that keys are associated with verified email addresses for discovery.

There is also [dat-keyserver](https://github.com/tdjsnelling/dat-keyserver). It's not clear yet what kind of guarantees the dat protocol offers in the case of data conflicts.

## New Approach

The goal for **dkeyserver** is to implement some form of a Byzantine Fault Tolerant (BFT) state replication protocol. A network is resilient and BFT ensures the data has not been tampered with.