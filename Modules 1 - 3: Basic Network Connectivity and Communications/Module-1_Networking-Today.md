# Module 1: Networking Today

**Networks Affect our Lives**

In today’s world, through the use of networks, we are connected like never before. People with ideas can communicate instantly with others to make those ideas a reality. The creation of online communities for the exchange of ideas and information has the potential to increase productivity opportunities across the globe. The creation of the cloud lets us store documents and pictures and access them anywhere, anytime.

**Network Components**

All computers that are connected to a network and participate directly in network communication are classified as hosts. Hosts can be called end devices. Some hosts are also called clients. Many computers function as the servers and clients on the network. This type of network is called a peer-to-peer network. An end device is either the source or destination of a message transmitted over the network. Intermediary devices connect the individual end devices to the network and can connect multiple individual networks to form an internetwork. Intermediary devices use the destination end device address, in conjunction with information about the network interconnections, to determine the path that messages should take through the network. The media provides the channel over which the message travels from source to destination.

**Network Representations and Topologies**

Diagrams of networks often use symbols to represent the different devices and connections that make up a network. A diagram provides an easy way to understand how devices connect in a large network. This type of “picture” of a network is known as a topology diagram. Physical topology diagrams illustrate the physical location of intermediary devices and cable installation. Logical topology diagrams illustrate devices, ports, and the addressing scheme of the network.

**Common Types of Networks**

Small home networks connect a few computers to each other and to the internet. The small office/home office (SOHO) network allows computers in a home office or a remote office to connect to a corporate network, or access centralized, shared resources. Medium to large networks, such as those used by corporations and schools, can have many locations with hundreds or thousands of interconnected hosts. The internet is a network of networks that connects hundreds of millions of computers world-wide. The two most common types of network infrastructures are Local Area Networks (LANs), and Wide Area Networks (WANs). A LAN is a network infrastructure that spans a small geographical area. A WAN is a network infrastructure that spans a wide geographical area. Intranet refers to a private connection of LANs and WANs that belongs to an organization. An organization may use an extranet to provide secure and safe access to individuals who work for a different organization but require access to the organization’s data.

**Internet Connections**

SOHO internet connections include cable, DSL, Cellular, Satellite, and Dial-up telephone. Business internet connections include Dedicated Leased Line, Metro Ethernet, Business DSL, and Satellite. The choice of connection varies depending on geographical location and service provider availability. Traditional separate networks used different technologies, rules, and standards. Converged networks deliver data, voice, and video between many different types of devices over the same network infrastructure. This network infrastructure uses the same set of rules, agreements, and implementation standards. Packet Tracer is a flexible software program that lets you use network representations and theories to build network models and explore relatively complex LANs and WANs.

**Reliable Networks**

The term network architecture refers to the technologies that support the infrastructure and the programmed services and rules, or protocols, that move data across the network. As networks evolve, we have learned that there are four basic characteristics that network architects must address to meet user expectations: Fault Tolerance, Scalability, Quality of Service (QoS), and Security. A fault tolerant network is one that limits the number of affected devices during a failure. Having multiple paths to a destination is known as redundancy. A scalable network expands quickly to support new users and applications. Networks are scalable because the designers follow accepted standards and protocols. QoS is a primary mechanism for managing congestion and ensuring reliable delivery of content to all users. Network administrators must address two types of network security concerns: network infrastructure security and information security. To achieve the goals of network security, there are three primary requirements: Confidentiality, Integrity, and Availability.

**Network Trends**

There are several recent networking trends that affect organizations and consumers: Bring Your Own Device (BYOD), online collaboration, video communications, and cloud computing. BYOD means any device, with any ownership, used anywhere. Collaboration tools, like Cisco WebEx give employees, students, teachers, customers, and partners a way to instantly connect, interact, and achieve their objectives. Video is used for communications, collaboration, and entertainment. Video calls are made to and from anyone with an internet connection, regardless of where they are located. Cloud computing allows us to store personal files, even backup an entire drive on servers over the internet. Applications such as word processing and photo editing can be accessed using the cloud. There are four primary types of Clouds: Public Clouds, Private Clouds, Hybrid Clouds, and Custom Clouds. Smart home technology is currently being developed for all rooms within a house. Smart home technology will become more common as home networking and high-speed internet technology expands. Using the same wiring that delivers electricity, powerline networking sends information by sending data on certain frequencies. A Wireless Internet Service Provider (WISP) is an ISP that connects subscribers to a designated access point or hot spot using similar wireless technologies found in home wireless local area networks (WLANs).

