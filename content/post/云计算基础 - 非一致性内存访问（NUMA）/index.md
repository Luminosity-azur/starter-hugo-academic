---
title: Cloud Computing - Non-Uniform Memory Access (NUMA)
subtitle: This post is a basic introduction to the background and technical characteristics of NUMA.

# Summary for listings and search engines
summary: This post is a basic introduction to the background and technical characteristics of NUMA.

tags: 
- Cloud Computing

categories: 
- Cloud Computing

date: '2022-06-04'
math: true
---
### Three system architectures & Two memory sharing methods
From the perspective of system architecture, the current commercial servers can be broadly divided into three categories:

1. Symmetric Multi-Processor (SMP)
2. Non-Uniform Memory Access (NUMA)
3. Massive Parallel Processing (MPP)

There are two technologies for shared memory multiprocessors:

1. Uniform-Memory-Access (UMA)
2. Nonuniform-Memory-Access (NUMA)

### Uniform-Memory-Access (UMA)
UMA is a shared memory architecture in parallel computers, that is, physical memory is shared uniformly by all processors and has the same access time for all stored words. Each processor can have a private cache, and peripheral devices can also be shared in some form. UMA technology is suitable for applications with common requirements and multi-user shared time. In applications with strict timing requirements, it is used to accelerate the execution rate of a single large-scale program.

### Nonuniform-Memory-Access (NUMA)
NUMA is a memory design used in multiprocess computing, and the memory reading depends on the association between the current memory and the processor. Under NUMA technology, a processor accesses local memory faster than non-local memory (local memory of another processor or memory shared by the processor).

### Virtual Nonuniform-Memory-Access (vNUMA)
vNUMA eliminates the transparency between the VM and the operating system, and directly connects the NUMA architecture to the operating system of the VM. It is worth mentioning that vNUMA is as famous as NUMA in the industry. For a wide range of VM technologies, the underlying architecture of VM operation, the NUMA topology of VM spans multiple NUMA nodes. After the initial function of vNUMA enabled VM, the architecture presented to the operating system is permanently defined and cannot be modified. This limitation is usually positive, because changing the vNUMA architecture may lead to instability of the operating system, but if the VM migrates to a hypervisor with a different NUMA architecture through vMotion, it may cause performance problems. It is worth mentioning that although most applications can use vNUMA, most VMS are small enough to load NUMA nodes; Recent optimizations to wide-VM support or vNUMA do not affect them.

Therefore, how the guest operating system or its application places processes and memory can significantly affect performance. The advantage of exposing NUMA topology to VM is that it allows users to make optimal decisions according to the underlying NUMA architecture. By assuming that the user operating system will make the best decisions in the exposed vNUMA topology, rather than inserting memory between NUMA clients.


### Importance of NUMA
Multithreaded applications need to access the local memory of the CPU core. When it must use remote memory, the performance will be affected by the delay. Accessing remote memory is much slower than accessing local memory. So using NUMA will improve performance. Modern operating systems attempt to schedule processes on NUMA nodes (local memory + local CPU = NUMA nodes), and processes will use local NUMA nodes to access the core. ESXi also uses NUMA technology for a wide range of virtual machines. When the virtual core is greater than 8, the virtual core is distributed on multiple NUMA nodes. When the machine starts, the virtual core will be distributed to different NUMA nodes, which will improve performance because the virtual core will access local memory.


### summary
When more virtual sockets are allocated to a virtual kernel, or more virtual cores are allocated to a virtual socket, the difference does not affect the number of NUMA nodes. Virtual sockets only affect software licenses, not performance.