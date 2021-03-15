# Module 4 : Physical Layer

<img src="https://i.pcmag.com/imagery/encyclopedia-terms/osi-model-osi.fit_lim.size_1050x.gif"/>

> **OSI physical layer** def. 
>
> - provides the means to transport the bits that make up a data link layer frame across the network media. 
> - accepts a complete frame from the data link layer and **encodes** it as a series of signals that are transmitted to the local media. The encoded bits that comprise a frame are received by either an end device or an intermediate device.



Transports bits across the network media

1. Accepts a complete frame from the Data Link Layer
2. encodes it as a series of signals that are transmitted as electrical, optical, or radio wave signals that represent the bits in each frame. These signals are then sent over the media, one at a time. => the last step in the encapsulation process.
3. The next device in the path to the destination receives the bits and re-encapsulates the frame, then decides what to do with it

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615731180/Untitled_Diagram_o0qf4h.png" style="zoom: 67%;" />

<img src="https://lh3.googleusercontent.com/proxy/YtFLo7GtIDHTwTLXpKcFRldQM5JZY0jNFxE5CFbICsFhKFOUQmTZPO8ujYn8MU-wcnhj0z5tKk7da2GtOtKVhFDnIuupmQEUaq60bPTpWbhOhyTc97TKrJn5gGQDmIO3-u3J1Qc"/>



## Purpose of the Physical Layer

before any network communications can occur => a physical connection to a local network must be established. 

physical connection can be 

- a wired connection using a cable (For example, in many corporate offices, employees have desktop or laptop computers that are physically connected, via cable, to a shared switch. This type of setup is a wired network. Data is transmitted through a physical cable.)
- a wireless connection using radio waves. ( Devices on a wireless network must be connected to a wireless access point (AP) or wireless router like )



<img src="https://contenthub.netacad.com/courses/itn-dl/aeece082-34fa-11eb-ad9a-f74babed41a6/af1ffe72-34fa-11eb-ad9a-f74babed41a6/assets/2dd1e703-1c25-11ea-81a0-ffc2c49b96bc.jpg" alt="back of a wireless router showing four Ethernet switchports and an Internet port" style="zoom:50%;" />

access points components

1. The wireless antennas (These are embedded inside the router version shown in the figure above.)
2. Several Ethernet switchports
3. An internet port



<img src="https://contenthub.netacad.com/courses/itn-dl/aeece082-34fa-11eb-ad9a-f74babed41a6/af1ffe72-34fa-11eb-ad9a-f74babed41a6/assets/2dd20e11-1c25-11ea-81a0-ffc2c49b96bc.jpg" alt="a laptop with a wired connection into an Ethernet switchport on a wireless router" style="zoom:50%;" />

**Network Interface Cards**

**connect a device to the network**. 

- Ethernet NICs are used for a wired connection
- wireless local area network (WLAN) NICs are used for wireless. 
- An end-user device may include one or both types of NICs.

## Physical Layer Characteristics

This topic dives deeper into the specifics of the physical layer. 

This includes 

- the components and the media used to build a network
- the standards that are required so that everything works together

### Physical Layer Standards

- **upper** **OSI layers** 
  - The protocols and operations performed using **software** designed by software engineers and computer scientists. 
  - The services and protocols in the **TCP/IP** suite are defined by the **Internet Engineering Task Force (IETF).**
- **The physical layer** 
  - standards are implemented in **hardware**
  - consists of electronic circuitry, media, and connectors developed by engineers. Therefore, it is appropriate that the standards governing this hardware are defined by the relevant electrical and communications engineering organizations. There are many different international and national organizations, regulatory government organizations, and private companies involved in establishing and maintaining physical layer standards. For instance, the physical layer hardware, media, encoding, and signaling standards are defined and governed by these standards organizations:
    - International Organization for Standardization (ISO)
    - Telecommunications Industry Association/Electronic Industries Association (TIA/EIA)
    - International Telecommunication Union (ITU)
    - American National Standards Institute (ANSI)
    - Institute of Electrical and Electronics Engineers (IEEE)
    - National telecommunications regulatory authorities including the Federal Communication Commission (FCC) in the USA and the European Telecommunications Standards Institute (ETSI)
    - In addition to these, there are often regional cabling standards groups such as CSA (Canadian Standards Association), CENELEC (European Committee for Electrotechnical Standardization), and JSA/JIS (Japanese Standards Association), which develop local specifications.



### functional areas of physical layer