**Network Security**

There are several common external threats to networks:

- Viruses, worms, and Trojan horses
- Spyware and adware
- Zero-day attacks
- Threat Actor attacks
- Denial of service attacks
- Data interception and theft
- Identity theft

These are the basic security components for a home or small office network:

- Antivirus and antispyware
- Firewall filtering

Larger networks and corporate networks use antivirus, antispyware, and firewall filtering, but they also have other security requirements:

- Dedicated firewall systems
- Access control lists (ACL)
- Intrusion prevention systems (IPS)
- Virtual private networks (VPN)

## 1.1 Networks Affect Our Lives

> not important

## 1.2 Network Components

### Host Roles

This topic discusses the parts of a network. 

<img src ="https://res.cloudinary.com/dri8yyakb/image/upload/v1614072471/cisco-netacad_a1iggs.png"/>

**hosts** = All computers that are connected to a network and participate directly in network communication. Hosts can be called **end devices** others **clients**. the term hosts specifically refers to devices on the network that are assigned *a number for communication purposes* (= **Internet Protocol (IP) address**) (it identifies a host within network). 

**Internet Protocol (IP) address** = identifies the host and the network to which the host is attached.

**Servers** = computers with software that allow them to provide information, like email or web pages, to other end devices on the network. 

> Each service requires separate server software. For example, a server requires web server software in order to provide web services to the network. A computer with server software can provide services simultaneously to many different clients.

**clients** = *type of host*. Clients have software for requesting and displaying the information obtained from the server

### Peer-to-peer

**peer-to-peer network** = computers function as the servers and clients on the network. **Client** and **server** software => usually run on separate computers, but it is also possible for one computer to be used for both roles at the same time. In small businesses and homes, many 

### end-to-end devices

The network devices that people are most familiar with are end devices. To distinguish one end device from another, *each end device on a network has an address*. When an end device initiates communication, it uses the address of the destination end device to specify where to deliver the message.

An end device is *either the source or destination of a message transmitted over the network.*

### intermediary devices

**Intermediary devices** 

- connect the individual end devices to the network. 
- They can connect multiple individual networks to form an **internetwork**. -
- provide connectivity and ensure that data flows across the network.

Intermediary devices use the destination end device **address**, in conjunction with information about the network **interconnections**, to determine the path that messages should take through the network. 


### network media

**media** = provides the channel over which the message travels from source to destination in a network.

Modern networks primarily use three types of media to interconnect devices

- Metal wires within cables - Data is encoded into electrical impulses.
- Glass or plastic fibers within cables (fiber-optic cable) - Data is encoded into pulses of light.
- Wireless transmission - Data is encoded via modulation of specific frequencies of electromagnetic waves.


## 1.3 Network Representations and Topologies

### Network Representations

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614072888/Screenshot_from_2021-02-23_10-34-26_qikvna.png"/>

terminology to describe how these devices and media connect to eachother

- **NIC (network interface card)** = phsically connects *end-device* to *network*
- **Physical Port** = connector/outlet on *networking device* where *media* connects to an *end-device* or another *networking device*
- **Interface** = specialized ports *on networking device* connecting to *individual networks*. because routers connect networks, the port on it is often referred to as *network interface*

> terms port and interface are often interchangeably used

### Topology Diagrams

Topology diagrams are mandatory documentation for anyone working with a network. They provide a visual map of how the network is connected. There are two types of topology diagrams: physical and logical.

- Physical Topology Diagrams = illustrate the physical location of intermediary devices and cable installation, as shown in the figure. 
- Logical topology diagrams = illustrate devices, ports, and the addressing scheme of the network.


## 1.4 Comon Types of Networks

### diferent sizes

- Small Home Networks – connect a few computers to each other and the Internet
- Small Office/Home Office – enables computer within a home or remote office to connect to a corporate network
- Medium to Large Networks – many locations with hundreds or thousands of interconnected computers
- World Wide Networks – connects hundreds of millions of computers world-wide – such as the internet

