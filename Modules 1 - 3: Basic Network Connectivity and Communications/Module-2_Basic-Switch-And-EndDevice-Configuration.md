# Module 2 : Basic switch and end-device configuration

## 2.1 Cisco IOS Access

### OS 

All end devices and network devices require an operating system (OS). 

- **kernel** = interacts directly with computer hardware + manages how hardware resources are used to meet software requirements
- **shell** = interfaces with applications and the user
- **command-line interface (CLI)** || **graphical user interface (GUI)** = How the user interacts with the shell

### GUI

A GUI such as Windows, macOS, Linux KDE, Apple IOS, or Android allows the user to interact with the system using an environment of graphical icons, menus, and windows. The GUI example in the figure is more user-friendly and requires less knowledge of the underlying command structure that controls the system. For this reason, most users rely on GUI environments.

However, GUIs may not always be able to provide all the features available with the CLI. GUIs can also fail, crash, or simply not operate as specified. For these reasons, network devices are typically accessed through a CLI. *The CLI is less resource intensive and very stable when compared to a GUI.*

The family of network operating systems used on many Cisco devices is called the **Cisco Internetwork Operating System (IOS)**. Cisco IOS is used on many Cisco routers and switches regardless of the type or size of the device. Each device router or switch type uses a different version of Cisco IOS. Other Cisco operating systems include IOS XE, IOS XR, and NX-OS.

Note: The operating system on home routers is usually called **firmware**. The most common method for configuring a home router is by using a web browser-based GUI.

### OS purpose

A CLI-based network operating system (e.g., the Cisco IOS on a switch or router) enables a network technician to do the following:

- Use a keyboard to run CLI-based network programs
- Use a keyboard to enter text and text-based commands
- View output on a monitor

Cisco networking devices run particular versions of the Cisco IOS. The IOS version is dependent on the type of device being used and the required features. While all devices come with a default IOS and feature set, it is possible to upgrade the IOS version or feature set to obtain additional capabilities.

### access methods

A **switch** will forward traffic by default and *does not need to be explicitly configured to operate*.

> For example, two configured hosts connected to the same new switch would be able to communicate.

Regardless of the default behavior of a new switch, *all switches should be configured and secured.*


- **Console** (port)
  - a **physical management port** that provides out-of-band access to a Cisco device. **Out-of-band access** refers to access via a dedicated management channel that is used for device maintenance purposes only. 
  - pro: device accessible if no networking services are configured (ex initial configuration.) 
  - A computer running terminal emulation software and a special console cable to connect to the device are required for a console connection.
- **Secure Shell (SSH)**
  - in-band and recommended method for remote secure CLI connections over a network through a virtual interface
  - Unlike a console connection, SSH connections *require active networking services*
  - including an active interface configured with an address. Most versions of Cisco IOS include an SSH server and an SSH client that can be used to establish SSH sessions with other devices.
- Telnet
  - in-band and insecure && unencrypted method for remote secure CLI connections over a network through a virtual interface Unlike SSH
  - User authentication, passwords, and commands are sent over the network in plaintext. 
  - The best practice is to use SSH instead of Telnet. Cisco IOS includes both a Telnet server and Telnet client.

Note: Some devices, such as routers, may also support a legacy auxiliary port that was used to establish a CLI session remotely over a telephone connection using a modem. Similar to a console connection, the AUX port is **out-of-band** and does not require networking services to be configured or available.

### terminal emulation programs

There are several terminal emulation programs you can use to connect to a networking device either by a serial connection over a **console port**, or by an **SSH/Telnet connection**. These programs allow you to enhance your productivity by adjusting window sizes, changing font sizes, and changing color schemes.

## 2.2 IOS navigation

### Primary Command Modes

As a security feature, the Cisco IOS software separates management access into the following two command modes:

- **User EXEC Mode** 
  - limited capabilities, useful for basic operations. 
  - only a limited number monitoring commands. no execution of any commands changing device config. 
  - The user EXEC mode is identified by the CLI prompt that ends with the **>** symbol.
- **Privileged EXEC Mode** 
  - To execute configuration commands, a network administrator must access privileged EXEC mode. 
  - Higher configuration modes, like **global configuration mode**, can only be reached from privileged EXEC mode. 
  - The privileged EXEC mode can be identified by the prompt ending with the **#** symbol.