- **Physical Components**

  - electronic hardware devices, media, and other connectors that transmit the signals that represent the bits. 
  - Hardware components such as NICs, interfaces and connectors, cable materials, and cable designs are all specified in standards associated with the physical layer. 
  - The various ports and interfaces on a Cisco 1941 router are also examples of physical components with specific connectors and pinouts resulting from standards.

- **Encoding** 

  - method of converting a stream of data bits into a predefined "code”. **Codes** are groupings of bits used to provide a predictable pattern that can be recognized by both the sender and the receiver. In other words, encoding is the **method** or **pattern used to represent digital information**. This is similar to how Morse code encodes a message using a series of dots and dashes.

  - example: Manchester encoding represents a 0 bit by a high to low voltage transition, and a 1 bit is represented as a low to high voltage transition. An example of Manchester encoding is illustrated in the figure. The **transition occurs at the middle of each bit period**. This type of encoding is used in 10 Mbps Ethernet. Faster data rates require more complex encoding. Manchester encoding is used in older Ethernet standards such as 10BASE-T. Ethernet 100BASE-TX uses 4B/5B encoding and 1000BASE-T uses 8B/10B encoding.

    <img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615737224/Screenshot_from_2021-03-14_16-51-22_aer76d.png" style="zoom:50%;" />

- **Signaling**

  - The physical layer must **generate** the electrical, optical, or wireless **signals** that represent the "1" and "0" on the media.
  - The way that bits are represented is called the **signaling method**. 
  - The physical layer standards must define what type of signal represents a "1" and what type of signal represents a "0". This can be as simple as a change in the level of an electrical signal or optical pulse. 
    - For example, a long pulse might represent a 1 whereas a short pulse might represent a 0. This is similar to the signaling method used in Morse code, which may use a series of on-off tones, lights, or clicks to send text over telephone wires or between ships at sea.

  <img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615737549/Untitled_Diagram-Page-2_1_x6rc06.png" style="zoom: 67%;" />





### Bandwidth

Different physical media support the transfer of bits at different rates. Data transfer is usually discussed in terms of bandwidth. Bandwidth is **the capacity at which a medium can carry data.** Digital bandwidth measures **the amount of data that can flow from one place to another in a given amount of time**. 

Bandwidth is sometimes thought of as the speed that bits travel, however this is not accurate. For example, in both 10Mbps and 100Mbps Ethernet, the **bits are sent at the speed of electricity. The difference is the number of bits that are transmitted per second.**

factors affecting bandwidth of a network:

- The properties of the physical media
- The technologies chosen for signaling and detecting network signals

Physical media properties, current technologies, and the laws of physics all play a role in determining the available bandwidth.

The table shows the commonly used units of measure for bandwidth.

| **Unit of Bandwidth** | **Abbreviation** | **Equivalence**                           |
| :-------------------- | :--------------- | :---------------------------------------- |
| Bits per second       | bps              | 1 bps = fundamental unit of bandwidth     |
| Kilobits per second   | Kbps             | 1 Kbps = 1,000 bps = 103 bps              |
| Megabits per second   | Mbps             | 1 Mbps = 1,000,000 bps = 106 bps          |
| Gigabits per second   | Gbps             | 1 Gbps = 1,000,000,000 bps = 109 bps      |
| Terabits per second   | Tbps             | 1 Tbps = 1,000,000,000,000 bps = 1012 bps |

Terms used to measure the **quality of bandwidth** include: Latency | Throughput | Goodput

**Latency**

*amount of time, including delays, for data to travel from one given point to another.*

In an internetwork, or a network with multiple segments, throughput cannot be faster than the slowest link in the path from source to destination. Even if all, or most, of the segments have high bandwidth, *it will only take one segment in the path with low throughput to create a bottleneck in the throughput of the entire network.*

**Throughput** (how capacity is used)

*the measure of the transfer of bits across the media over a given period of time*.

Due to a number of factors, throughput usually *does not match the specified bandwidth in physical layer implementations.* Throughput is usually lower than the bandwidth. 

factors that influence throughput:

- The amount of traffic
- The type of traffic
- The latency created by the number of network devices encountered between source and destination

There are many online speed tests that can reveal the throughput of an internet connection.

**Goodput**

*the measure of usable data transferred over a given period of time.* 

Goodput = throughput - traffic overhead for establishing sessions, acknowledgments, encapsulation, and retransmitted bits. 

Goodput < throughput < bandwidth.



## Copper Cabling

#### characteristics

