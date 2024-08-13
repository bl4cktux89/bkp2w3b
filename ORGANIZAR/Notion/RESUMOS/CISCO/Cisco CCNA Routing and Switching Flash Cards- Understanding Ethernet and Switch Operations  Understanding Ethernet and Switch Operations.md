[https://www.ciscopress.com/articles/printerfriendly/2114358](https://www.ciscopress.com/articles/printerfriendly/2114358)

  

To help in your CCNA preparations, this chapter covers the fundamentals of Ethernet technologies and describes how switches operate.

# Understanding Ethernet and Switch Operations

Ethernet is the technology of choice for today’s LANs. It is fast, has low costs, and is easy to maintain. Today’s Ethernet standards support speeds of 10 Mbps, 100 Mbps, 1 Gbps, 10 Gbps, and 40 Gbps.

Ethernet functions at Layers 1 and 2 of the Open Systems Interconnection (OSI) model. As such, Ethernet standards specify cabling, signaling, and data link layer addressing.

Because most LANs use Ethernet as the primary Layer 2 technology, most switches today are Ethernet switches. This section covers the fundamentals of Ethernet technologies and describes how switches operate.

Question 1

**What does BASE mean in 100BASE-T and 1000BASE-T?**

Answer 1

BASE in 100BASE-T and 1000BASE-T refers to the baseband signaling method. Baseband is a network technology in which only one carrier frequency is used. This means that when a device transmits, it uses the entire bandwidth on the wire and does not share it during the single time interval.

Question 2

**What is carrier sense multiple access collision detect (CSMA/CD)?**

Answer 2

CSMA/CD describes the Ethernet access method.

In CSMA/CD, many stations can transmit on the same cable, and no station has priority over any other. Before a station transmits, it listens on the wire (carrier sense) to make sure that no other station is transmitting. If no other station is transmitting, the station transmits across the wire. If a collision occurs, the transmitting stations detect the collision and run a random backoff algorithm. The random backoff algorithm is a random time that each station waits before retransmitting.

Question 3

**What is UTP cabling?**

Answer 3

Unshielded twisted-pair (UTP) cabling is a type of twisted-pair cable that relies solely on the cancellation effects produced by the twisted wire pairs to limit electromagnetic interference (EMI) and radio frequency interference (RFI).

UTP cable is often installed using an RJ-45 connector, and UTP cabling must follow precise specifications dictating how many twists are required per meter of cable. The advantages of UTP are ease of installation and low cost. A disadvantage of UTP is that it is more prone to EMI than other types of media.

Question 4

**What is the maximum cable length for UTP?**

Answer 4

The maximum length is 100 meters or 328 feet.

Question 5

**What is a straight-through Ethernet cable, and when would you use it?**

Answer 5

A straight-through Ethernet cable is wired the same way at both ends. This cable uses pins 1, 2, 3, and 6. The send and receive wires are not crossed.

You should use a straight-through Ethernet cable when connecting dissimilar devices (for example, data terminal equipment [DTE] to data communications equipment [DCE]). Examples include connecting PCs (DTE) to switches or hubs (DCE) or a router (DTE) to a switch or a hub (DCE).

Question 6

**What is a crossover Ethernet cable, and when would you use it?**

Answer 6

A crossover Ethernet cable is a cable that has the send and receive wires crossed at one of the ends. In a Category 5 cable, the 1 and 3 wires are switched and the 2 and 6 wires are switched at one end of the cable.

You should use a crossover cable when connecting similar devices (DCE to DCE or DTE to DTE), such as connecting a router to a router, a switch to a switch or hub, a hub to a hub, or a PC to a PC.

NOTE

In today’s networks, most Catalyst switches have auto-mdix, which can automatically detect the type of cable connected to the interface and automatically configure the connection appropriately.

Question 7

**What are the different UTP categories?**

Answer 7

The categories of UTP cable are as follows:

- **Category 1:** Used for telephone communications.
- **Category 2:** Capable of data transmission speeds of up to 4 Mbps.
- **Category 3:** Used in 10BASE-T networks. Speeds up to 10 Mbps.
- **Category 4:** Used in Token Ring networks. Speeds up to 16 Mbps.
- **Category 5:** Capable of data transmission speeds of up to 100 Mbps.
- **Category 5e:** Supports speeds of up to 1 Gbps.
- **Category 6:** Consists of four pairs of 24-gauge copper wires. Speeds up to 1 Gbps.
- **Category 6a:** Supports speeds up to 10 Gbps.

Question 8

**What is the difference between single-mode fiber (SMF) and multimode fiber (MMF)?**

Answer 8

The primary difference between SMF and MMF is the ability of the fiber to send light for a long distance at high bit rates. In general, MMF supports shorter distances than SMF.

Question 9

**What are three ways that LAN traffic is transmitted?**

Answer 9

LAN traffic is transmitted one of the following three ways:

- **Unicast:** Unicasts are the most common type of LAN traffic. A unicast frame is a frame intended for only one host.
- **Broadcast:** Broadcast frames are intended for all hosts within a broadcast domain. Stations view broadcast frames as public service announcements. All stations receive and process broadcast frames.
- **Multicast:** Multicasts are traffic in which one transmitter tries to reach only a subset, or group, of the entire segment.

Question 10

**How many bits are in an Ethernet address?**

Answer 10

Also called a MAC address, an Ethernet address is the Layer 2 address associated with the Ethernet network adapter. Typically burned into the adapter, the MAC address is usually displayed in a hexadecimal format, such as 00-0d-65-ac-50-7f.

Question 11

**What portion of the MAC address is vendor specific?**

Answer 11

The first half or first 24 bits of the MAC address are vendor specific.

A MAC address is 48 bits and is displayed in hexadecimal. The first half of the address identifies the vendor or manufacturer of the card. This is called the Organizational Unique Identifier (OUI). The last half of the address identifies the card address.

Question 12

**What portion of the MAC address is vendor assigned?**

Answer 12

The last 24 bits are vendor assigned.

Question 13

**What are the first 24 bits in a MAC address called?**

Answer 13

These bits are the Organizational Unique Identifier (OUI).

Question 14

**What is an example of a Layer 2 address?**

Answer 14

An example is a MAC address.

Question 15

**What is an example of a Layer 3 address?**

Answer 15

An example is an IP address.

Question 16

**If a sending device does not know the MAC address of the destination device, what protocol is used to find the MAC address of the receiving device?**

Answer 16

Address Resolution Protocol (ARP) is used to find the MAC address of the receiving device.

ARP is a local broadcast sent to all devices on the local segment to find the MAC address of a host.

Question 17

**Host A wants to send data to host B. Host B is on a different segment from host A. The two segments are connected to each other through a router. What will host B see as the source MAC address for all frames sent from host A?**

Answer 17

Because host B is on a different segment that is separated by a router, the MAC address of all frames sent from host A will be the MAC address of the router. Anytime a frame passed through a router, a router rewrites the MAC address to the MAC address of the router’s exit interface for the segment and then sends the frame to the local host.

In this case, the router will change the source MAC address of the frame sent from host A with the MAC address of its interface connecting to the segment host B is on. Host B will see that the frame came from the MAC address of the router with the IP address of host A.

Question 18

**Switching uses a process outlined by the IEEE as transparent bridging. What are the five processes transparent bridges use for determining what to do with a frame?**

Answer 18

The five processes of transparent bridging as defined in IEEE 802.1d are

1. Learning
2. Flooding
3. Filtering
4. Forwarding
5. Aging

Question 19

**What is the transparent bridging learning process?**

Answer 19

When a frame enters a switch, the switch adds the source Ethernet MAC address and source port into its MAC address table. The process of recording the source MAC address and the source port in the table whenever a switch sees a frame is called the learning process.

Question 20

**What is the transparent bridging flooding process?**

Answer 20

When a switch receives a unicast frame and it does not have the destination MAC address and port in its bridging table, or a broadcast or multicast frame, the switch will forward this frame out all ports, except the port it received the unicast frame on. This is called the flooding process.

Question 21

**What is the transparent bridging filtering process?**

Answer 21

The filtering process occurs when a switch receives a frame and the source and destination hosts reside on the same interface. When this occurs, the switch filters or discards the frame.

Question 22

**What is the transparent bridging forwarding process?**

Answer 22

A switch forwards a frame when the destination address is in the switch’s MAC address table and the source and destination are on different interfaces. This is the forwarding process.

Question 23

**What is the transparent bridging aging process?**

Answer 23

When a switch learns a source address, it time-stamps the entry in the MAC address table. Every time the switch sees a frame from the same source, the timestamp is updated. The aging process occurs when the switch does not see a frame from the source before the aging timer expires. When this happens, the switch removes the entry from the MAC address table.

Question 24

**For what two purposes does the Ethernet protocol use physical addresses?**

Answer 24

Ethernet uses physical addresses to

- Uniquely identify devices at Layer 2
- Allow communication between different devices on the same Layer 2 network

Question 25

**What will an Ethernet switch do if it receives a unicast frame with a destination MAC that is listed in the switch table?**

Answer 25

The switch will forward the frame to a specific port.

Switches use the transparent bridging process to determine how to handle frames. The process is as follows:

1. A frame is received.
2. If the destination is a broadcast or multicast, the switch will forward the frame to all ports except to the port the frame was received.
3. If the destination is a unicast and the address is not in the MAC address table, the switch forwards the frame to all ports except the receiving port.
4. If the destination is a unicast, the address is in the MAC address table, and the associated interface in the MAC address table is not the receiving interface, the switch forwards the frame to the correct interface.
5. If the above rules do not occur, filter the frame.

Question 26

**Under what conditions would a switch flood a frame?**

Answer 26

A switch will flood a frame if the MAC address table is full, if the destination MAC address has not been learned by the switch, or if the frame is a broadcast or multicast frame.

Question 27

**What is the switch MAC address table used for?**

Answer 27

The switch MAC address table forwards traffic out the appropriate interface.

Because switches operate at Layer 2 of the OSI model, they switch traffic by MAC address. Instead of flooding traffic out all interfaces, a switch learns the MAC address of devices on each interface and only forwards traffic destined to the host on the interface. The learned MAC addresses are stored in the switch’s MAC address table.

Question 28

**Describe full-duplex transmission.**

Answer 28

Full-duplex transmission is achieved by setting switch interfaces, router ports, and host NICs to full duplex. Microsegmentation, where each network device has its own dedicated segment to the switch, ensures that full duplex will work properly. Because the network device has its own dedicated segment, it does not have to worry about sharing the segment with other devices. With full-duplex transmission, the device can send and receive at the same time, effectively doubling the amount of bandwidth between nodes.

Three points to remember about the operation of full-duplex communication are

- There are no collisions in full-duplex mode.
- A dedicated switch port is required for each full-duplex node.
- The host network card and the switch port must be capable of operating in full-duplex mode.

Question 29

**What are the advantages of using full-duplex Ethernet instead of half-duplex?**

Answer 29

Full-duplex provides faster data transfer by being able to send and receive simultaneously and operates without collisions.

NOTE

By enabling full-duplex on a port, you are disabling CSMA/CD on the segment.

Question 30

**How does replacing a hub with a switch affect CSMA/CD behavior in an Ethernet network?**

Answer 30

It effectively eliminates collisions.

Replacing a hub with a switch effectively eliminates collisions because each switch port is a separate collision domain. One device per switch port and configured for full-duplex operation eliminates the need for CSMA/CD.

Question 31

**What command allows you to view the duplex and speed settings configured for a switch port?**

Answer 31

To view the duplex and speed setting configured for a switch port, enter the **show interface** _interface-id_ command, as follows:

```Plain
Cat2960\#show interface f0/1
FastEthernet0/1 is up, line protocol is up
  Hardware is Fast Ethernet, address is 0019.e81a.4801
    (bia 0019.e81a.4801)
  MTU 1500 bytes, BW 10000 Kbit, DLY 1000 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA, loopback not set
  Keepalive set (10 sec)
  Auto-duplex, Auto-speed, media type is 10/100BaseTX
  input flow-control is off, output flow-control is unsupported
  ARP type: ARPA, ARP Timeout 04:00:00
```

Question 32

**Can a network hub be connected to a switch port in full-duplex mode?**

Answer 32

No. Because a hub shares access to the segment, it must connect to a switch port in half-duplex mode to be able to detect collisions.

NOTE

CSMA/CD is not enforced when full-duplex is configured.

Question 33

**When troubleshooting a switch interface operating in full-duplex mode, which error condition can be immediately ruled out?**

Answer 33

Collisions can be ruled out.

Remember, collisions occur only on half-duplex links. There are no collisions on full-duplex links.

Question 34

**An end user complains of slow access to the network. You issue the** show interface **command on the port the end user is connected to and you see a lot of collisions and runts on the interface. What is most likely the cause of the problem?**

Answer 34

A duplex mismatch is most likely the cause.

Although there are many things that can cause network slowness, the key here is when you issue the **show interface** command, you see many collisions and runts. A duplex mismatch will not only cause the end user to experience network slowness but also cause many collisions and runts on the switch interface.

Question 35

**An end user complains of slow access to the network. You issue the** show interface **command on the port the user is connected to and you see a lot of collisions and cyclic redundancy check (CRC) errors on the interface. What can be several causes for the problem?**

Answer 35

The most likely causes of the problem are a bad network cable, damaged media, or EMI.

Excessive collisions and CRC errors usually indicate a problem with the network cable attached to the port, or outside interference.

Question 36

**You connect two switches using a straight-through UTP Cat 6 cable. The port link lights between the switches are not coming on. What is the problem?**

Answer 36

The problem is with the cable. A straight-through cable is used to connect data terminal equipment (DTE) devices to data communications equipment (DCE) devices. A switch is considered a DCE device, and so are hubs. DTE devices include computers, printers, servers, and routers. For two like devices to connect to each other, a crossover cable is needed. In this case, replacing the cable with a crossover cable will fix the problem.

Question 37

**You have a port on your switch that is not working properly. You enter the** show interface **command on the faulty port and the port status says “errDisable.” What are some possible causes for this error?**

Answer 37

If you are having connectivity issues and the port state shows “errDisable,” the following issues can be causing this error:

- EtherChannel misconfiguration.
- Duplex mismatch.
- Bridge protocol data unit (BPDU) port guard has been enabled on the port.
- Unidirectional Link Detection (UDLD).
- A native VLAN mismatch.

Question 38

**Traffic between two switches is slow. You issue the** show interface **command on the uplink between the two switches and you see the following:**

```Plain
!output omitted!
0 input packets with dribble condition detected
     180749 packets output, 8004302 bytes, 0 underruns
     0 output errors, 45345 collisions, 0 interface resets
     0 babbles, 45345 late collision, 0 deferred
     0 lost carrier, 0 no carrier
     0 output buffer failures, 0 output buffers swapped out
```

**What are several possibilities for this problem?**

Answer 38

The switch port is receiving a lot of late collisions. The problem can be a duplex mismatch or a faulty port, or the distance between the two switches might exceed the cable specifications.

NOTE

Duplex mismatches occur when the connecting ends are set to different duplex modes, or when one end’s duplex is configured and the other end is set to autonegotiation.

Question 39

**What is the cause of multiple collisions on a port?**

Answer 39

Multiple collisions are the number of times the transmitting port had more than one collision before successfully transmitting a frame. If you experience multiple collisions on a port, the problem usually lies with an oversaturated medium.

Question 40

**While troubleshooting a switched network, you see the following on a switch interface that is having connectivity problems:**

```Plain
!output omitted!
  5 minute input rate 10000 bits/sec, 8 packets/sec
  5 minute output rate 10000 bits/sec, 7 packets/sec
     1476671 packets input, 363178961 bytes, 0 no buffer
     Received 20320 broadcasts (12683 multicast)
     2345 runts, 0 giants, 0 throttles
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
```

**What could be the cause of the problem?**

Answer 40

The switch is receiving a lot of runts. Runts are frames smaller than 64 bytes with a bad frame check sequence (FCS). Bad cabling or inconsistent duplex settings usually cause runts.