### (sub)configuration mode

To configure the device, the user must enter **global configuration mode**, which is commonly called **global config mode**.

- CLI configuration changes are made that affect the operation of the device as a whole. 
- Global configuration mode is identified by a prompt that ends with **(config)#** after the device name, such as **Switch(config)#.**
- Global configuration mode is accessed before other specific configuration modes
- From global config mode, the user can enter different sub-configuration modes. Each of these modes allows the configuration of a particular part or function of the IOS device. Two common sub-configuration modes include:
  - **Line Configuration Mode** - Used to configure console, SSH, Telnet, or AUX access.
  - **Interface Configuration Mode** - Used to configure a switch port or router network interface.

When the CLI is used, the mode is identified by the command-line prompt that is unique to that mode. By default, *every prompt begins with the device name. Following the name, the remainder of the prompt indicates the mode.* For example, the default prompt for line configuration mode is **Switch(config-line)#** and the default prompt for interface configuration mode is **Switch(config-if)#**.

```ios
/**
To move from user EXEC mode to privileged EXEC mode, use the **enable** command. Use the **disable** privileged EXEC mode command to return to user EXEC mode.
**/

Switch>enable

/**
To move in and out of **global configuration mode**, use the **configure terminal** privileged EXEC mode command. To return to the **privileged EXEC mode**, enter the **exit** global config mode command.
**/

Switch#configure terminal
Enter configuration commands, one per line. End with CNTL/Z

/**
There are many different subconfiguration modes. For example, to enter line subconfiguration mode, you use the **line** command followed by the management line type and number you wish to access. Use the **exit** command to exit a subconfiguration mode and return to global configuration mode.
**/

Switch(config)# line console 0
Switch(config-line)# exit
Switch(config)#

Switch(config)#interface vlan 1 //interface-subconfiguration-mode 
Switch(config-if)#

/**
To move from any subconfiguration mode of the global configuration mode to the mode one step above it in the hierarchy of modes, enter the exit command.

To move from any subconfiguration mode to the privileged EXEC mode, enter the end command or enter the key combination Ctrl+Z.
**/

Switch(config-if)# end
Switch#
Switch#configure terminal

/**
You can also move directly from one subconfiguration mode to another. Notice how after selecting an interface, the command prompt changes from (config-line)# to (config-if)#.
**/

Switch(config-line)# interface FastEthernet 0/1
Switch(config-if)#
```

## 2.3 command structure

### basic IOS command structure

A Cisco IOS device supports many commands. Each IOS command has a specific format, or syntax, and can only be executed in the appropriate mode. 

The general syntax for a command, shown in the figure, is the **command** followed by any appropriate **keywords** and **arguments**.

- **Keyword** - This is a specific parameter defined in the operating system (in the figure, ip protocols).
- **Argument** - This is not predefined; it is a value or variable defined by the user (in the figure, 192.168.10.5).

<img src="https://res.cloudinary.com/dri8yyakb/image/upload/v1614322416/Screenshot_from_2021-02-26_07-53-26_uvlqum.png" width=400/>

The diagram shows the general syntax for a switch command (which is prompt, command, space, and keyword or argument) and provides two examples. 

> In the first example, the prompt is Switch>, the command is show, a space follows, and the keywords are ip protocols. 
> In the second example, the prompt is Switch>, the command is ping, a space follows, and the argument is 192 dot 168 dot 10 dot 5.

### IOS command syntax check


A command might require one or more arguments. To determine the keywords and arguments required for a command, refer to the command syntax. The syntax provides the pattern, or format, that must be used when entering a command.

- boldface text indicates commands and keywords that are 
- Italic text indicates an argument for which the user provides the value.


- **boldface**	Boldface text indicates commands and keywords that you enter literally as shown.
- **italics**	 indicates arguments for which you supply values.
- **[x]**	Square brackets indicate an optional element (keyword or argument).
- **{x}**	Braces indicate a required element (keyword or argument).
- **[x {y | z }]**	Braces and vertical lines within square brackets indicate a required choice within an optional element. Spaces are used to clearly delineate parts of the command.


> For instance, the syntax for using the description command is description string. The argument is a string value provided by the user. The description command is typically used to identify the purpose of an interface. For example, entering the command, description Connects to the main headquarter office switch, describes where the other device is at the end of the connection.