- most **common** type of cabling used in networks today. 
- Networks use copper media because it is **inexpensive**, **easy** to install, and has **low resistance** to electrical current. However, copper media is **limited by distance and signal interference**.
- Data is **transmitted** on copper cables as **electrical pulses**. 
  - A detector in the network interface of a destination device must receive a signal that can be successfully decoded to match the signal sent. However, the farther the signal travels, the more it deteriorates. This is referred to as **signal attenuation**. For this reason, all copper media must follow strict distance limitations as specified by the guiding standards.
  - The timing and voltage values of the electrical pulses are also susceptible to interference from two sources
    - **Electromagnetic interference (EMI) or radio frequency interference (RFI) -** EMI and RFI signals can distort and corrupt the data signals being carried by copper media. Potential sources of EMI and RFI include radio waves and electromagnetic devices, such as fluorescent lights or electric motors.
    - **Crosstalk** - Crosstalk is a disturbance caused by the electric or magnetic fields of a signal on one wire to the signal in an adjacent wire. In telephone circuits, crosstalk can result in hearing part of another voice conversation from an adjacent circuit. Specifically, when an electrical current flows through a wire, it creates a small, circular magnetic field around the wire, which can be picked up by an adjacent wire.

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615738441/Screenshot_from_2021-03-14_17-13-51_uwqiwj.png" style="zoom:60%;" />

### Types of Copper Cabling

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615738848/Screenshot_from_2021-03-14_17-19-19_z7rzqe.png" style="zoom:50%;" />



<img src="https://5.imimg.com/data5/EF/MS/MY-22205833/utp-cables-500x500.jpg" style="zoom:50%;" />



- **UTP (unshielded twisted pair)  **

  - the most common networking media. 
  - UTP cabling, terminated with RJ-45 connectors, is used for interconnecting network hosts with intermediary networking devices, such as switches and routers.
  - In LANs, UTP cable consists of four pairs of color-coded wires that have been twisted together and then encased in a flexible plastic sheath that protects from minor physical damage. The twisting of wires helps protect against signal interference from other wires.

  

- **STP (shielded twisted pair)**

  - provides better noise protection than UTP cabling.
  - more expensive and difficult to install. 
  - Like UTP cable, STP uses an **RJ-45 connector**.
  - STP cables combine the techniques of *shielding to counter EMI and RFI, and wire twisting to counter crosstalk.* To gain the full benefit of the shielding, STP cables are terminated with special shielded STP data connectors. If the cable is improperly grounded, the shield may act as an antenna and pick up unwanted signals.

  

- **coaxial**

  - gets its name from the fact that there are two conductors that share the same axis. 
  - consists of the following:
    - copper conductor is used to transmit the electronic signals.
    - layer of flexible plastic insulation surrounds a copper conductor.
    - The insulating material is surrounded in a woven copper braid, or metallic foil, that acts as the second wire in the circuit and as a shield for the inner conductor. This second layer, or shield, also reduces the amount of outside electromagnetic interference.
    - The entire cable is covered with a cable jacket to prevent minor physical damage.
  - There are different types of connectors used with coax cable. 
  - Although UTP cable has essentially replaced coaxial cable in modern Ethernet installations, the coaxial cable design is used in the following situations:
    - **Wireless installations** - Coaxial cables attach antennas to wireless devices. The coaxial cable carries radio frequency (RF) energy between the antennas and the radio equipment.
    - **Cable internet installations** - Cable service providers provide internet connectivity to their customers by replacing portions of the coaxial cable and supporting amplification elements with fiber-optic cable. However, the wiring inside the customer's premises is still coax cable.

  

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615739295/Screenshot_from_2021-03-14_17-27-59_bks7fq.png" style="zoom:50%;" />





## UTP Cabling

UTP cabling is the standard for use in LANs, this topic goes into detail about its advantages and limitations, and what can be done to avoid problems.

### properties

- consists of four pairs of color-coded copper wires that have been twisted together and then encased in a flexible plastic sheath. Its small size can be advantageous during installation.
- **does not use shielding** to counter the effects of EMI and RFI. 
  - relies solely on cancellation effect by the twisted wire pairs to limit signal degradation and provide self-shielding for wire pairs within the network media.
  - other ways that they can limit the negative effect of **crosstalk**:
    - **Cancellation -** Designers now pair wires in a circuit. When two wires in an electrical circuit are placed close together, their magnetic fields are the exact opposite of each other. Therefore, the **two magnetic fields cancel each other and also cancel out any outside EMI and RFI signals.**
    - **Varying the number of twists per wire pair** - To further enhance the cancellation effect of paired circuit wires, designers vary the number of twists of each wire pair in a cable. UTP cable must follow precise specifications governing how many twists or braids are permitted per meter (3.28 feet) of cable.  Each colored pair is twisted a different number of times.



