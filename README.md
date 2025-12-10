# Network-for-DevOps-Engineers

**_1.In general, what do you need in order to communicate?_**

- A common language (for the two ends to understand)
- A way to address who you want to communicate with
- A Connection (so the content of the communication can reach the recipients)

**_2.What is TCP/IP?_**

- A set of protocols that define how two or more devices can communicate with each other.

**_3.What is Ethernet?_**

- Ethernet simply refers to the most common type of Local Area Network (LAN) used today. A LAN—in contrast to a WAN (Wide Area Network), which spans a larger geographical area—is a connected network of computers in a small area, like your office, college campus, or even home.

**_4.What is a MAC address? What is it used for?_**

- A MAC address is a unique identification number or code used to identify individual devices on the network.

- Packets that are sent on the ethernet are always coming from a MAC address and sent to a MAC address. If a network adapter is receiving a packet, it is comparing the packet’s destination MAC address to the adapter’s own MAC address.

**_5.When is this MAC address used?: ff:ff:ff:ff:ff:ff_**

- When a device sends a packet to the broadcast MAC address (FF:FF:FF:FF:FF:FF​), it is delivered to all stations on the local network. Ethernet broadcasts are used to resolve IP addresses to MAC addresses (by ARP) at the data link layer.

**_6.What is an IP address?_**

- An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.An IP address serves two main functions: host or network interface identification and location addressing.

**_7.Explain the subnet mask and give an example._**

- A Subnet mask is a 32-bit number that masks an IP address and divides the IP addresses into network addresses and host addresses. Subnet Mask is made by setting network bits to all "1"s and setting host bits to all "0"s. Within a given network, out of the total usable host addresses, two are always reserved for specific purposes and cannot be allocated to any host. These are the first address, which is reserved as a network address (a.k.a network ID), and the last address used for network broadcast.

**_8.What is a private IP address? In which scenarios/system designs, one should use it?_**

- Private IP addresses are assigned to the hosts in the same network to communicate with one another. As the name "private" suggests, the devices having the private IP addresses assigned can't be reached by the devices from any external network. For example, if I am living in a hostel and I want my hostel mates to join the game server I have hosted, I will ask them to join via my server's private IP address, since the network is local to the hostel.

  **_9.What is a public IP address? In which scenarios/system designs, one should use it?_**

- A public IP address is a public-facing IP address. In the event that you were hosting a game server that you want your friends to join, you will give your friends your public IP address to allow their computers to identify and locate your network and server in order for the connection to take place. One time that you would not need to use a public-facing IP address is in the event that you were playing with friends who were connected to the same network as you, in that case, you would use a private IP address. In order for someone to be able to connect to your server that is located internally, you will have to set up a port forward to tell your router to allow traffic from the public domain into your network and vice versa.

**_10.Explain the OSI model. What layers there are? What each layer is responsible for?_**

- Application: user end (HTTP is here)
- Presentation: establishes context between application-layer entities (Encryption is here)
- Session: establishes, manages, and terminates the connections
- Transport: transfers variable-length data sequences from a source to a destination host (TCP & UDP are here)
- Network: transfers datagrams from one network to another (IP is here)
- Data link: provides a link between two directly connected nodes (MAC is here)
- Physical: the electrical and physical spec of the data connection (Bits are here)

**_11.For each of the following determines to which OSI layer it belongs:_**
- **_Error correction_** - Data link
- **_Packets routing_** - Network
- **_Cables and electrical signals_** - Physical
- **_MAC address_** - Data link
- **_IP address_** - Network
- **_Terminate connections_** - Session
- **_3-way handshake_** - Transport

**_12.What delivery schemes are you familiar with?_**

- Unicast: One-to-one communication where there is one sender and one receiver.

- Broadcast: Sending a message to everyone in the network. The address ff:ff:ff:ff:ff:ff is used for broadcasting. Two common protocols which use broadcast are ARP and DHCP.

- Multicast: Sending a message to a group of subscribers. It can be one-to-many or many-to-many.

**_13.What is CSMA/CD? Is it used in modern ethernet networks?_**

- CSMA/CD stands for Carrier Sense Multiple Access / Collision Detection. Its primary focus is to manage access to a shared medium/bus where only one host can transmit at a given point in time.

