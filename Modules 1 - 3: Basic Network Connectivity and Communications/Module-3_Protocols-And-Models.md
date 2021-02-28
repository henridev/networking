# Protocols and Models

You know the basic components of a simple network, as well as initial configuration. But after you have configured and connected these components, how do you know they will work together? Protocols! Protocols are sets of agreed upon rules that have been created by standards organizations. But, because you cannot pick up a rule and look closely at it, how do you truly understand why there is such a rule and what it is supposed to do? Models! Models give you a way to visualize the rules and their place in your network. This module gives you an overview of network protocols and models. You are about to have a much deeper understanding of how networks actually work!

## 1. Protocols

### network protocol overview

You know that for end devices to be able to communicate over a network, each device must abide by the same set of rules. These rules are called **protocols** and they have many functions in a network. 

**Network protocols** 

- define a common format and set of rules for exchanging messages between devices. 

- Protocols are implemented by end devices and intermediary devices in software, hardware, or both. 

- *Each network protocol has its own function, format, and rules for communications.*

Protocol Types : 

- **Network Communications Protocols** = Protocols enable two or more devices to communicate over one or more networks. 
  - The Ethernet family of technologies involves a variety of protocols such as IP, Transmission Control Protocol (TCP), HyperText Transfer Protocol (HTTP), and many more.
- **Network security protocols** = Protocols secure data to provide authentication, data integrity, and data encryption.
  - Examples of secure protocols include Secure Shell (SSH), Secure Sockets Layer (SSL), and Transport Layer Security (TLS).
- **Routing protocols** = Protocols enable routers to exchange route information, compare path information, and then to select the best path to the destination network.
  - Examples of routing protocols include Open Shortest Path First (OSPF) and Border Gateway Protocol (BGP).
- **Service discovery protocols** = Protocols are used for the automatic detection of devices or services. 
  - Examples of service discovery protocols include Dynamic Host Configuration Protocol (DHCP) which discovers services for IP address allocation, and Domain Name System (DNS) which is used to perform name-to-IP address translation.



### network protocol functions

Network communication protocols are responsible for a variety of functions necessary for network communications between end devices. For example, in the figure how does the computer send a message, across several network devices, to the server?

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614421999/Screenshot_from_2021-02-27_11-33-06_nzgbae.png"/>

6 functions of protocols

- **addressing** = identifies  sender and receiver of the message via a defined addressing scheme. (Examples of protocols that provide addressing include Ethernet, IPv4, and IPv6.)
- **reliability** = guarantee delivery in case messages are lost or corrupted in transit. (TCP provides guaranteed delivery)
- **flow control** = ensure that data flows at efficiently between two communicating devices. (TCP provides flow control services.)
- **sequencing** = uniquely labels each transmitted segment of data. The receiving device uses the sequencing information to reassemble the information correctly. This is useful if the data segments are lost, delayed or received out-of-order. (TCP provides sequencing services.)
- **error detection** = used to determine if data became corrupted during transmission. Various protocols that provide error detection include Ethernet, IPv4, IPv6, and TCP
- **application interface** = contains information used for process-to-process communications between network applications. (For example, when accessing a web page, HTTP or HTTPS protocols are used to communicate between the client and server web processes.)

### Protocol Interaction

A message sent over a computer network typically requires the use of several protocols, each one with its own functions and format. The figure shows some common network protocols that are used when a device sends a request to a web server for its web page.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614422646/Screenshot_from_2021-02-27_11-43-34_jt71p2.png"/>

## 2. Protocol Suites

In many cases, protocols must be able to work with other protocols so that your online experience gives you everything you need for network communications. **Protocol suites** are designed to work with each other seamlessly.

**protocol suite = group of inter-related protocols necessary to perform a communication function.

> One of the best ways to visualize how the protocols within a suite interact is to view the interaction as a stack. 

**protocol stack** 

- shows how the individual protocols within a suite are implemented. 
- The protocols are viewed in terms of layers
  - each **higher-level** service depending on the functionality defined by the protocols shown in the lower levels. 
  - The **lower layers** of the stack are concerned with moving data over the network and providing services to the upper layers, which are focused on the content of the message being sent.

As illustrated in the figure, we can use layers to describe the activity occurring in face-to-face communication. At the bottom is the physical layer where we have two people with voices saying words out loud. In the middle is the rules layer that stipulates the requirements of communication including that a common language must be chosen. At the top is the content layer and this is where the content of the communication is actually spoken.

