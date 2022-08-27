---
title: Communication & Computer Network - "Single-hop" and "Multi-hop"
subtitle: This post analyzes the concepts of "single-hop" and "multi-hop".

# Summary for listings and search engines
summary: This post analyzes the concepts of "single-hop" and "multi-hop".

tags: 
- Communication & Computer Network

categories: 
- Communication & Computer Network
date: '2022-04-07'
math: true
---
## Definition of single-hop
In the traditional wireless LAN, each client accesses the network through an infinite link linked with the AP. If users want to communicate with each other, they must first access a fixed access point. This network is called a **single-hop** network.

## Definition of multi-hop
In a wireless network, any wireless device point can act as an AP and a router at the same time. Each node in the network can send and receive signals, and each node can directly communicate with one or more peer nodes. This network is called a **multi-hop** network.
It can also be understood that the transmission of information is completed through forwarding by multiple nodes on the link. Each node can directly communicate with one or more peer nodes. Multi hop means multiple forwarding.

## Concrete explanation and application of multi-hop intermediate node
In wireless multi hop networks, the typical path from the source node to the destination node is composed of multiple hops, and the intermediate node on the path acts as the forwarding node. Therefore, a node in a wireless multi-hop network has two functions:
1. Act as an end node to generate or receive data packets;
2. Act as a router to forward data packets from other nodes.
The main applications are: wireless AD Hoc network, wireless sensor network (WSN) and wireless mesh network.