- CSMA/CD algorithm:

- 1.Before sending a frame, it checks whether another host is already transmitting a frame.
- 2.If no one is transmitting, it starts transmitting the frame.
- 3.If two hosts transmit at the same time, we have a collision.
- 4.Both hosts stop sending the frame and they send everyone a 'jam signal' notifying everyone that a collision occurred
- 5.They are waiting for a random time before sending it again
- 6.Once each host waited for a random time, they try to send the frame again and so the cycle starts again

**_14.Describe the following network devices and the difference between them:_**
**_router_**
**_switch_**
**_hub_**

- A router, switch, and hub are all network devices used to connect devices in a local area network (LAN). However, each device operates differently and has its specific use cases. Here is a brief description of each device and the differences between them:

- 1.Router: a network device that connects multiple network segments together. It operates at the network layer (Layer 3) of the OSI model and uses routing protocols to direct data between networks. Routers use IP addresses to identify devices and route data packets to the correct destination.

- 2.Switch: a network device that connects multiple devices on a LAN. It operates at the data link layer (Layer 2) of the OSI model and uses MAC addresses to identify devices and direct data packets to the correct destination. Switches allow devices on the same network to communicate with each other more efficiently and can prevent data collisions that can occur when multiple devices send data simultaneously.

- 3.Hub: a network device that connects multiple devices through a single cable and is used to connect multiple devices without segmenting a network. However, unlike a switch, it operates at the physical layer (Layer 1) of the OSI model and simply broadcasts data packets to all devices connected to it, regardless of whether the device is the intended recipient or not. This means that data collisions can occur, and the network's efficiency can suffer as a result. Hubs are generally not used in modern network setups, as switches are more efficient and provide better network performance.

**_15.What is a "Collision Domain"?_**

- A collision domain is a network segment in which devices can potentially interfere with each other by attempting to transmit data at the same time. When two devices transmit data at the same time, it can cause a collision, resulting in lost or corrupted data. In a collision domain, all devices share the same bandwidth, and any device can potentially interfere with the transmission of data by other devices.

**_16.What is a "Broadcast Domain"?_**

- A broadcast domain is a network segment in which all devices can communicate with each other by sending broadcast messages. A broadcast message is a message that is sent to all devices in a network rather than a specific device. In a broadcast domain, all devices can receive and process broadcast messages, regardless of whether the message was intended for them or not.

**_17.Three computers connected to a switch. How many collision domains are there? How many broadcast domains?_**

- Three collision domains and one broadcast domain

**_18.How does a router work?_**

- A router is a physical or virtual appliance that passes information between two or more packet-switched computer networks. A router inspects a given data packet's destination Internet Protocol address (IP address), calculates the best way for it to reach its destination, and then forwards it accordingly.

**_19.What is NAT?_**

- Network Address Translation (NAT) is a process in which one or more local IP addresses are translated into one or more Global IP address and vice versa in order to provide Internet access to the local hosts.

**_20.What is a proxy? How does it work? What do we need it for?_**

- A proxy server acts as a gateway between you and the internet. It’s an intermediary server separating end users from the websites they browse.

- If you’re using a proxy server, internet traffic flows through the proxy server on its way to the address you requested. The request then comes back through that same proxy server (there are exceptions to this rule), and then the proxy server forwards the data received from the website to you.

- Proxy servers provide varying levels of functionality, security, and privacy depending on your use case, needs, or company policy.

**_21.What is TCP? How does it work? What is the 3-way handshake?_**

- TCP 3-way handshake or three-way handshake is a process that is used in a TCP/IP network to make a connection between server and client.

- A three-way handshake is primarily used to create a TCP socket connection. It works when:
 - 1.A client node sends an SYN data packet over an IP network to a server on the same or an external network. The objective of this packet is to ask/infer if the server is open for new connections.

 - 2.The target server must have open ports that can accept and initiate new connections. When the server receives the SYN packet from the client node, it responds and returns a confirmation receipt – the ACK packet or SYN/ACK packet.

 - 3.The client node receives the SYN/ACK from the server and responds with an ACK packet.

**_22.What is round-trip delay or round-trip time?_**

- The length of time it takes for a signal to be sent plus the length of time it takes for an acknowledgment of that signal to be received"