### evolution of protocol suites

**protocol suite** = set of protocols that work together to provide comprehensive network communication services. 

During the evolution of network communications and the internet there were several competing protocol suites, as shown in the figure.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614424165/Screenshot_from_2021-02-27_12-09-14_ilcicp.png"/>



### TCP/IP protocol example

- TCP/IP protocols are available for the application, transport, and internet layers. 
- There are no TCP/IP protocols in the **network access layer**. The most common network access layer LAN protocols are Ethernet and WLAN (wireless LAN) protocols. Network access layer protocols are responsible for delivering the IP packet over the physical medium.

The figure 

- example of the three TCP/IP protocols used to send packets between the web browser of a host and the web server.
- HTTP, TCP, and IP are the TCP/IP protocols used. 
- At the network access layer, Ethernet is used in the example. However, this could also be a wireless standard such as WLAN or cellular service.



<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614424439/Screenshot_from_2021-02-27_12-13-50_fnumra.png"/>

### TCP/IP protocol suite

this protocol suite is used by todays internet and network it has 2 important properties

- **open-standard protocol suite** = freely available and usable
- **standard-based protocol suit** = endorsed by networking industry and standards organizations

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614424632/Screenshot_from_2021-02-27_12-17-01_lju7iu.png"/>

---

**Application Layer**

Name System

- **DNS** - Domain Name System. Translates domain names such as cisco.com, into IP addresses.

Host Config

- **DHCPv4** - Dynamic Host Configuration Protocol for IPv4. A DHCPv4 server dynamically assigns IPv4 addressing information to DHCPv4 clients at start-up and allows the addresses to be re-used when no longer needed.
- **DHCPv6** - Dynamic Host Configuration Protocol for IPv6. DHCPv6 is similar to DHCPv4. A DHCPv6 server dynamically assigns IPv6 addressing information to DHCPv6 clients at start-up.
- **SLAAC** - Stateless Address Autoconfiguration. A method that allows a device to obtain its IPv6 addressing information without using a DHCPv6 server.

Email

- **SMTP** - Simple Mail Transfer Protocol. Enables clients to send email to a mail server and enables servers to send email to other servers.
- **POP3** - Post Office Protocol version 3. Enables clients to retrieve email from a mail server and download the email to the client's local mail application.
- **IMAP** - Internet Message Access Protocol. Enables clients to access email stored on a mail server as well as maintaining email on the server.

File Transfer

- **FTP** - File Transfer Protocol. Sets the rules that enable a user on one host to access and transfer files to and from another host over a network. FTP is a reliable, connection-oriented, and acknowledged file delivery protocol.
- **SFTP** - SSH File Transfer Protocol. As an extension to Secure Shell (SSH) protocol, SFTP can be used to establish a secure file transfer session in which the file transfer is encrypted. SSH is a method for secure remote login that is typically used for accessing the command line of a device.
- **TFTP** - Trivial File Transfer Protocol. A simple, connectionless file transfer protocol with best-effort, unacknowledged file delivery. It uses less overhead than FTP.

Web and Web Service

- **HTTP** - Hypertext Transfer Protocol. A set of rules for exchanging text, graphic images, sound, video, and other multimedia files on the World Wide Web.
- **HTTPS** - HTTP Secure. A secure form of HTTP that encrypts the data that is exchanged over the World Wide Web.
- **REST** - Representational State Transfer. A web service that uses application programming interfaces (APIs) and HTTP requests to create web applications.

---

**Transport layer**

Connection-Oriented

- **TCP** - Transmission Control Protocol. Enables reliable communication between processes running on separate hosts and provides reliable, acknowledged transmissions that confirm successful delivery.

Connectionless

- **UDP** - User Datagram Protocol. Enables a process running on one host to send packets to a process running on another host. However, UDP does not confirm successful datagram transmission.

---

**Internet Layer**

Internet Protocol

- **IPv4** - Internet Protocol version 4. Receives message segments from the transport layer, packages messages into packets, and addresses packets for end-to-end delivery over a network. IPv4 uses a 32-bit address.
- **IPv6** - IP version 6. Similar to IPv4 but uses a 128-bit address.
- **NAT** - Network Address Translation. Translates IPv4 addresses from a private network into globally unique public IPv4 addresses.

Messaging

