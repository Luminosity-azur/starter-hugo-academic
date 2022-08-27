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

### HA of load balancing server
In order to shield the failure of the load balancing server, a backup machine needs to be established. Both the primary server and the backup machine run the High Availability monitoring program to monitor the health of each other by transmitting information such as "I am alive". When the backup machine cannot receive such information within a certain time, it takes over the service IP of the primary server and continues to provide services; When the backup manager receives the message "I am alive" from the primary manager again, it releases the service IP address, and the primary manager starts to perform cluster management again. In order to enable the system to work normally in the event of failure of the primary server, we synchronize and backup the configuration information of the load cluster system between the primary and backup machines to maintain the basic consistency of the two systems.

### Fault tolerant backup operation process of HA
#### Auto-Detect phase
The software on the host passes through the redundant detection line and through the complex monitoring program. Logical judgment is used to detect each other's operation. The items to be checked include: host hardware (CPU and peripheral), host network, host operating system, database engine and other application programs, host and disk array connection. In order to ensure the correctness of detection and prevent wrong judgment, the safety detection time can be set, including the detection time interval and the detection times to adjust the safety factor, and the redundant communication connection of the host computer records the collected information for maintenance reference.
#### Auto-Switch phase
If a host confirms the fault of the other side, the normal host will not only continue the original task, but also take over the preset backup operation procedures according to various fault-tolerant backup modes, and carry out subsequent procedures and services.
#### Auto-Recovery phase
After the normal host works instead of the fault host, the fault host can be repaired offline. After the fault host is repaired, connect with the original normal host through the redundant communication line and automatically switch back to the repaired host. The whole reply process is completed automatically by EDI-HA, and the reply action can be selected as semi-automatic or no reply according to the pre configuration.

### Three working modes of HA:
1. Master slave mode (asymmetric mode)
Working principle: the main machine is working and the standby machine is in the monitoring preparation state; When the host is down, the standby machine will take over all the work of the host. After the host is restored to normal, the service will be switched to the host automatically or manually according to the user's settings. The data consistency will be solved through the shared storage system.
2. Dual machine duplex mode (mutual standby and mutual assistance)
Working principle: two hosts run their own service work at the same time and monitor each other. When either host goes down, the other host immediately takes over all its work to ensure real-time work. The key data of the application service system is stored in the shared storage system.
3. Cluster working mode (multi server mutual backup mode)
Working principle: multiple hosts work together, each running one or several services, and each defining one or more standby hosts for the service. When a host fails, the services running on it can be taken over by other hosts.
　　 
### Measures of HA
calculation formula:
％availability＝（Total Elapsed Time－Sum of Inoperative Times）/ Total Elapsed Time
where elapsed time = operating time＋downtime.
Availability is related to the failure rate of system components. An indicator to measure the failure rate of system equipment is MTBF (mean time between failures). Usually this metric measures the components of the system, such as disks.
MTBF＝Total Operating Time / Total No. of Failures 
where Operating time is the time the system is in use (excluding downtime).

### Design of HA system
To design the usability of the system, the most important thing is to meet the needs of users. The failure of the system will affect the availability index only when the service failure is enough to affect the needs of the system users. The sensitivity of the user depends on the application provided by the system. For example, a failure that can be repaired within 1 second will not be perceived in some online transaction processing systems, but it is unacceptable for a real-time scientific computing application system.
The high availability design of the system depends on your application. For example, if a planned downtime of several hours is acceptable, the storage system may not be designed to be disk hot swappable. Instead, you might want to use a disk system that can be hot swapped, hot swapped, and mirrored.
Therefore, the high availability system needs to consider:
Determine the duration of business interruption. According to the index of measuring ha calculated by the formula, the interruptible time in a period of time can be obtained. However, it is possible that a large number of short-time interrupts are tolerable, while a small number of long-time interrupts are intolerable.
Statistics show that not all unplanned downtime factors are hardware problems. Hardware problems only account for 40%, software problems account for 30%, human factors account for 20%, and environmental factors account for 10%. Your high availability system should take all of the above factors into account as much as possible.

### Factors leading to planned downtime
- Periodic backup
- Software upgrade
- Hardware expansion or maintenance
- System configuration changes
- Data change

### Factors leading to unplanned downtime 
- Hardware failure
- File system full error
- Memory overflow
- Backup failed
- Disk full
- Power supply failure
- Network failure
- Application failed
- natural disaster
- Operation or management error
Through targeted design, losses caused by all or part of the above factors can be avoided. Of course, 100% highly available systems do not exist.

### Create a highly available computer system
Creating a high availability computer system on UNIX system is a common and effective practice in the industry, that is, using Cluster system to organically form a group of host systems through network or other means to provide services to the outside world. Create a Cluster system, and combine redundant hardware components and software components with high availability through software that realizes high availability to eliminate single point of failure:

- Eliminate single point failure of power supply
- Eliminate single point of failure of disk
- Eliminate single point of failure of SPU (system Process Unit)
- Eliminate network single point of failure
- Eliminate software single point of failure
- Try to eliminate single point of failure during single system operation