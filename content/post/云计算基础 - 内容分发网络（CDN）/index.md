---
title: Cloud Computing - Content Delivery Network (CDN)
subtitle: This post is an explanation of CDN.

# Summary for listings and search engines
summary: This post is an explanation of CDN.

tags: 
- Cloud Computing

categories: 
- Cloud Computing
date: '2022-07-06'
math: true
---
### Overview
The full name of CDN is Content Delivery Network. Its purpose is to add a new layer of network architecture to the existing Internet, publish the content of the website to the network edge closest to the user, enable the user to obtain the required content nearby, and improve the response speed of the user when visiting the website. CDN is different from mirroring because it is more intelligent than mirroring. Or we can use a metaphor: CDN = more intelligent mirroring + caching + traffic diversion. Therefore, CDN can obviously improve the efficiency of information flow in Internet network. Technically, it comprehensively solves the problems of small network bandwidth, large number of users and uneven distribution of outlets, and improves the response speed of users visiting websites.

To better understand CDN, let's take a look at the CDN workflow:
When a user visits a website that has joined the CDN service, the best CDN node closest to the user is first determined through DNS redirection technology, and the user's request is directed to the node. When the user's request reaches the designated node, the CDN server (Cache on the node) is responsible for providing the content requested by the user to the user. The specific process is as follows: the user inputs the domain name of the website to be visited in his browser, the browser requests the local DNS to resolve the domain name, and the local DNS sends the request to the main DNS of the website. The main DNS determines the most appropriate CDN node at that time according to a series of policies, and sends the resolution result (IP address) to the user. The user requests the content of the corresponding website from the given CDN node.

Due to the performance bottleneck of users accessing the source service, the content of the source station is cached to multiple nodes through CDN technology. When a user makes a request to the domain name of the source site, the request will be dispatched to the service node closest to the user, and the service node will respond directly and quickly, effectively reducing the user's access delay and improving the availability.

The advantages of CDN are obvious:
(1) The CDN node solves the problem of cross operator and cross region access, and the access delay is greatly reduced;
(2) Most requests are completed at the edge nodes of the CDN. The CDN plays a role of shunting and alleviates the load of the source station.

### Related technologies
The implementation of CDN needs the support of many network technologies, among which load balancing technology, dynamic content distribution and replication technology and cache technology are the main ones

#### Load balancing technology
Load balancing technology is not only applied in CDN, but also widely used in many fields of the network, such as server load balancing and network traffic load balancing.

As the name implies, load balancing in the network is to distribute the network traffic to several servers or network nodes that can complete the same tasks as evenly as possible, so as to avoid overload of some network nodes. This can not only improve the network traffic, but also improve the overall performance of the network.

In CDN, load balancing is divided into server load balancing and server overall load balancing (also known as server global load balancing). Server load balancing refers to the ability to allocate tasks among servers with different performance, which can not only ensure that servers with poor performance do not become the bottleneck of the system, but also ensure that the resources of servers with high performance are fully utilized. While the overall server load balancing allows Web hosting providers, portal sites and enterprises to distribute content and services according to geographical location. Improve fault tolerance and availability by using multi site content and services to prevent failures caused by local network or regional network interruption, power failure or natural disasters. In the CDN scheme, the overall load balancing of the server will play an important role, and its performance will directly affect the performance of the entire CDN.

#### Dynamic content distribution and replication technology
As we all know, the response speed of website access depends on many factors, such as whether there is a bottleneck in the bandwidth of the network, whether there is congestion and delay in the route during transmission, the processing capacity of the website server and the access distance. In most cases, the response speed of the website is closely related to the distance between the visitor and the website server. If the distance between the visitors and the website is too long, the communication between them needs to go through heavy routing and processing, and network delay is inevitable.

An effective method is to use content distribution and replication technology to distribute and copy most of the static web pages, images and streaming media data that account for the main body of the website to the acceleration nodes in various places. Therefore, dynamic content distribution and replication technology is also a major technology required by CDN.

#### Cache technology
Cache technology is not a new technology. Web caching services improve the response time of users in several ways, such as proxy caching services, transparent proxy caching services, and transparent proxy caching services using redirection services. Through the Web cache service, users can minimize the traffic of the WAN when accessing the Web page. For corporate intranet users, this means that the content is cached locally, instead of retrieving Web pages through a dedicated Wan. For Internet users, this means storing content in the cache of their ISP without having to retrieve web pages over the Internet. This will undoubtedly improve the access speed of users. The core role of CDN is to improve the access speed of the network. Therefore, cache technology will be another major technology adopted by CDN.