### LAN WAN

The two most common types of network infrastructures are **Local Area Networks (LANs)**, and **Wide Area Networks (WANs)**. 

- **LAN** is a network infrastructure that provides access to users and end devices in a small geographical area. 
- **WAN** is a network infrastructure that provides access to other networks over a wide geographical area, which is typically owned and managed by a larger corporation or a telecommunications service provider.
  

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614090824/Screenshot_from_2021-02-23_15-33-32_tucxrj.png"/>

### internet

**internet** = worldwide collection of interconnected LANs and WANs. 

- LANs are connected to each other using WANs.
- WANs may use copper wires, fiber optic cables, and wireless transmissions.
- The internet is not owned by any individual or group. The following groups were developed to help maintain structure on the internet: IETF ICANN IAB

### intranet and extranet

**intranet** = a private collection of LANs and WANs internal to an organization that is meant to be accessible only to the organizations members or others with authorization.

An organization might use an **extranet** to provide secure access to their network for individuals who work for a different organization that need access to their data on their network.


## 1.5 Internet Connections

### Internet access technologies 

variety of internet connection options are available

- *Home users, remote workers, and small offices* typically require a connection to an **ISP** to access the internet. Connection options vary greatly between ISPs and geographical locations. However, popular choices include broadband cable, **broadband digital subscriber line (DSL)**, wireless WANs, and mobile services.
- *Organizations* usually need access to other corporate sites as well as the internet. Fast connections are required to support business services including IP phones, video conferencing, and data center storage. **SPs** offer business-class interconnections. Popular business-class services include business DSL, leased lines, and Metro Ethernet.

### Home and small office Internet connections

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614091679/Screenshot_from_2021-02-23_15-47-51_orhzlz.png"/>

| Connection        | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| Cable             | high bandwidth, always on, internet offered by cable television service providers. |
| DSL               | high bandwidth, always on, internet connection that runs over a telephone line. In general, small office and home office users connect using **Asymmetrical DSL (ADSL)**, which means that the download speed is faster than the upload speed. |
| Cellular          | uses a cell phone network to connect to the internet.        |
| Satellite         | major benefit to rural areas without Internet Service Providers. |
| Dial-up telephone | an inexpensive, low bandwidth option using a modem.          |



### Business internet connections 

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614091698/Screenshot_from_2021-02-23_15-48-00_thsrgd.png"/>

| Connection                    | Description                                                  |
| ----------------------------- | ------------------------------------------------------------ |
| Dedicated Leased Line         | These are reserved circuits within the service provider’s network that connect distant offices with private voice and/or data networking. |
| Ethernet WAN / Metro Ethernet | This extends LAN access technology into the WAN.             |
| Business DSL                  | uses a cell phone network to connect to the internet. A popular choice is **Symmetric Digital Subscriber Line (SDSL)** which is similar to the consumer version of DSL but provides uploads and downloads at the same high speeds. |
| Satellite                     | Satellite service can provide a connection when a wired solution is not available. |


### Converging network

**Traditional Separate Networks**

cabling for the data network, telephone network, and video network for televisions. These separate networks could not communicate with each other. Each network used different technologies to carry the communication signal. Each network had its own set of rules and standards to ensure successful communication. Multiple services ran on multiple networks.

**Converged Networks**

Today, the separate data, telephone, and video networks converge. Unlike dedicated networks, converged networks are capable of delivering data, voice, and video between many different types of devices over the same network infrastructure. This network infrastructure uses the same set of rules, agreements, and implementation standards. Converged data networks carry multiple services on one network.