- **ICMPv4** - Internet Control Message Protocol for IPv4. Provides feedback from a destination host to a source host about errors in packet delivery.
- **ICMPv6** - ICMP for IPv6. Similar functionality to ICMPv4 but is used for IPv6 packets.
- **ICMPv6 ND** - ICMPv6 Neighbor Discovery. Includes four protocol messages that are used for address resolution and duplicate address detection.

Routing Protocols

- **OSPF** - Open Shortest Path First. Link-state routing protocol that uses a hierarchical design based on areas. OSPF is an open standard interior routing protocol.
- **EIGRP** - EIGRP - Enhanced Interior Gateway Routing Protocol. An open standard routing protocol developed by Cisco that uses a composite metric based on bandwidth, delay, load and reliability.
- **BGP** - Border Gateway Protocol. An open standard exterior gateway routing protocol used between Internet Service Providers (ISPs). BGP is also commonly used between ISPs and their large private clients to exchange routing information.

---
**Network Access Layer**

Address Resolution

- **ARP** - Address Resolution Protocol. Provides dynamic address mapping between an IPv4 address and a hardware address.

  **Note**: You may see other documentation state that ARP operates at the Internet Layer (OSI Layer 3). However, in this course we state that ARP operates at the Network Access layer (OSI Layer 2) because it's primary purpose is the discover the MAC address of the destination. A MAC address is a Layer 2 address.

Data Link Protocols

- **Ethernet** - Defines the rules for wiring and signaling standards of the network access layer.
- **WLAN** - Wireless Local Area Network. Defines the rules for wireless signaling across the 2.4 GHz and 5 GHz radio frequencies.



## 3. Reference Models

### Benefits of a layered model

a layered model is used to modularize the operations of a network into manageable layers.

These are the benefits of using a layered model to describe network protocols and operations:

- Assisting in protocol design because protocols that operate at a specific layer have defined information that they act upon and a defined interface to the layers above and below
- Fostering competition because products from different vendors can work together
- Preventing technology or capability changes in one layer from affecting other layers above and below
- Providing a common language to describe networking functions and capabilities

As shown in the figure, there are two layered models that are used to describe network operations:

- **Open System Interconnection (OSI)** Reference Model
- **TCP/IP Reference Model**

<img src="http://fiberbit.com.tw/wp-content/uploads/2013/12/TCP-IP-model-vs-OSI-model.png"/>

### OSI reference model

- extensive list of functions and services that can occur at each layer. 
- This type of model provides consistency within all types of network protocols and services by **declarative description**  (what must be done at a particular layer) instead of imperative description (how it should be done)
- It also describes the interaction of each layer with the layers directly above and below. 
- The TCP/IP protocols discussed in this course are structured around both the OSI and TCP/IP models. 

The table shows details about each layer of the OSI model. The functionality of each layer and the relationship between layers will become more evident throughout this course as the protocols are discussed in more detail.

| **OSI Model Layer**  | **Description**                                              |
| :------------------- | :----------------------------------------------------------- |
| **7 - Application**  | protocols for process to process communication               |
| **6 - Presentation** | common representation of data transferred between application layer services |
| **5 - Session**      | provides services to presentation to organize its dialogue and to manage data exchange |
| **4 - Transport**    | services to segment / transfer and reassemble data for individual communications between end devices |
| **3 - Network**      | provides services to exchange the individual pieces of data over the network between identified end devices. |
| **2 - Data Link**    | methods for exchanging data frames between devices over common media |
| **1 - Physical**     | describes mechanical / electrical / functional and procedural means to activate / maintain and de-activate physical connections for bit transmission to and from network devices |

> OSI-model layers are often refereed to by layer number

### TCP/IP protocol model

The TCP/IP protocol model for internetwork communications was created in the early 1970s and is sometimes referred to as the internet model. This type of model closely matches the structure of a particular protocol suite. The TCP/IP model is a protocol model because it describes the functions that occur at each layer of protocols within the TCP/IP suite. TCP/IP is also used as a reference model. The table shows details about each layer of the OSI model.

| **4 - Application**    | Represents data to the user, plus encoding and dialog control. |
| ---------------------- | ------------------------------------------------------------ |
| **3 - Transport**      | Supports communication between various devices across diverse networks. |
| **2 - Internet**       | Determines the best path through the network.                |
| **1 - Network Access** | Controls the hardware devices and media that make up the network. |

### OSI vs TCP/IP model