**_23.How does an SSL handshake work?_**

- SSL handshake is a process that establishes a secure connection between a client and a server.

 - 1.The client sends a Client Hello message to the server, which includes the client's version of the SSL/TLS protocol, a list of the cryptographic algorithms supported by the client, and a random value.

 - 2.The server responds with a Server Hello message, which includes the server's version of the SSL/TLS protocol, a random value, and a session ID.

 - 3.The server sends a Certificate message, which contains the server's certificate.

 - 4.The server sends a Server Hello Done message, which indicates that the server is done sending messages for the Server Hello phase.

 - 5.The client sends a Client Key Exchange message, which contains the client's public key.
  
 - 6.The client sends a Change Cipher Spec message, which notifies the server that the client is about to send a message encrypted with the new cipher spec.

 - 7.The client sends an Encrypted Handshake Message, which contains the pre-master secret encrypted with the server's public key.

 - 8.The server sends a Change Cipher Spec message, which notifies the client that the server is about to send a message encrypted with the new cipher spec.

 - 9.The server sends an Encrypted Handshake Message, which contains the pre-master secret encrypted with the client's public key.

 - 10.The client and server can now exchange application data.

**_24.What is the difference between TCP and UDP?_**

- TCP establishes a connection between the client and the server to guarantee the order of the packages, on the other hand, UDP does not establish a connection between the client and server and doesn't handle package orders. This makes UDP more lightweight than TCP and a perfect candidate for services like streaming.

**_25.What TCP/IP protocols are you familiar with?_**

- Application Layer: HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, SSH, Telnet.

- Transport Layer: TCP (Transmission Control Protocol), UDP (User Datagram Protocol).

- Internet Layer (Network Layer): IP (Internet Protocol), ICMP, ARP, RARP.

- Link Layer (Data Link/Physical): Ethernet, Wi-Fi.

**_26.Explain the "default gateway"_**

- A default gateway serves as an access point or IP router that a networked computer uses to send information to a computer in another network or the internet.

**_27.What is ARP? How does it work?_**

- ARP stands for Address Resolution Protocol. When you try to ping an IP address on your local network, say 192.168.1.1, your system has to turn the IP address 192.168.1.1 into a MAC address. This involves using ARP to resolve the address, hence its name.

- Systems keep an ARP look-up table where they store information about what IP addresses are associated with what MAC addresses. When trying to send a packet to an IP address, the system will first consult this table to see if it already knows the MAC address. If there is a value cached, ARP is not used.

**_28.What is TTL? What does it help to prevent?_**

- TTL (Time to Live) is a value in an IP (Internet Protocol) packet that determines how many hops or routers a packet can travel before it is discarded. Each time a packet is forwarded by a router, the TTL value is decreased by one. When the TTL value reaches zero, the packet is dropped, and an ICMP (Internet Control Message Protocol) message is sent back to the sender indicating that the packet has expired.

- TTL is used to prevent packets from circulating indefinitely in the network, which can cause congestion and degrade network performance.

- It also helps to prevent packets from being trapped in routing loops, where packets continuously travel between the same set of routers without ever reaching their destination.

- In addition, TTL can be used to help detect and prevent IP spoofing attacks, where an attacker attempts to impersonate another device on the network by using a false or fake IP address. By limiting the number of hops that a packet can travel, TTL can help prevent packets from being routed to destinations that are not legitimate.

**_29.What is DHCP? How does it work?_**

- It stands for Dynamic Host Configuration Protocol and allocates IP addresses, subnet masks, and gateways to hosts. This is how it works:
 - A host upon entering a network broadcasts a message in search of a DHCP server (DHCP DISCOVER)
 - An offer message is sent back by the DHCP server as a packet containing lease time, subnet mask, IP addresses, etc (DHCP OFFER)
 - Depending on which offer is accepted, the client sends back a reply broadcast letting all DHCP servers know (DHCP REQUEST)
 - The server sends an acknowledgment (DHCP ACK)

**_30.Can you have two DHCP servers on the same network? How does it work?_**