> Packet Tracer - Network Representation 
>
> Objectives 
>
> The network model in this activity incorporates many of the technologies that you will master in your CCNA studies. It represents a simplified version of how a small to medium-sized business network might look. Feel free to explore the network on your own. When you are ready, proceed through the following steps and answer the questions. Note: It is not important that you understand everything you see and do in this activity. Feel free to explore the network on your own. If you wish to proceed more systematically, follow the steps below. Answer the questions to the best of your ability. 
>
> Instructions 
>
> ### Step 1: Identify common components of a network as represented in Packet Tracer.
>
> 1. The icon toolbar at the bottom left hand corner has various categories of networking components. You should see categories that correspond to intermediary devices, end devices, and media. The **Connections** category (with the lightning bolt icon) represents the networking media supported by Packet Tracer. There is also an **End Devices** category and two categories specific to Packet Tracer: **Custom Made Devices** and **Multiuser Connection**.
> 2. List the intermediary device categories. Routers, Switches, Hubs, Wireless Devices, and WAN Emulation
> 3. Without entering into the Internet cloud or Intranet cloud, how many icons in the topology represent endpoint devices (only one connection leading to them)? 15
> 4. Without counting the two clouds, how many icons in the topology represent intermediary devices (multiple connections leading to them)? 11
> 5. How many end devices are **not** desktop computers? 8
> 6. How many different types of media connections are used in this network topology? 4
>
> ### Step 2: Explain the purpose of the devices.
>
> 1. In Packet Tracer, only the Server-PT device can act as a server. Desktop or Laptop PCs cannot act as a server. Based on your studies so far, explain the client-server model. In modern networks, a host can act as a client, a server, or both. Software installed on the host determines the role it plays on the network. Servers are hosts that have software installed that enables them to provide information and services, like email or web pages, to other hosts on the network. Clients are hosts that have software installed that enables them to request and display the information obtained from the server. A client could also be configured as a server simply by installing server software.
> 2. List at least two functions of intermediary devices. Regenerate and retransmit data signals; maintain information about what pathways exist through the network and internetwork; notify other devices of errors and communication failures; Direct data along alternate pathways when there is a link failure; Classify and direct messages according to QoS priorities; Permit or deny the flow of data, based on security settings.
> 3. List at least two criteria for choosing a network media type. The distance the media can successfully carry a signal. The environment in which the media is to be installed. The amount of data and the speed at which it must be transmitted. The cost of the media and installation.
>
> ### Step 3: Compare and contrast LANs and WANs.
>
> 1. Explain the difference between a LAN and a WAN. Give examples of each. LANs provide access to end users in a small geographical area. A home office or school campus are examples of LANs. WANs provide access to users in a wide geographical area over long distances spanning a few miles to thousands of miles. A Metropolitan Area Network and the Internet are examples of WANs. A company’s intranet may also connect multiple remote sites using a WAN.
> 2. In the Packet Tracer network, how many WANs do you see? There are two: the Internet and the Intranet WANs.
> 3. How many LANs do you see? There are three, easily identifiable because each has a border and label.
> 4. The Internet in this Packet Tracer network is overly simplified and does not represent the structure and form of the real Internet. Briefly describe the Internet. The Internet is mostly used when we need to communicate with a resource on another network. The Internet is a global mesh of interconnected networks (internetworks).
> 5. What are some of the common ways a home user connects to the Internet? Cable, DSL, dial-up, cellular, and satellite.
> 6. What are some common methods that businesses use to connect to the Internet in your area? Dedicated leased line, Metro-E, DSL, Cable, Satellite



## 1.6 Reliable Networks

**Network Architecture** =  the technologies that support the infrastructure that moves data across the network.

There are four basic characteristics that the underlying architectures need to address to meet user expectations:

- Fault Tolerance
- Scalability
- Quality of Service (QoS)
- Security

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614155592/cisco-netacad-Page-2_mce3ic.png"/>



## 1.7 Network Trends

> not important

## 1.8 Network Security

- Network security is an integral part of networking regardless of the size of the network.
- The network security that is implemented must take into account the environment while securing the data, but still allowing for quality of service that is expected of the network.
- Securing a network involves many protocols, technologies, devices, tools, and techniques in order to secure data and mitigate threats.
- Threat vectors might be external or internal.

- Security must be implemented in multiple layers using more than one security solution.
  - Network security components for home or small office network:
    - Antivirus and antispyware software should be installed on end devices.
    - Firewall filtering used to block unauthorized access to the network.
  - Larger networks have additional security requirements:
    - Dedicated firewall system
    - Access control lists (ACL) 
    - Intrusion prevention systems (IPS)
    - Virtual private networks (VPN)



## 1.9 The IT Professional

> not important 