### standards and connectors

- conforms to the standards established by the **TIA/EIA.** 

  - Specifically, TIA/EIA-568 stipulates the commercial cabling standards for LAN installations and is the standard most commonly used in LAN cabling environments. Some of the elements defined are as follows:
    - Cable types 
    - Cable lengths
    - Connectors
    - Cable termination
    - Methods of testing cable

- electrical characteristics of copper cabling are defined by the Institute of Electrical and Electronics Engineers (IEEE). 

- IEEE **rates UTP cabling according to its performance**. Cables are placed into categories based on their ability to carry higher bandwidth rates. For example, Category 5 cable is used commonly in 100BASE-TX Fast Ethernet installations. Other categories include Enhanced Category 5 cable, Category 6, and Category 6a. Cables in **higher categories** are designed and constructed to support **higher data rates**. As new gigabit speed Ethernet technologies are being developed and adopted, Category 5e is now the minimally acceptable cable type, with Category 6 being the recommended type for new building installations.

  - Category 3 => originally used for voice communication over voice lines, later used for data transmission.
  - Category 5 and 5e is used for data transmission. Category 5 supports 100Mbps and Category 5e supports 1000 Mbps
  - Category 6 has an added separator between each wire pair to support higher speeds. Category 6 supports up to 10 Gbps.
  - Category 7 also supports 10 Gbps.
  - Category 8 supports 40 Gbps.
  - Some manufacturers are making cables exceeding the TIA/EIA Category 6a specifications and refer to these as Category 7.

- UTP cable is usually terminated with an **RJ-45** connector. The TIA/EIA-568 standard describes the wire color codes to pin assignments (pinouts) for Ethernet cables.

  <img src="https://www.kenable.co.uk/119257-large_default/network-cat6-utp-ethernet-rj45-extension-male-female-cable-white-3m-007013.jpg" alt="kenable Network CAT6 UTP Ethernet RJ45 Extension Male/Female Cable ..." style="zoom:20%;" />



### straight-through and crossover UTP cables

Different situations may require UTP cables to be *wired according to different wiring conventions.* This means that the individual wires in the cable have to be connected in different orders to different sets of pins in the RJ-45 connectors.

<img src="https://lh3.googleusercontent.com/proxy/1lK-YpmXwvb8osRRRv62vjUSrLtov0OcGskcMTU8rmCXJq9BKBiIbIuBdTVBfhi-Jys-mClefAp3VZde9sXGativYfsf4ZQLYF8Lnn8LzY_bMN1O3QeySUjrQB_rdK-_7Ho8kaCKExNg0qrKSLH_-x_zORieZQhYqM7TOf4qm4h1ilc9R7U"/>

| Cable Type                | Standard                           | Application                                                  |
| :------------------------ | :--------------------------------- | :----------------------------------------------------------- |
| Ethernet Straight-through | Both ends T568A or both ends T568B | Connects a network host to a network device such as a switch or hub |
| Ethernet Crossover        | One end T568A, other end T568B     | Connects two network hosts Connects two network intermediary devices (switch to switch or router to router) <br /><br />crossover cables are now considered legacy as NICs use medium-dependent interface crossover (auto-MDIX) to automatically detect the cable type and make the internal connection. |
| Rollover                  | Cisco proprietary                  | Connects a workstation serial port to a router console port, using an adapter |



mixing crossover or straight-through cables 

- no damage to the devices
- *connectivity and communication between the devices will not take place.* 
- a common error and checking that the device connections are correct should be the first troubleshooting action if connectivity is not achieved.





## Fiber-Optic Cabling

As you have learned, fiber-optic cabling is the other type of cabling used in networks. 

### Properties

- Optical fiber cable transmits data over **longer distances** and at **higher bandwidths** than any other networking media. 
- Unlike copper wires, fiber-optic cable can transmit signals with **less attenuation** and is **immune to EMI and RFI**. 
- Optical fiber is commonly used to interconnect network devices.
- Optical fiber is a flexible, but extremely thin, transparent strand of very pure glass, not much bigger than a human hair. **Bits are encoded on the fiber as light impulses**. The fiber-optic cable acts as a waveguide, or “light pipe,” to transmit light between the two ends with minimal loss of signal.