The protocols that make up the TCP/IP protocol suite can also be described in terms of the OSI reference model. In the OSI model, the network access layer and the application layer of the TCP/IP model are further divided to describe discrete functions that must occur at these layers.

At the network access layer, the TCP/IP protocol suite does not specify which protocols to use when transmitting over a physical medium; it only describes the hand-off from the internet layer to the physical network protocols. OSI Layers 1 and 2 discuss the necessary procedures to access the media and the physical means to send data over a network.



differ in how layers relate to each-other

- direct mapping
  - OSI Layer 3 | TCP/IP Internet Layer 
  - OSI Layer 4 | TCP/IP Transport Layer 
- difference
  - OSI Layer 5 / 6 / 7  = references for application software developers and vendors to produce applications operating on networks
  - TCP/IP Transport Layer = specific functionality to variety of end-user applications
  - OSI Layer 1 / 2 
  - TCP / IP Network access 



## 4. data-encapsulation

### segmenting messages

Knowing the OSI reference model and the TCP/IP protocol model will come in handy when you learn about *how data is encapsulated as it moves across a network*. 

```javascript
const data = "a single communication, such as a video or an email + attachments"
data.send({via: "network"}) // in theory possible not good in practice
const problems = {
    overcrowded: "problems devices needing to use the same communication channels or links.",
    delay: "large streams of data would result in significant delays.",
    fail: "if link in interconnected network infrastructure fails during the transmission, the complete message would be lost and would have to be retransmitted in full."
}
const solution = "Segmentation" // the process of dividing a stream of data into smaller units for transmissions over the network. 

/**
Segmentation is necessary because data networks use the TCP/IP protocol suite send data in individual IP packets. 
Each packet is sent separately, similar to sending a long letter as a series of individual postcards. 
Packets containing segments for the same destination can be sent over different paths.
/**
```

This leads to **segmenting** messages having two primary benefits:

- **Increases speed** - Because a large data stream is segmented into packets, large amounts of data can be sent over the network without tying up a communications link. This allows many different conversations to be interleaved on the network called **multiplexing**.

- **Increases efficiency** -If a single segment is fails to reach its destination due to a failure in the network or network congestion, only that segment needs to be retransmitted instead of resending the entire data stream.

### sequencing

The challenge to using segmentation and multiplexing to transmit messages across a network is the level of complexity that is added to the process.  we need to reassemble the data in the proper order.

In network communications, each segment of the message must go through a similar process to ensure that it gets to the correct destination and can be reassembled into the content of the original message, as shown in the figure. **TCP** is *responsible for sequencing the individual segments.*

The figure shows two computers sending messages on a network to a server. Each message has been divided up into multiple pieces shown as yellow and orange envelopes, some are interleaved and numbered. 



<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614445295/Screenshot_from_2021-02-27_17-59-38_kh9pl2.png" width=400/>



### Protocol Data Units

encapsulation process = as application data passes the protocol stack to be transmitted across the network media, various protocol information is added at each level

**Note**: Although the UDP PDU is called **datagram**, IP packets are sometimes also referred to as IP datagrams.

The form that a piece of data takes at any layer is called a **protocol data unit (PDU)**. 

- During encapsulation, each succeeding layer encapsulates the PDU that it receives from the layer above in accordance with the protocol being used. 
- At each stage of the process, a PDU has a different name to reflect its new functions. 
- Although there is no universal naming convention for PDUs, in this course, the PDUs are named according to the protocols of the TCP/IP suite. The PDUs for each form of data are shown in the figure.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614447788/Screenshot_from_2021-02-27_18-42-57_ofsjia.png"/>

### (de-)encapsulation example

When messages are being sent on a network, the encapsulation process works from top to bottom. At each layer, the upper layer information is considered data within the encapsulated protocol. For example, the TCP segment is considered data within the IP packet.

This process is reversed at the receiving host and is known as de-encapsulation. De-encapsulation is the process used by a receiving device to remove one or more of the protocol headers. The data is de-encapsulated as it moves up the stack toward the end-user application.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614448147/Screenshot_from_2021-02-27_18-48-06_muc7le.png"/>

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614448147/Screenshot_from_2021-02-27_18-48-10_gbck0c.png"/>

## 5. Data-Access

### Addresses

in order to segment messages in a network => segmented messages need to be addressed properly with **network addresses**



