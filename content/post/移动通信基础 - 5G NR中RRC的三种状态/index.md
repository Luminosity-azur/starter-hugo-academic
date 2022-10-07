---
title: Mobile Communication - Three modes of RRC in 5G/NR (idle, active, inactive)
subtitle: This post first discusses the introduction of INACTIVE mode in 5G/NR, and then makes functional differentiation and specific description of IDLE, INACTIVE and ACTIVE modes of RRC.

# Summary for listings and search engines
summary: This post first discusses the introduction of INACTIVE mode in 5G/NR, and then makes functional differentiation and specific description of IDLE, INACTIVE and ACTIVE modes of RRC.

tags: 
- Mobile Communication

categories: 
- Mobile Communication

date: '2022-09-21'

math: true
---
This post is synchronously published on my CSDN blog:
https://blog.csdn.net/weixin_45766278

<br></br>

## Introduction of RRC_ INACTIVE mode

Before the introduction of RRC_INACTIVE mode, LTE had only two RRC statuses: RRC_IDLE and RRC_CONNECTED. After R13, LTE RRC introduced the new mode.

The R15 specification of 5G/NR continues the inactive mode item introduced in R13, that is, the RRC under NR has three states: **IDLE, INACTIVE, and ACTIVE (CONNECTED)**.

<br></br>

#### So why introduce RRC_ INACTIVE mode?

In fact, similar to NB-IoT in LTE, NB-IoT belongs to the deployment of low power consumption scenarios, and RRC_ INACTIVE mode is mainly used to reduce terminal energy consumption and delay. The mMTC, one of the three typical application scenarios of 5G/NR, includes NB-IoT. (And the RRC_INACTIVE state is not limited to applications in the mMTC scenario.)

<br></br>

#### How to reduce energy consumption and delay in RRC_ INACTIVE mode?
There are three reasons:

- The UE will retain the context of the core network when entering the RRC_INACTIVE mode; Until there is data receiving or sending in RRC_INACTIVE mode, when it is necessary to transition to RRC_CONNETED mode, it is only necessary to carry the unique UE identifier of the core network for recovery through the recovery process, and the gNB can receive and send data packets after receiving the connection recovery.
<br></br>

- Compared with the previous RRC_IDLE mode transition to RRC_CONNETED mode directly (the context applied by the core network needs to be released, and the signaling interaction with the core network side is required when applying for the context), the above process can be omitted when the RRC_INACTIVE mode transitions to RRC_CONNETED mode.
<br></br>

- When UE receives signaling messages from gNB, it needs to blind check PDCCH to know the resource location of signaling. When the RRC_INACTIVE mode transitions to the RRC_CONNETED mode, the UE does not release the context, and the core network side does not need to re allocate the context, so the signaling reception is reduced. This will reduce the energy consumption caused by UE blind detection and the transmission time caused by air port transmission.

<br></br>
<br></br>



## Differences and explanations of the three models

- ACTIVE (CONNECTED):     UE --- NG-RAN :connected    NG-RAN --- 5GC :connected
- IDLE:                   UE --- NG-RAN :released     NG-RAN --- 5GC :released
- INACTIVE:               UE --- NG-RAN :suspend      NG-RAN --- 5GC :connected

<br></br>

#### RRC_ IDLE：
1. PLMN selection;
2. Broadcasting system information;
3. Cell reselection mobility;
4. Paging of mobile termination data is initiated by 5GC;
5. Paging in the mobile terminal data area is managed by 5GC;
6. DRX configured by NAS for CN paging.


<br></br>

#### RRC_ INACTIVE：
1. PLMN selection;
2. Broadcasting system information;
3. Cell reselection mobility;
4. Paging is initiated by NG-RAN (RAN paging);
5. RAN based notification area (RNA) is managed by NG-RAN;
6. RAN paging DRX configured by NG-RAN;
7. Establish 5GC-NG-RAN connection for UE (including control plane/user plane);
8. UE AS message is stored in NG-RAN and UE;
9. NG-RAN knows the RNA of UE.


<br></br>

#### RRC_ ACTIVE (CONNECTED)：
1. Establish 5GC-NG-RAN connection for UE (including control plane/user plane);
2. UE AS message is stored in NG-RAN and UE;
3. NG-RAN knows the cell to which the UE belongs;
4. Transmit unicast data to or from UE;
5. Network control mobility, including measurement.