<img src="https://contenthub.netacad.com/courses/itn-dl/aeece082-34fa-11eb-ad9a-f74babed41a6/af204c92-34fa-11eb-ad9a-f74babed41a6/assets/2ddbf920-1c25-11ea-81a0-ffc2c49b96bc.png" alt="img" style="zoom:43%;" />

### Types of Fiber Media

Fiber-optic cables are broadly classified into two types:

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615740963/Screenshot_from_2021-03-14_17-55-31_glvs7i.png" style="zoom: 50%;" />

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1615740963/Screenshot_from_2021-03-14_17-55-49_kgbtxy.png" style="zoom:50%;" />

- **Single-mode fiber (SMF)**  (less dispersion)
  -  small core and uses expensive laser technology to send a single ray of light
  - SMF is popular in long-distance situations spanning hundreds of kilometers, such as those required in long haul telephony and cable TV applications.
- **Multimode fiber (MMF) **(more dispersion)
  - larger core and uses LED emitters to send light pulses. 
  - Specifically, light from an LED enters the multimode fiber at different angles
  - Popular in LANs because they can be powered by low-cost LEDs. It provides bandwidth up to 10 Gb/s over link lengths of up to 550 meters.



One of the highlighted differences between MMF and SMF is the amount of **dispersion**. Dispersion refers to the spreading out of a light pulse over time. **Increased dispersion means increased loss of signal strength**. MMF has a greater dispersion than SMF. That is why MMF can only travel up to 500 meters before signal loss.

### Usage

- **Enterprise Networks -** Used for backbone cabling applications and interconnecting infrastructure devices
- **Fiber-to-the-Home (FTTH) -** Used to provide always-on broadband services to homes and small businesses
- **Long-Haul Networks -** Used by service providers to connect countries and cities
- **Submarine Cable Networks -** Used to provide reliable high-speed, high-capacity solutions capable of surviving in harsh undersea environments at up to transoceanic distances. Search the internet for “submarine cables telegeography map” to view various maps online.

### Fiber-Optic Connectors

An optical-fiber connector terminates the end of an optical fiber. 

The main differences among the types of connectors are dimensions and methods of coupling. Businesses decide on the types of connectors that will be used, based on their equipment.



- Straight-Tip (ST) Connectors => one of the first connector types used. The connector locks securely with a “Twist-on/twist-off” bayonet-style mechanism.
- Subscriber Connector (SC) =>  sometimes referred to as square connector or standard connector. They are a widely-adopted LAN and WAN connector that uses a push-pull mechanism to ensure positive insertion. This connector type is used with multimode and single-mode fiber.
- Lucent Connector (LC)  => are a smaller version of the SC connector. These are sometimes called little or local connectors and are quickly growing in popularity due to their smaller size.
- Duplex Multimode LC Connectors => is similar to a LC simplex connector, but uses a duplex connector.



<img src="https://ae01.alicdn.com/kf/HTB17i47dQxz61VjSZFtq6yDSVXa8/10pcs-1Gb-OM2-LC-LC-Fiber-Cable-Multimode-Duplex-2-0-3-0mmFiber-Optic-Patch-Cord.jpg_q50.jpg" alt="The image shows two fiber optic cables with a b n c connector and an approximate one inch white core sticking outward." style="zoom:50%;" />

**Until recently, light could only travel in one direction over optical fiber**.  => Two fibers were required to support the full duplex operation. => Therefore, **fiber-optic patch cables bundle together two optical fiber cables and terminate them with a pair of standard, single-fiber connectors.** 

Some fiber connectors accept both the transmitting and receiving fibers in a single connector known as a **duplex connector**, as shown in the Duplex Multimode LC Connector in the figure. BX standards such as 100BASE-BX use different wavelengths for sending and receiving over a single fiber.



### Fiber Patch Cords

- Fiber patch cords are required for interconnecting infrastructure devices. 

- color distinguishes between single-mode and multimode patch cords. 
  - yellow jacket is for single-mode fiber cables
  - orange (or aqua) for multimode fiber cables.

**Note**: Fiber cables should be protected with a small plastic cap when not in use.



### Fiber versus Copper

There are many advantages to using fiber-optic cable compared to copper cables. The table highlights some of these differences.