<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614494034/cisco-netacad-Page-3_chq6ow.png"/>



### Layer 3 : Logical address 

- ip-address => network layer
- logical address is used to deliver an ip packet from original source to final destination
- 2 ip-addresses in the packet 
  - **source ip address** = ip address of device sending
  - **destination ip address** = ip address of device receiving
  - does not matter if they are on the same network or not
- 2 parts for an ip-address
  - **host portion / interface Id** => left part indicates network in which ip-address is located 
  - **network portion / Prefix** => right part indicates device on network 



<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614494631/cisco-netacad-Page-4_ujynyj.png"/>



### example on same network

In this example we have a client computer, PC1, communicating with an FTP server on the same IP network.

- **Source IPv4 address** - The IPv4 address of the sending device, the client computer PC1: *192.168.1*.110.
- **Destination IPv4 address** - The IPv4 address of the receiving device, FTP server: *192.168.1*.9.



```javascript
if((sender && receiver)ip_packet === network){
     send({data: "ethernet-data-link-frame", to: "receiving device"})
}

const data_link_addresses === "Ethernet Media Access Control Addresses (MAC)"
```



Mac Adresses

- physically embedded in the Ethernet NIC
- **source mac address** = the **data link address**  / **Ethernet MAC address**, of the device that sends the data link frame with the encapsulated IP packet. 
- **Destination MAC address** = When the receiving device is on the same network as the sending device, this is the data link address of the receiving device.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614495746/cisco-netacad-Page-5_fhyu1u.png"/>

> the destination MAC address is the MAC address of the FTP server: (X0-CC-CC-CC-CC-CC-CC)
>
> ``The MAC address of the Ethernet NIC is (X0-AA-AA-AA-AA-AA-AA)



### example devices on remote network

But what are the roles of the network layer address and the data link layer address when a device is communicating with a device on a remote network? In this example we have a client computer, PC1, communicating with a server, named Web Server, on a different IP network.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614496282/cisco-netacad-Page-6_ko9mib.png"/>

#### network layer address

```javascript
if((sender && receiver)ip_packet !== network){
     // cant sent direct to destination host because host not direct reachable in sender network
     send({data: "ethernet-data-link-frame", to: "**router or default gateway**"})
}

const data_link_addresses === "Ethernet Media Access Control Addresses (MAC)"
```

In our example, the default gateway is R1. R1 has an Ethernet data link address that is on the same network as PC1. This allows PC1 to reach the router directly.

- **Source MAC address** - The Ethernet MAC address of the sending device, PC1. The MAC address of the Ethernet interface of PC1 is AA-AA-AA-AA-AA-AA.
- **Destination MAC address** - When the receiving device, the destination IP address, is on a different network from the sending device, the sending device uses the Ethernet MAC address of the default gateway or router. In this example, the destination MAC address is the MAC address of the R1 Ethernet interface, 11-11-11-11-11-11. This is the interface that is attached to the same network as PC1, as shown in the figure.

The Ethernet frame with the encapsulated IP packet can now be transmitted to R1. R1 forwards the packet to the destination, Web Server. This may mean that R1 forwards the packet to another router or directly to Web Server if the destination is on a network connected to R1.

*It is important that the IP address of the default gateway be configured on each host on the local network*. All packets to a destination on remote networks are sent to the default gateway. Ethernet MAC addresses and the default gateway are discussed in more detail in other modules.

#### data-link address

Role: deliver the data link frame from one network interface to another network interface on the same network.

Before an IP packet can be sent over a wired or wireless network, **it must be encapsulated in a data link frame, so it can be transmitted over the physical medium.**

As the IP packet travels

- host-to-router
- router-to-router
- router-to-host

each point along the way the IP packet is encapsulated in a new data link frame. Each data link frame contains the source data link address of the NIC card sending the frame, and the destination data link address of the NIC card receiving the frame.

The Layer 2, data link protocol is only used to deliver the packet from NIC-to-NIC on the same network. The router removes the Layer 2 information as it is received on one NIC and adds new data link information before forwarding out the exit NIC on its way towards the final destination.

The IP packet is encapsulated in a data link frame that contains the following data link information:

- **Source data link address** - The physical address of the NIC that is sending the data link frame.
- **Destination data link address** - The physical address of the NIC that is receiving the data link frame. This address is either the next hop router or the address of the final destination device.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614497225/cisco-netacad-Page-7_gfyotr.png"/>

