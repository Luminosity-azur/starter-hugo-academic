---
title: Cloud Computing - High Availability (HA)
subtitle: This post mainly explains the concept and working mode of HA.

# Summary for listings and search engines
summary: This post mainly explains the concept and working mode of HA.

tags: 
- Cloud Computing

categories: 
- Cloud Computing

date: '2022-05-23'
math: true
---
### Definition of High Availability (HA)
"High availability" usually describes that a system is specially designed to reduce downtime and maintain high availability of its services.

For example, we hope that power and hydraulic services are highly available systems.
The reliability of computer system is measured by mean time between failures (MTTF), that is, how long the computer system can operate normally before a failure occurs. The higher the reliability of the system, the longer the mean time between failures. Maintainability is measured by mean time to repair (MTTR), i.e. the average time taken to repair and restore normal operation after system failure. The better the maintainability of the system, the shorter the average maintenance time. The availability of computer system is defined as: MTTF / (MTTF + MTTR) * 100%. It can be seen that the availability of a computer system is defined as the percentage of the normal operation time of the system.

### 负载均衡服务器的高可用性 
　　为了屏蔽负载均衡服务器的失效，需要建立一个备份机。主服务器和备份机上都运行High Availability监控程序，通过传送诸如“I am alive”这样的信息来监控对方的运行状况。当备份机不能在一定的时间内收到这样的信息时，它就接管主服务器的服务IP并继续提供服务；当备份管理器又从主管理器收到“I am alive”这样的信息是，它就释放服务IP地址，这样的主管理器就开开始再次进行集群管理的工作了。为在主服务器失效的情况下系统能正常工作，我们在主、备份机之间实现负载集群系统配置信息的同步与备份，保持二者系统的基本一致。
### HA的容错备援运作过程 
#### 自动侦测(Auto-Detect)阶段
由主机上的软件通过冗余侦测线，经由复杂的监听程序。逻辑判断，来相互侦测对方运行的情况，所检查的项目有：主机硬件(CPU和周边)、主机网络、主机操作系统、数据库引擎及其它应用程序、主机与磁盘阵列连线。为确保侦测的正确性，而防止错误的判断，可设定安全侦测时间，包括侦测时间间隔，侦测次数以调整安全系数，并且由主机的冗余通信连线，将所汇集的讯息记录下来，以供维护参考。 
#### 自动切换(Auto-Switch)阶段 
某一主机如果确认对方故障，则正常主机除继续进行原来的任务，还将依据各种容错备援模式接管预先设定的备援作业程序，并进行后续的程序及服务。 
#### 自动恢复(Auto-Recovery)阶段
在正常主机代替故障主机工作后，故障主机可离线进行修复工作。在故障主机修复后，透过冗余通讯线与原正常主机连线，自动切换回修复完成的主机上。整个回复过程完成由EDI-HA自动完成，亦可依据预先配置，选择回复动作为半自动或不回复。
　
### HA三种工作方式： 
　　（1）主从方式 （非对称方式） 
　　工作原理：主机工作，备机处于监控准备状况；当主机宕机时，备机接管主机的一切工作，待主机恢复正常后，按使用者的设定以自动或手动方式将服务切换到主机上运行，数据的一致性通过共享存储系统解决。 
　　（2）双机双工方式（互备互援） 
　　工作原理：两台主机同时运行各自的服务工作且相互监测情况，当任一台主机宕机时，另一台主机立即接管它的一切工作，保证工作实时，应用服务系统的关键数据存放在共享存储系统中。 
　　（3）集群工作方式（多服务器互备方式） 
　　工作原理：多台主机一起工作，各自运行一个或几个服务，各为服务定义一个或多个备用主机，当某个主机故障时，运行在其上的服务就可以被其它主机接管。
　　 
### 高可用性的衡量指标 
　　可用性的计算公式： 
　　％availability＝（Total Elapsed Time－Sum of Inoperative Times）/ Total Elapsed Time 
　　elapsed time为operating time＋downtime。 
　　可用性和系统组件的失败率相关。衡量系统设备失败率的一个指标是“失败间隔平均时间”MTBF（mean time between failures）。通常这个指标衡量系统的组件，如磁盘。 
　　MTBF＝Total Operating Time / Total No. of Failures 
　　Operating time为系统在使用的时间（不包含停机情况）。 
### 高可用性系统的设计 
　　设计系统的可用性，最重要的是满足用户的需求。系统的失败只有当其导致服务的失效性足以影响到系统用户的需求时才会影响其可用性的指标。用户的敏感性决定于系统提供的应用。例如，在一个能在1秒钟之内被修复的失败在一些联机事务处理系统中并不会被感知到，但如果是对于一个实时的科学计算应用系统，则是不可被接受的。 
　　系统的高可用性设计决定于您的应用。例如，如果几个小时的计划停机时间是可接受的，也许存储系统就不用设计为磁盘可热插拔的。反之，你可能就应该采用可热插拔、热交换和镜像的磁盘系统。 
　　所以涉及高可用系统需要考虑： 
　　决定业务中断的持续时间。根据公式计算出的衡量HA的指标，可以得到一段时间内可以中断的时间。但可能很大量的短时间中断是可以忍受的，而少量长时间的中断却是不可忍受的。 
　　在统计中表明，造成非计划的宕机因素并非都是硬件问题。硬件问题只占40％，软件问题占30％，人为因素占20％，环境因素占10％。您的高可用性系统应该能尽可能地考虑到上述所有因素。 
　　当出现业务中断时，尽快恢复的手段。 
### 导致计划内的停机因素有： 
　　周期性的备份 
　　软件升级 
　　硬件扩充或维修 
　　系统配置更改 
　　数据更改 
### 导致计划外停机的因素有： 
　　硬件失败 
　　文件系统满错误 
　　内存溢出 
　　备份失败 
　　磁盘满 
　　供电失败 
　　网络失败 
　　应用失败 
　　自然灾害 
　　操作或管理失误 
　　通过有针对性的设计，可以避免上述全部或部分因素带来的损失。当然，100％的高可用系统是不存在的。 
### 创建高可用性的计算机系统 
　　在UNIX系统上创建高可用性计算机系统，业界的通行做法，也是非常有效的做法，就是采用群集系统（Cluster），将各个主机系统通过网络或其他手段有机地组成一个群体，共同对外提供服务。创建群集系统，通过实现高可用性的软件将冗余的高可用性的硬件组件和软件组件组合起来，消除单点故障： 
　　消除供电的单点故障 
　　消除磁盘的单点故障 
　　消除SPU（System Process Unit）单点故障 
　　消除网络单点故障 
　　消除软件单点故障 
　　尽量消除单系统运行时的单点故障