At present, in most enterprise environments, optical fiber is primarily used as backbone cabling for high-traffic, point-to-point connections between data distribution facilities. It is also used for the interconnection of buildings in multi-building campuses. Because fiber-optic cables do not conduct electricity and have a low signal loss, they are well suited for these uses.



| **Implementation Issues**      | **UTP Cabling**                   | **Fiber-Optic Cabling**               |
| :----------------------------- | :-------------------------------- | :------------------------------------ |
| Bandwidth supported            | 10 Mb/s - 10 Gb/s                 | 10 Mb/s - 100 Gb/s                    |
| Distance                       | Relatively short (1 - 100 meters) | Relatively long ( 1 - 100,000 meters) |
| Immunity to EMI and RFI        | Low                               | High (Completely immune)              |
| Immunity to electrical hazards | Low                               | High (Completely immune)              |
| Media and connector costs      | Lowest                            | Highest                               |
| Installation skills required   | Lowest                            | Highest                               |
| Safety precautions             | Lowest                            | Highest                               |



## Wireless Media

the third way to connect to the physical layer of a network.

### Properties

Wireless media carry electromagnetic signals that **represent the binary digits of data communications using radio or microwave frequencies.**

These are some of the limitations of wireless:

- **Coverage area** - Wireless data communication technologies work in open environments. However, certain construction materials used in buildings and structures, and the local terrain, limit effective coverage.
- **Interference** - Wireless is susceptible to interference and can be disrupted by such common devices as household cordless phones, some types of fluorescent lights, microwave ovens, and other wireless communications.
- **Security** - Wireless communication coverage requires no access to a physical strand of media. Therefore, devices and users, not authorized for access to the network, can gain access to the transmission. Network security is a major component of wireless network administration.
- **Shared medium** - WLANs operate in **half-duplex, which means only one device can send or receive at a time**. The wireless medium is shared amongst all wireless users. Many users accessing the WLAN simultaneously results in reduced bandwidth for each user.

Although wireless is increasing in popularity for desktop connectivity, copper and fiber are the most popular physical layer media for deployment of intermediary network devices, such as routers and switches.

## Types of Wireless Media

The IEEE and telecommunications industry standards for wireless data communications cover both the data link and physical layers. In each of these standards, physical layer specifications are applied to areas that include the following:

- Data to radio signal encoding
- Frequency and power of transmission
- Signal reception and decoding requirements
- Antenna design and construction

These are the wireless standards:

- **Wi-Fi (IEEE 802.11)** - Wireless LAN (WLAN) technology, commonly referred to as Wi-Fi. WLAN uses a contention-based protocol known as carrier sense multiple access/collision avoidance (CSMA/CA). The wireless NIC must first listen before transmitting to determine if the radio channel is clear. If another wireless device is transmitting, then the NIC must wait until the channel is clear. Wi-Fi is a trademark of the Wi-Fi Alliance. Wi-Fi is used with certified WLAN devices based on the IEEE 802.11 standards.
- **Bluetooth (IEEE 802.15)** - This is a wireless personal area network (WPAN) standard, commonly known as “Bluetooth.” It uses a device pairing process to communicate over distances from 1 to 100 meters.
- **WiMAX (IEEE 802:16)** - Commonly known as Worldwide Interoperability for Microware Access (WiMAX), this wireless standard uses a point-to-multipoint topology to provide wireless broadband access.
- **Zigbee (IEEE 802.15.4)** - Zigbee is a specification used for low-data rate, low-power communications. It is intended for applications that require short-range, low data-rates and long battery life. Zigbee is typically used for industrial and Internet of Things (IoT) environments such as wireless light switches and medical device data collection.

**Note**: Other wireless technologies such as cellular and satellite communications can also provide data network connectivity. However, these wireless technologies are out of scope for this module.

## Wireless LAN

A common wireless data implementation is enabling devices to connect wirelessly via a LAN. In general, a WLAN requires the following network devices:

- **Wireless Access Point (AP)** - These concentrate the wireless signals from users and connect to the existing copper-based network infrastructure, such as Ethernet. Home and small business wireless routers integrate the functions of a router, switch, and access point into one device, as shown in the figure.
- **Wireless NIC adapters** - These provide wireless communication capability to network hosts.

As the technology has developed, a number of WLAN Ethernet-based standards have emerged. When purchasing wireless devices, ensure compatibility and interoperability.

The benefits of wireless data communications technologies are evident, especially the savings on costly premises wiring and the convenience of host mobility. Network administrators must develop and apply stringent security policies and processes to protect WLANs from unauthorized access and damage.

### 

