> The following examples demonstrate conventions used to document and use IOS commands:

 ```
ping ip-address 
// The command is ping and the user-defined argument is the ip-address of the destination device. For example, ping 10.10.10.5.
traceroute ip-address
// The command is traceroute and the user-defined argument is the ip-address of the destination device. 
Switch(config-if)# switchport port-security aging { static | time time | type {absolute | inactivity}}
// If a command is complex with multiple arguments, you may see it represented like this: The command will typically be followed with a detailed description of the command and each argument.
 ```

### keyboard - shortcuts | hotkeys

The IOS CLI provides hot keys and shortcuts that make configuring, monitoring, and troubleshooting easier.

Commands and keywords can be shortened to the minimum number of chars that identify a unique selection. For example, the configure command can be shortened to conf because configure is the only command that begins with conf. An even shorter version, con, will not work because more than one command begins with con. Keywords can also be shortened.

The table lists keystrokes to enhance command line editing.

| key                | description                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------- |
| Ctrl+D             | Ers the char at the cursor.                                                                 |
| Ctrl+K             | Ers all chars from the cursor to the end of the command line.                               |
| Esc D              | Ers all chars from the cursor to the end of the word.                                       |
| Ctrl+U or X        | Ers all chars from the cursor back to the start of the command line.                        |
| Ctrl+W             | Ers the word to the left of the cursor.                                                     |
| Ctrl+A             | Moves the cursor to the beginning of the line.                                              |
| Left Arrow Ctrl+B  | Moves the cursor one char to the left.                                                      |
| Esc B              | Moves the cursor back one word to the left.                                                 |
| Esc F              | Moves the cursor forward one word to the right.                                             |
| Right Arrow Ctrl+F | Moves the cursor to the end of command line.                                                |
| Ctrl+E             | Recalls the previous command in the history buffer, beginning with the most recent command. |
| Down Arrow Ctrl+N  | Goes to the next line in the the history buffer.                                            |
| Ctrl+R or +I or +L | Redisplays the system prompt and command line after a console message is received.          |


| key          | description                                                                                                                                             |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ctrl-C       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode. When in setup mode, aborts back to the command prompt. |
| Ctrl+Z       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode.                                                        |
| Ctrl+shift-6 | All-purpose break sequence used to abort DNS lookups, traceroutes, pings, etc.                                                                          |


## 2.4 basic device configuration

The first configuration command on any device should be to give it a unique device name or **hostname**. 
By default, all devices are assigned a factory default name. For example, a Cisco IOS switch is "Switch."

```
Switch# configure terminal
Switch(config)# hostname Sw-Floor-1
Sw-Floor-1(config)#
```

*To secure user EXEC mode access*, 
- enter line console configuration mode using the **line console 0 global** configuration command 
- specify the user EXEC mode password using the **password** password command. 
- enable user EXEC access using the **login** command.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

To have administrator access to all IOS commands including configuring a device, you must gain privileged EXEC mode access. It is the most important access method because it provides complete access to the device.

To secure privileged EXEC access, use the `enable secret [password]` global config command.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# enable secret class
Sw-Floor-1(config)# exit
Sw-Floor-1#
```

Virtual terminal (VTY) lines enable remote access using Telnet or SSH to the device. Many Cisco switches support up to 16 VTY lines that are numbered 0 to 15.

To secure VTY lines, enter line VTY mode using the line vty 0 15 global config command. Next, specify the VTY password using the password password command. Lastly, enable VTY access using the login command.

An example of securing the VTY lines on a switch is shown.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco 
Sw-Floor-1(config-line)# login 
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

The startup-config and running-config files display most passwords in plaintext. This is a security threat because anyone can discover the passwords if they have access to these files.

To encrypt all plaintext passwords, use the service **password-encryption** global config command as shown in the example.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# service password-encryption
Sw-Floor-1(config)#
```

The command applies weak encryption to all unencrypted passwords. This encryption applies only to passwords in the configuration file, not to passwords as they are sent over the network. The purpose of this command is to keep unauthorized individuals from viewing passwords in the configuration file.

Use the show running-config command to verify that passwords are now encrypted.

```
Sw-Floor-1(config)# end
Sw-Floor-1# show running-config
!
(Output omitted)
!
line con 0
password 7 094F471A1A0A
login
!
line vty 0 4
 password 7 094F471A1A0A
 login
line vty 5 15
password 7 094F471A1A0A
login
!
!
end
```


