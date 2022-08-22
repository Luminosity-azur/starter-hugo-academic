---
title: R&D - OAM
subtitle: 本文为对无线轨道角动量复用原理相关研究的整理。

# Summary for listings and search engines
summary: 本文为对无线轨道角动量复用原理相关研究的整理。

# Link this post with a project
projects: []

# Date published
date: '2021-7-16T'

authors:
  - admin

tags:
  - R&D
  - OAM

categories:
  - R&D

math: true
---

## 研究背景
随着第一代移动通信网络到第五代移动通信网络的发展，为了应对容量需求的增长，业界分别提出了基于时间、频率、码字和空间等正交资源的复用通信技术。随着通信技术的进一步发展，在未来的第六代移动通信系统中将会面临更高的容量需求，是否存在新的自由度资源？答案是有的，近年来，基于轨道角动量的模态资源被认为是一种全新的空间自由度。本文聚焦轨道角动量无线通信，研究其模式复用的问题。

<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/8b00db2efb31ce8e.png' >


## OAM的定义

角动量是由自旋角动量（Spin Angular Momentum，SAM）和轨道角动量（Orbital Angular Momentum，OAM）组成的。自旋角动量仅与光子的自旋有关，表现为圆偏振状态。轨道角动量表示电子绕传播轴旋转，是由能量流（由坡印廷矢量描述）围绕光轴旋转而产生的，它使电磁波的相位波前呈涡旋状，因此，携带有轨道角动量的电磁波也被称为涡旋电磁波。

<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/2c9fe1872d81d56d.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/c01c64d995fe3b8c.png' >

## OAM相关特性
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/5ff356d4b9945b8e.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/b698178a57c2dceb.png' >

## OAM-MIMO
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/9c0def5156d6ed82.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/850eaa80c4583505.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/128654addabddef2.png' >

## 常见接收模型分析
<img src = 'https://s3.bmp.ovh/imgs/2022/08/19/c27694ef4e5d9803.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/3fe4ddbbae3640f6.png' >

## 模型性能分析
接下来是仿真部分，首先是倾斜模型仿真结果分析，图中表示系统容量随着倾斜角度变化关系，可以看出随着倾斜角度的增加，信道容量呈整体下降趋势。
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/5d42b258f6e311a0.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/1e9bddffc0c9592c.png' >

## 一般模型信道矩阵求解方法
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/7ad6324ed50b4702.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/f6941e36ac8b729a.png' >
<img src = 'https://s3.bmp.ovh/imgs/2022/08/20/0401cda972003aad.png' >

## 推荐阅读参考文献
[1]廖希,周晨虹,王洋,廖莎莎,周继华,张杰.面向无线通信的轨道角动量关键技术研究进展[J].电子与信息学报,2020,42(7):1666-1677.
[2]ChenR,ZhouH,MorettiM,WangXD,andLiJD.Orbitalangularmomentumwaves:Generation,detection,andemergingapplications[J].IEEECommunicationsSurveysandTutorials,2019,22(2):840-868.