---
title: WSN nodes location
subtitle: This is a brief summary of my research on WSN node location algorithms.

# Summary for listings and search engines
summary: This is a brief summary of my research on WSN node location algorithms.

# Link this post with a project
projects: []

# Date published
date: '2022-07-30T00:00:00Z'

# Date updated
lastmod: '2022-07-30T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

authors:
  - admin

tags: 
  - IoT

math: true
---

## Introduction
- In the 5G network architecture, IoT will interconnect devices with various potentials during the identical heterogeneous network
- Wireless Sensor Networks (WSN) is the core technology of the IoT.
- Large-scale WSN positioning in the IoT, that is, to locate unknown nodes through the information of known nodes, is a key technology to solve entity position problems in specific environments (such as environmental monitoring and intrusion positioning)
<div align="center">
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/bcd351f97c3bde61.png' >
</div>

## Preliminary
### Particle Swarm Optimization

<div align="center">
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/d19978fa47cbcef5.gif' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/b91daec2dfc70f55.png' >

- High efficiency, good robustness and easy convergence.
- But easy to fall into local optimization
</div>

### Simulated Annealing

<div align="center">
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/808fdcc73d267404.gif' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/9f30bda77acec3c2.png' >

- Can jump out of the local optimal solution with a certain probability
</div>

## Methodology
- Introduce the SA algorithm to break through the local optimal characteristics
- Improve the acceptance process of PSO algorithm in individual extreme value update

<div align="center">
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/529bb1c584512295.png' >
</div>


## Experiments & Discussions

<div align="center">
<img src = 'https://s3.bmp.ovh/imgs/2022/08/21/d745d1d344c64e83.png' >
</div>

<div align="center">
SA-PSO vs Traditional PSO

- Faster convergence
- Better coverage
- More reasonable positioning
</div>

## Critical Analysis

1. Existing Flaws
- PSO traditional inertia weight
- PSO fixer learning Factor
- SA inner loop

2. Improvement Directions
- PSO dynamic inertia weight
- PSO contraction learning factor
- SA inner loop with adaptive sampling stability condition
- Large scale node location (number, range) conditions should be considered (**already in the experimental process...**)