Although requiring passwords is one way to keep unauthorized personnel out of a network, it is vital to provide a method for declaring that only authorized personnel should attempt to access the device. To do this, add a banner to the device output. Banners can be an important part of the legal process in the event that someone is prosecuted for breaking into a device. Some legal systems do not allow prosecution, or even the monitoring of users, unless a notification is visible.

To create a banner message of the day on a network device, use the banner motd # the message of the day # global config command. The “#” in the command syntax is called the delimiting character. It is entered before and after the message. The delimiting character can be any character as long as it does not occur in the message. For this reason, symbols such as the "#" are often used. After the command is executed, the banner will be displayed on all subsequent attempts to access the device until the banner is removed.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# banner motd #Authorized Access Only#
```

## 2.5 save configurations

### configuration files

You now know how to perform basic configuration on a switch,  
including passwords and banner messages. This topic will show you how to save your configurations.

There are two system files that store the device configuration:

- **startup-config** - This is the saved configuration file that is stored in NVRAM. It contains all the commands that will be used by the device upon startup or reboot. Flash does not lose its contents when the device is powered off.
- **running-config** - This is stored in Random Access Memory (RAM). It reflects the current configuration. Modifying a running configuration affects the operation of a Cisco device immediately. RAM is volatile memory. It loses all of its content when the device is powered off or restarted.

**show running-config** privileged EXEC mode command is used to view the running config.  
As shown in the example, the command will list the complete configuration currently stored in RAM.

```
Sw-Floor-1# show running-config
Building configuration...
Current configuration : 1351 bytes
!
! Last configuration change at 00:01:20 UTC Mon Mar 1 1993
!
version 15.0
no service pad
service timestamps debug datetime msec
service timestamps log datetime msec
service password-encryption
!
hostname Sw-Floor-1
!
(output omitted)
```

To view the startup configuration file, use the `show startup-config` privileged EXEC command.

If power to the device is lost, or if the device is restarted, all configuration changes will be lost unless they have been saved. To save changes made to the running configuration to the startup configuration file, use the `copy running-config startup-config` privileged EXEC mode command.

### alter running configuration

If changes made to the running config do not have the desired effect and the running-config has not yet been saved

- you can restore the device to its previous configuration.
- Remove the changed commands individually
- Reload the device using the `reload` privileged EXEC mode command to restore the startup-config.

The downside to using the `reload` command to remove an unsaved running config => **network downtime**.

When a reload is initiated, the IOS will detect that the running config has changes that were not saved to the startup configuration. A prompt will appear to ask whether to save the changes. To discard the changes, enter n or no.

Alternatively, if undesired changes were saved to the startup config, it may be necessary to clear all the configurations. This requires erasing the startup config and restarting the device.  `erase startup-config` to remove startup config. After the command is issued, the switch will prompt you for confirmation. Press Enter to accept.

After removing the startup config from NVRAM, reload the device to remove the current running config file from RAM. On reload, a switch will load the default startup config that originally shipped with the device.

`dir nvram | flash`= to show contents of NVRAM or flash

## 2.6 ports and addresses

After the basic device configuration we want end devices to communicate with each other for this we give each device an **IP address**, **device ports** and the **media** used to connect devices in this topic.

ip-address

- primary means of enabling devices to locate one another and establish end-to-end communication on the internet. 

- Each end device on a network must be configured with an IP address. 

- The structure of an **IPv4 address** is called **dotted decimal notation** and is represented by four decimal numbers between 0 and 255. IPv4 addresses are **assigned to individual devices connected to a network**.

  

<img src="http://www.homenethowto.com/wp-content/uploads/default-gateway.jpg" alt="addresses" style="zoom:50%;" />



**subnet mask** => 32-bit value that differentiates the **network portion** of the address from the **host portion**. Coupled with the IPv4 address, the subnet mask *determines to which subnet the device is a member*.

> ex: IPv4 address (192.168.1.10), subnet mask (255.255.255.0), and default gateway (192.168.1.1) assigned to a host.



**default gateway address** is the IP address of the router that the host will use to access remote networks, including the internet.



**IPv6 addresses** = 128 bits in length and written as a string of hexadecimal values. Every four bits is represented by a single hexadecimal digit; for a total of 32 hexadecimal values. Groups of four hexadecimal digits are separated by a colon (:) . IPv6 addresses are not case-sensitive and can be written in either lowercase or uppercase.

### interfaces and ports

Network communications depend on end user device interfaces, networking device interfaces, and the cables that connect them. Each physical interface has specifications, or standards, that define it. *A cable connecting to the interface must be designed to match the physical standards of the interface*. Types of **network media** include twisted-pair copper cables, fiber-optic cables, coaxial cables, or wireless, as shown in the figure.



<img src="https://sites.google.com/site/cis3347edwardtello/_/rsrc/1487118120821/home/osi-and-tcp-layered-models/application-protocols/network-cabling-media-and-topologies/network%20cablings.jpg?height=489&width=703" alt="cables" style="zoom:67%;" />



Different types of network media have different features and benefits. Not all network media have the same characteristics. Not all media are appropriate for the same purpose. These are some of the differences between various types of media:

- Distance the media can successfully carry a signal
- Environment in which the media is to be installed
- Amount of data and the speed at which it must be transmitted
- Cost of the media and installation

Not only does each link on the internet require a specific network media type, but each link also requires a particular network technology. For example, **Ethernet** is the most common local-area network (LAN) technology used today. Ethernet ports are found on end-user devices, switch devices, and other networking devices that can physically connect to the network using a cable.

Cisco IOS Layer 2 switches have physical ports for devices to connect. These ports do not support Layer 3 IP addresses. Therefore, switches have one or more **switch virtual interfaces (SVIs)**. These are virtual interfaces because there is no physical hardware on the device associated with it. An SVI is created in software.

The *virtual interface lets you remotely manage a switch over a network using IPv4 and IPv6*. Each switch comes with one SVI appearing in the default configuration "out-of-the-box." **The default SVI is interface VLAN1**.

**Note**: A Layer 2 switch does not need an IP address. The IP address assigned to the SVI is used to remotely access the switch. An IP address is not necessary for the switch to perform its operations.

## 2.7 configure IP addressing



Much like you need your friends' telephone numbers to text or call them, end devices in your network need an IP address so that they can communicate with other devices on your network. In this topic, you will implement basic connectivity by configuring IP addressing on switches and PCs.

assigning IPv4 address information

- entered into end devices manually
- automatically using **Dynamic Host Configuration Protocol (DHCP)**.

### automatic IP address configuration 

End devices typically default to using DHCP for automatic IPv4 address configuration. DHCP is a technology that is used in almost every network. The best way to understand why DHCP is so popular is by considering all the extra work that would have to take place without it.

**DHCP** => *enables automatic IPv4 address configuration for every end device that is DHCP-enabled*. 

Imagine the amount of time it would take if every time you connected to the network, you had to manually enter the IPv4 address, the subnet mask, the default gateway, and the DNS server. Multiply that by every user and every device in an organization and you see the problem. Manual configuration also increases the chance of misconfiguration by duplicating another device’s IPv4 address.

**Note**: IPv6 uses DHCPv6 and SLAAC (Stateless Address Auto-configuration) for dynamic address allocation.

### Switch virtual interface configuration

To access the switch remotely, an **IP address** and a **subnet mask** must be configured on the SVI.   
To configure an SVI on a switch

- use the `interface vlan 1` global configuration command. Vlan 1 is not an actual physical interface but a virtual one.
- assign an IPv4 address using the `ip address *ip-address subnet-mask*` interface configuration command. 
- enable the virtual interface using the `no shutdown` interface configuration command.

After these commands are configured, the switch has all the IPv4 elements ready for communication over the network.

**Note**: Similar to a Windows hosts, switches configured with an IPv4 address will typically also need to have a **default gateway** assigned. This can be done using the `ip default-gateway *ip-address*` global configuration command. The *ip-address* parameter would be the IPv4 address of the local router on the network, as shown in the example. However, in this module you will only be configuring a network with switches and hosts. Routers will be introduced later.

`````
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# interface vlan 1
Sw-Floor-1(config-if)# ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)# no shutdown
Sw-Floor-1(config-if)# exit
Sw-Floor-1(config)# ip default-gateway 192.168.1.1
Sw-Floor-1(config)# exit
Sw-Floor-1# show ip interface brief 
// This command is useful for verifying the condition of the switch interfaces.
`````