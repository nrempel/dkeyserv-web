---
title: dkeyserv
type: docs
---

# Distributed PGP Keyserver

**dkeyserv** is an exploration of the benefits and implementation of a distributed PGP keyserver.

## What Are the Benefits?

{{< columns >}}

### Resilient

A distributed keyserver is resilient to downtime and provides redundancy in case of failure.
If a single keyserver node disappears, it does not necessarily effect the network. Run your own node
to contribute to the strength of the network.

<--->

### Trustworthy

By replicating state across all nodes in the keyserver network and ensuring immutability, you can be sure keys have not been tampered with. Run your own node to ensure you have direct access to replicated keys.

{{< /columns >}}

## Status

**dkeyserv** is a research project in an early phase. Currently information is being gathered and data replication protocols are being evaluated.