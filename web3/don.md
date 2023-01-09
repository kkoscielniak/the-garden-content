---
title: Decentralized Oracle Network
---

**DON** (_Decentralized OracleNetwork_) is a group of independent [[web3/oracle|oracles]] that provide external data to the [[blockchain]].

Decentralized oracle networks eliminate any [[web3/single-point-of-failure]] in the [[web3/Smart contracts]] by utilizing multiple data inputs. This enables end-to-end reliability and allows high-value smart contracts in low trust environments to become viable.

## How does a DON work?

Every independent node in DON independently retrieves data from an [[off-chain]] source and brings it [[on-chain]]. The data is then aggregated into a deterministing value of truth for that data point. The value is put on the blockchain in a smart contract (often referred to as a _data feed_) for us to read from. The value is constantly updated by the DON itself.

If a singular node or source is hacked, depreciated, or deleted, the DON will leverage the decentralized network and carry on.

The most widely-known DON is [[web3/Chainlink]].
