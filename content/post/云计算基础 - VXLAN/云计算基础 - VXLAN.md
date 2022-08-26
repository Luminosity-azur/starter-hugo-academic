---
title: Cloud Computing - Virtual eXtensible Local Area Network (VxLAN)
subtitle: This post describes the background, principle and format of VxLAN.

# Summary for listings and search engines
summary: This post describes the background, principle and format of VxLAN.

tags: 
- Cloud Computing

categories: 
- Cloud Computing
date: '2022-06-12'
math: true
---
## VxLAN overview and causes
1. The scale of virtual machine is limited by the performance specification of network equipment
Server virtualization leads to a geometric increase in the number of virtual machines, which is accompanied by a sharp increase in the number of MAC addresses of virtual machine network cards. The MAC address table specification of the layer 2 device on the original access side cannot meet the rapidly growing number of virtual machines.
**VxLAN solution:**
VxLAN encapsulates the message sent by the virtual machine in the same area planned by the network administrator into a new UDP message, and uses the IP and MAC addresses of the physical network as the outer layer header, so that the message only shows the encapsulated parameters to other devices in the network.


2. The isolation capability of the network is limited
For the current public cloud or large-scale virtualized computing server needs tens of thousands or more tenants, the existing VLAN number is insufficient to meet this demand
**VxLAN solution:**
VxLAN introduces a user ID similar to VLAN ID and becomes the vxlan network identifier VNI (VxLAN network identifier), which is composed of 24 bits. Therefore, it can support up to 16M VxLAN segments.


3. Virtual machine migration scope is limited
The traditional two-layer network can not meet the virtual machine migration that has become a normal job, nor can it meet the business of ensuring that the migration range and the availability of services are not limited.
**VxLAN solution:**
VxLAN encapsulates the original message sent by the virtual machine and transmits it through the VxLAN tunnel. This tunnel can span any network. Therefore, for virtual machines in the same network segment, it is logically equivalent to being in the same layer 2 domain. In other words, VxLAN technology can build a virtual layer 2 network on the three-layer network. As long as the virtual machine route is reachable, it can be planned into the same layer 2 network.

## Principle of VxLAN
VxLAN is a network virtualization technology. It encapsulates the data packets sent by the original host in UDP, and uses the IP and MAC of the physical network as the outermost headers to encapsulate them in parallel, and then transmits them on the IP network. After reaching the destination, the tunnel endpoint decapsulates and sends the data to the target host.
UDP port number of VxLAN: 4789

## VxLAN message encapsulation format
VxLAN communication process:
1. The sender sends a data frame to the receiver, which contains the virtual MAC addresses of the sender and the receiver.
2. The VTEP node connected by the sender receives the data frame, encapsulates it and sends it to the destination VTEP node.
3. The message is transmitted to the destination VTEP node through the Underlay network
4. After receiving the message, the destination VTEP node decapsules the internal data frame and delivers the data frame to the receiver.
5. The receiver receives the data frame and completes the transmission.

## VxLAN Configuration instance
<div align=center> 
<img src = 'https://s3.bmp.ovh/imgs/2022/07/13/75ba1a3b4bb833a8.png'></img>
<div align=left>