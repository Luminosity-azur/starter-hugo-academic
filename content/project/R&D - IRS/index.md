---
title: IRS

# Summary for listings and search engines
summary: This paper combs the basic contents of IRS.

# Link this post with a project
projects: []

# Date published
date: '2021-07-23'

# Date updated
lastmod: '2021-07-23'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

authors:
  - admin

tags:
  - Millimeter wave communication

math: true

image:
  focal_point: Smart
---

This paper combs the basic contents of IRS.

## Research Background
### Proposal and new changes of 6G
1. Future applications have higher requirements for communication systems: storage capacity; Data rate, communication reliability, etc. Including the possible large-scale industrial Internet of things in the future, the requirements of the Internet of vehicles have not been fully met

2. Although 5G technology has been developed, there are still many deficiencies in cost, energy consumption and design complexity, and there are certain problems in practical application


**The IRS actively changes the wireless channel from bottom to top, instead of passively adapting**

## Basic concepts of IRS
The most fundamental difference from the current technology is reflecting. In essence, the current technology is based on the concept of transmission and reception rather than reflection.

Intelligent in IRS is two-sided:
- The intelligent reflection unit is reconfigurable in hardware;
- The signal processing, beamforming, artificial intelligence and convex optimization design related to IRS are also intelligent in software.

<br/>
<br/>

---

## Structure of IRS
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/0620bae9c0dbefdd.png' >

The first layer is a surface directly in contact with the electromagnetic wave, and there are many reflection units on it. The direction of the incident wave can be adjusted by controlling the reflection phase of the reflection units;

The second layer is the contact back plate, which is mainly used to prevent the leakage of electromagnetic wave signals behind the reflection surface and improve the reflection efficiency;

The third layer is used to modulate the reflection surface and the controller. The controller can be made of FPGA, **adjust the phase of the reflection unit on the reflection surface by controlling the output signal** Or the controller (by installing some sensors) can also be used for environmental sensing, which can help the reflective surface to switch between the reflective mode and intelligent sensing. For example, the reflection unit is composed of a diode. By adjusting the bias voltage of the diode, the switching of 1-bit phase (such as 0 and π) can be achieved.

<br/>
<br/>

---

## Beam shaping of IRS
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/640c1b9c562ba4ab.png' >

The above adaptive beamforming needs to control each reflection unit, so it needs to consume a certain amount of energy. However, unlike the existing MIMO, it does not require any radio frequency link.

Each reflection unit is like a point source and emits the received signal

<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/78a13fecd91ff88b.png' >

1. The maximum amplitude of the reflection unit is 1, because it is passive and will not be amplified. The amplitude of 0 is sparse reflection; The amplitude of 1 is total reflection.
2. We generally hope that the reflection phase can be continuously taken between 0-2 π; However, considering the cost and feasibility in practical application, discrete values can be taken.
3. For the whole reflection matrix, it is in diag form; Because each reflection unit has an independent influence on the reflected signal.


<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/9186ac341fc32dd5.png' >
The above is the introduction of IRS discrete amplitude and phase shift.
The general discrete ideas are: uniform quantization. However, even quantization is not necessarily optimal, depending on the actual application scenario. For example, when the reflection amplitude is given 1 bit, the discrete value (0, 1) or (0.5, 1) shall be taken according to the channel statistical characteristics.

- Phased reflector : fixed amplitude, phase shift quantization 
- Amplitude control reflector : phase fixed, amplitude quantization
  
In comparison, the complexity of amplitude controlled reflector is lower.


<br/>
<br/>

---


## Path loss of IRS
In IRS, the formula of path loss is the first;
The second one is only applicable to the infinity of the reflection surface (the IRS is used to study the signal reflection of a single reflection unit, so it cannot be considered as infinity) and is not applicable to the phase / amplitude controlled IRS
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/75ba0dd35559b42d.png' >


<br/>
<br/>

---


## Application of IRS
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/6c55aa0f6a01bd6a.png' >
The above applications have improved the coverage rate of communication: IRS can bypass obstacles for communication and will be widely used in future high-frequency communication. Like mmWave, the frequency increases and the wavelength decreases. The high-frequency wave is sensitive to the barrier effect of obstacles, and the performance can be improved with the help of IRS.