- It is possible to have two DHCP servers on the same network, however, it is not recommended, and it is important to configure them carefully to prevent conflicts and configuration problems.
 - When two DHCP servers are configured on the same network, there is a risk that both servers will assign IP addresses and other network configuration settings to the same device, which can cause conflicts and connectivity issues. Additionally, if the DHCP servers are configured with different network settings or options, devices on the network may receive conflicting or inconsistent configuration settings.
 
 - However, in some cases, it may be necessary to have two DHCP servers on the same network, such as in large networks where one DHCP server may not be able to handle all the requests. In such cases, DHCP servers can be configured to serve different IP address ranges or different subnets, so they do not interfere with each other.

**_31.What is SSL tunneling? How does it work?_**

- SSL (Secure Sockets Layer) tunneling is a technique used to establish a secure, encrypted connection between two endpoints over an insecure network, such as the Internet. The SSL tunnel is created by encapsulating the traffic within an SSL connection, which provides confidentiality, integrity, and authentication.

- Here's how SSL tunneling works:

 - 1.A client initiates an SSL connection to a server, which involves a handshake process to establish the SSL session.

 - 2.Once the SSL session is established, the client and server negotiate encryption parameters, such as the encryption algorithm and key length, then exchange digital certificates to authenticate each other.

 - 3.The client then sends traffic through the SSL tunnel to the server, which decrypts the traffic and forwards it to its destination.

 - 4.The server sends traffic back through the SSL tunnel to the client, which decrypts the traffic and forwards it to the application.

**_32.What is a socket? Where can you see the list of sockets in your system?_**

- A socket is a software endpoint that enables two-way communication between processes over a network. Sockets provide a standardized interface for network communication, allowing applications to send and receive data across a network. To view the list of open sockets on a Linux system: `netstat -an`

- This command displays a list of all open sockets, along with their protocol, local address, foreign address, and state.

**_33.What is IPv6? Why should we consider using it if we have IPv4?_**

- IPv6 (Internet Protocol version 6) is the latest version of the Internet Protocol (IP), which is used to identify and communicate with devices on a network. IPv6 addresses are 128-bit addresses and are expressed in hexadecimal notation, such as 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

- There are several reasons why we should consider using IPv6 over IPv4:

 - 1.Address space: IPv4 has a limited address space, which has been exhausted in many parts of the world. IPv6 provides a much larger address space, allowing for trillions of unique IP addresses.

 - 2.Security: IPv6 includes built-in support for IPsec, which provides end-to-end encryption and authentication for network traffic.

 - 3.Performance: IPv6 includes features that can help to improve network performance, such as multicast routing, which allows a single packet to be sent to multiple destinations simultaneously.

 - 4.Simplified network configuration: IPv6 includes features that can simplify network configuration, such as stateless autoconfiguration, which allows devices to automatically configure their own IPv6 addresses without the need for a DHCP server.

 - 5.Better mobility support: IPv6 includes features that can improve mobility support, such as Mobile IPv6, which allows devices to maintain their IPv6 addresses as they move between different networks.

**_34.What is VLAN?_**

- A VLAN (Virtual Local Area Network) is a logical network that groups together a set of devices on a physical network, regardless of their physical location. VLANs are created by configuring network switches to assign a specific VLAN ID to frames sent by devices connected to a specific port or group of ports on the switch.

**_35.What is MTU?_**

- MTU stands for Maximum Transmission Unit. It's the size of the largest PDU (protocol Data Unit) that can be sent in a single transaction.

**_36.What happens if you send a packet that is bigger than the MTU?_**

- With the IPv4 protocol, the router can fragment the PDU and then send all the fragmented PDU through the transaction.

- With IPv6 protocol, it issues an error to the user's computer.

**_37.True or False? Ping is using UDP because it doesn't care about reliable connection_**

- False. Ping is actually using ICMP (Internet Control Message Protocol) which is a network protocol used to send diagnostic messages and control messages related to network communication.

**_38.What is SDN?_**

- SDN stands for Software-Defined Networking. It is an approach to network management that emphasizes the centralization of network control, enabling administrators to manage network behavior through a software abstraction.

- In a traditional network, network devices such as routers, switches, and firewalls are configured and managed individually, using specialized software or command-line interfaces. In contrast, SDN separates the network control plane from the data plane, allowing administrators to manage network behavior through a centralized software controller.
