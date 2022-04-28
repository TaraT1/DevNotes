---
id: 6sfcivq9mfe4o0rxku6shsq
title: tcp
desc: ''
updated: 1650388609563
created: 1650085213858
---
# TCP/IP
- refers to the two main protocols Transmission Control Protocol (TCP) and Internet Protocol (IP).
- a suite of communication protocols that is used to connect devices and transfer data over the Internet.

TCP/IP uses:
	• IP addresses: An IP address identifies the location of a computer on a network.
	• Ports: A port is a location on the recipient computer, where data is received.
While an IP address tells you where to find a particular computer, it doesn't tell you specifically where on that computer a particular connection should be made—that's what port numbers are for.

• Port 80: The port number most commonly used for HTTP requests. For example, when a client makes a request to a web server, this request is usually sent through port 80.
• Port 5432: The port number used by most database systems; default port for Postgres.

Ports are much like the different terminals of an airport, tracking and receiving different airplanes at the same time, allowing for the effective receipt of multiple types of traffic at the same IP address.

[Common network ports](https://opensource.com/article/18/10/common-network-ports)

[free networking course]( https://www.udacity.com/course/computer-networking--ud436)

## Connections & Sessions in TCP/IP
- TCP/IP is a connection based protocol - all comms are arranged over connection
- session - start & end connection
	- more connections increases risk of problems
	- transactions continually committed to db
	- deliveries over connection are error-checked; if packets are damaged or lost, they are resent (retransmission)
	
## UDP protocol 
- simpler than TCP; hosts on network send data in datagrams w/o any connections needing to be established

## TDP vs UDP
- TDP like highway. Built before sending packages
- UDP delivers (or not) w/o feedback. Fewer delays than TCP. Real time streaming apps (VOIP, live TV streaming) since not retransmit lost datagrams
- TCP's continuous connection is more reliable and has more latency
- Databases are interacted using client-server interactions, over a network
- Postgres uses TCP/IP to be interacted with, which is connection-based
- We interact with databases like Postgres during sessions
- Sessions have transactions that commit work to the database
- Transactions capture logical bundles of work.
Work is bundled into transactions, so that in case of system failures, data in your database is still kept in a valid state (by rolling back the entire transaction if any part of it fails). 