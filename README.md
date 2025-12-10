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

**_39.What is ICMP? What is it used for?_**

- ICMP stands for Internet Control Message Protocol. It is a protocol used for diagnostic and control purposes in IP networks. It is a part of the Internet Protocol suite, operating at the network layer.

- ICMP messages are used for a variety of purposes, including:
 - 1.Error reporting: ICMP messages are used to report errors that occur in the network, such as a packet that could not be delivered to its destination.

 - 2.Ping: ICMP is used to send ping messages, which are used to test whether a host or network is reachable and to measure the round-trip time for packets.

 - 3.Path MTU discovery: ICMP is used to discover the Maximum Transmission Unit (MTU) of a path, which is the largest packet size that can be transmitted without fragmentation.

 - 4.Traceroute: ICMP is used by the traceroute utility to trace the path that packets take through the network.

 - 5.Router discovery: ICMP is used to discover the routers in a network.

**_40.What is NAT? How does it work?_**

- NAT stands for Network Address Translation. It’s a way to map multiple local private addresses to a public one before transferring the information. Organizations that want multiple devices to employ a single IP address use NAT, as do most home routers. For example, your computer's private IP could be 192.168.1.100, but your router maps the traffic to its public IP (e.g. 1.1.1.1). Any device on the internet would see the traffic coming from your public IP (1.1.1.1) instead of your private IP (192.168.1.100).

**_41.Which port number is used in each of the following protocols?:_**
- **_SSH_** - 22
- **_SMTP_** - 25
- **_HTTP_** - 80
- **_DNS_** - 53
- **_HTTPS_** - 443
- **_FTP_** - 21
- **_SFTP_** - 22

**_42.Which factors affect network performance?_**

- Several factors can affect network performance, including:

 - 1.Bandwidth: The available bandwidth of a network connection can significantly impact its performance. Networks with limited bandwidth can experience slow data transfer rates, high latency, and poor responsiveness.

 - 2.Latency: Latency refers to the delay that occurs when data is transmitted from one point in a network to another. High latency can result in slow network performance, especially for real-time applications like video conferencing and online gaming.

 - 3.Network congestion: When too many devices are using a network at the same time, network congestion can occur, leading to slow data transfer rates and poor network performance.

 - 4.Packet loss: Packet loss occurs when packets of data are dropped during transmission. This can result in slower network speeds and lower overall network performance.

 - 5.Network topology: The physical layout of a network, including the placement of switches, routers, and other network devices, can impact network performance.

 - 6.Network protocol: Different network protocols have different performance characteristics, which can impact network performance. For example, TCP is a reliable protocol that can guarantee the delivery of data, but it can also result in slower performance due to the overhead required for error checking and retransmission.

 - 7.Network security: Security measures such as firewalls and encryption can impact network performance, especially if they require significant processing power or introduce additional latency.

 - 8.Distance: The physical distance between devices on a network can impact network performance, especially for wireless networks where signal strength and interference can affect connectivity and data transfer rates.

**_43.What is APIPA?_**

- APIPA is a set of IP addresses that devices are allocated when the main DHCP server is not reachable

**_44.What IP range does APIPA use?_**

- APIPA uses the IP range: 169.254.0.1 - 169.254.255.254.

## Control Plane and Data Plane

**_45.What does "control plane" refer to?_**

- The control plane is a part of the network that decides how to route and forward packets to a different location.

**_46.What does "data plane" refer to?_**

- The data plane is a part of the network that actually forwards the data/packets.

**_47.What does "management plane" refer to?_**

- It refers to monitoring and management functions.

**_48.To which plane (data, control, ...) does creating routing tables belong to?_**

- Control Plane.

**_49.Explain Spanning Tree Protocol (STP)._**

- The Spanning Tree Protocol (STP) is a Layer 2 network protocol designed to prevent network loops in Ethernet networks that have redundant paths. Without STP, redundant links between switches would cause broadcast storms (frames circulating indefinitely) and MAC address table instability, leading to network failure.

- STP works by executing an algorithm to elect a single Root Bridge switch, calculating the best path to it, and then logically blocking any redundant ports to create a single, loop-free logical topology (a "spanning tree"). If an active link fails, STP automatically unblocks a standby path to restore connectivity, ensuring fault tolerance.

**_50.What is link aggregation? Why is it used?_**

- Link aggregation is the technique of bundling multiple physical network links (like Ethernet cables) into a single logical link. This combined link is often called a Link Aggregation Group (LAG) or a port channel.

It is used for two main reasons:

 - 1.Increased Bandwidth (Load Balancing): It multiplies the available throughput between devices (e.g., switches or a server and a switch). Traffic is distributed (load-balanced) across all bundled physical links.

 - 2.Redundancy/High Availability (Fault Tolerance): If one physical link fails, traffic is automatically and seamlessly shifted to the remaining active links in the bundle, preventing a network outage and ensuring continuous connectivity.

**_51.What is Asymmetric Routing? How to deal with it?_**

- Asymmetric routing occurs when the outbound packets from a source take a different network path to the destination than the inbound return packets take back to the source. While common and often a result of load balancing or multi-homed BGP networks, it becomes problematic for stateful devices like firewalls and NATs, which expect to see both directions of a session to track its state and can drop one-way return traffic.

- To deal with it, the goal is often to force symmetric traffic flow through stateful devices. Solutions include using Policy-Based Routing (PBR) to explicitly control the return path, adjusting routing protocol metrics (like BGP attributes) to steer traffic, or consolidating network egress points so that the same firewall sees both the request and the response.

**_52.What overlay (tunnel) protocols are you familiar with?_**

- VPN Protocols (Security/Remote Access):
  - IPsec (Internet Protocol Security)
  - SSL/TLS VPN (Used by OpenVPN and others)
  - L2TP (Layer 2 Tunneling Protocol)

- Network Virtualization (Data Centers/Cloud):
  - VXLAN (Virtual eXtensible Local Area Network)
  - GRE (Generic Routing Encapsulation)

- MPLS VPNs:
  - Used in Service Provider networks for creating BGP-based VPNs
 
 **_53.What is GRE? How does it work?_**

 - GRE, or Generic Routing Encapsulation, is a tunneling protocol that encapsulates one network layer protocol (the payload, like IPv6 or a private IP) inside the packets of another protocol (the delivery protocol, usually IPv4). It creates a virtual point-to-point link between two endpoints over an existing network, often the public internet, allowing non-IP protocols, or IP traffic from discontinuous private networks, to be routed transparently.

 - The process works by the tunnel's source router taking the original packet and adding a GRE header (which identifies the payload protocol) and then an outer IP header (the delivery header) with the tunnel endpoints' public IP addresses. This new packet is routed across the transit network to the tunnel's destination router. The destination router removes the outer IP and GRE headers (de-encapsulation) and forwards the original, inner packet to its final private destination.

**_54.What is VXLAN? How does it work?_**

- VXLAN (Virtual eXtensible Local Area Network) is a network virtualization technology designed to solve the scalability limits of VLANs in modern data centers and cloud environments. It creates a Layer 2 overlay network that can span a physical Layer 3 (IP) infrastructure (the underlay). Its primary benefit is providing massive network segmentation, supporting up to 16 million unique network segments using a 24-bit identifier called the VNI (VXLAN Network Identifier), far exceeding the 4,094 limit of traditional VLANs.

- VXLAN works by encapsulating the original Layer 2 Ethernet frame (the inner packet) into a UDP packet (the outer packet) for transport over the IP network. This process happens at a device called a VTEP (VXLAN Tunnel Endpoint). The destination VTEP receives the UDP packet, removes the outer headers (de-encapsulation), and forwards the original Ethernet frame to the destination device as if they were on the same local Layer 2 network, regardless of the underlying Layer 3 path.

**_55.What is SNAT?_**

- SNAT (Source Network Address Translation) is a process where a network device (like a router or firewall) replaces the private source IP address of an outbound packet with a public IP address before forwarding it to an external network (like the internet). This allows multiple devices on a private network to share a single public IP address for outgoing connections and is fundamental for enabling private networks to access the public internet.

**_56.Explain OSPF._**

- OSPF (Open Shortest Path First) is a routing protocol that can be implemented on various types of routers. In general, OSPF is supported on most modern routers, including those from vendors such as Cisco, Juniper, and Huawei. The protocol is designed to work with IP-based networks, including both IPv4 and IPv6. Also, it uses a hierarchical network design, where routers are grouped into areas, with each area having its own topology map and routing table. This design helps to reduce the amount of routing information that needs to be exchanged between routers and improve network scalability.

- The OSPF 4 Types of routers are:
 - Internal Router
 - Area Border Routers
 - Autonomous Systems Boundary Routers
 - Backbone Routers

**_57.What is latency?_**

- Latency is the time taken for information to reach its destination from the source.

**_58.What is bandwidth?_**

- Bandwidth is the capacity of a communication channel to measure how much data the latter can handle over a specific time period. More bandwidth would imply more traffic handling and thus more data transfer.

**_59.What is throughput?_**

- Throughput refers to the measurement of the real amount of data transferred over a certain period of time across any transmission channel.

**_60.When performing a search query, what is more important, latency or throughput? And how to ensure that we manage global infrastructure?_**

- Latency. To have good latency, a search query should be forwarded to the closest data center.

**_61.When uploading a video, what is more important, latency or throughput? And how to assure that?_**

- Throughput. To have good throughput, the upload stream should be routed to an underutilized link.

**_62.What other considerations (except latency and throughput) are there when forwarding requests?_**

- Keep caches updated (which means the request could be forwarded not to the closest data center)

**_63.Explain Spine & Leaf_**

- "Spine & Leaf" is a networking topology commonly used in data center environments to connect multiple switches and manage network traffic efficiently. It is also known as "spine-leaf" architecture or "leaf-spine" topology. This design provides high bandwidth, low latency, and scalability, making it ideal for modern data centers handling large volumes of data and traffic.
Within a Spine & Leaf network there are two main tipology of switches:

 - Spine Switches: Spine switches are high-performance switches arranged in a spine layer. These switches act as the core of the network and are typically interconnected with each leaf switch. Each spine switch is connected to all the leaf switches in the data center.

 - Leaf Switches: Leaf switches are connected to end devices like servers, storage arrays, and other networking equipment. Each leaf switch is connected to every spine switch in the data center. This creates a non-blocking, full-mesh connectivity between leaf and spine switches, ensuring any leaf switch can communicate with any other leaf switch with maximum throughput.

- The Spine & Leaf architecture has become increasingly popular in data centers due to its ability to handle the demands of modern cloud computing, virtualization, and big data applications, providing a scalable, high-performance, and reliable network infrastructure

**_64.What is Network Congestion? What can cause it?_**

- Network congestion occurs when there is too much data to transmit on a network and it doesn't have enough capacity to handle the demand.
This can lead to increased latency and packet loss. The causes can be multiple, such as high network usage, large file transfers, malware, hardware issues, or network design problems.

- To prevent network congestion, it's important to monitor your network usage and implement strategies to limit or manage the demand.

**_65.What can you tell me about the UDP packet format? What about the TCP packet format? How is it different?_**

- The UDP (User Datagram Protocol) packet format is extremely simple, consisting of a fixed 8-byte header with only four fields: Source Port, Destination Port, Length, and Checksum. This minimal overhead makes UDP fast and efficient, as it is connectionless and offers no guarantees on delivery or order.

- The TCP (Transmission Control Protocol) packet format, or segment, is significantly more complex, with a header that is a minimum of 20 bytes and can be up to 60 bytes. It includes all the UDP fields plus crucial extra fields like Sequence Number, Acknowledgment Number, Control Flags (like SYN, ACK, FIN), Window Size for flow control, and a Data Offset field to specify the header length.

- The difference in size and fields is because TCP is a connection-oriented protocol that must manage reliability, ordering, and flow control.

**_66.What is the exponential backoff algorithm? Where is it used?_**

- The Exponential Backoff algorithm is a collision resolution and error handling strategy where a system multiplicatively increases the waiting time between successive retries of a failed operation. When a network failure, collision, or server overload occurs, the device first waits a short delay, and for each subsequent failure, the delay typically doubles (e.g., 1s, 2s, 4s, 8s, etc.). This delay often includes a small randomized component (jitter) to prevent multiple devices from synchronizing and retrying at the exact same moment, which would cause another wave of collisions or overloads.

- It is widely used in networking and distributed systems to improve resilience and prevent network congestion. Key applications include: Ethernet and Wi-Fi networks (using the Binary Exponential Backoff variant in CSMA/CD and CSMA/CA) to resolve packet collisions; TCP retransmission to handle lost packets; and in client-server APIs (like Google, AWS, and Stripe) to gracefully handle transient errors, rate limiting (`429` status codes), and server overloads (`5xx` status codes) without overwhelming the service.

**_67.Using Hamming code, what would be the code word for the following data word 100111010001101?_**

- 00110011110100011101

**_68.Give examples of protocols found in the application layer_**

- Hypertext Transfer Protocol (HTTP) - used for the webpages on the internet

- Simple Mail Transfer Protocol (SMTP) - email transmission

- Telecommunications Network - (TELNET) - terminal emulation to allow a client access to a telnet server

- File Transfer Protocol (FTP) - facilitates the transfer of files between any two machines

- Domain Name System (DNS) - domain name translation

- Dynamic Host Configuration Protocol (DHCP) - allocates IP addresses, subnet masks, and gateways to hosts
- Simple Network Management Protocol (SNMP) - gathers data on devices on the network

**_69.Give examples of protocols found in the Network Layer_**

- Internet Protocol (IP) - assists in routing packets from one machine to another

- Internet Control Message Protocol (ICMP) - lets one know what is going such as error messages and debugging information

**_70.What is HSTS?_**

- HTTP Strict Transport Security is a web server directive that informs user agents and web browsers how to handle its connection through a response header sent at the very beginning and back to the browser. This forces connections over HTTPS encryption, disregarding any script's call to load any resource in that domain over HTTP.

## Misc

**_71.What is the Internet? Is it the same as the World Wide Web?_**

- The internet refers to a network of networks, transferring huge amounts of data around the globe.

- The World Wide Web is an application running on millions of servers, on top of the internet, accessed through what is known as the web browser

**_72.What is the ISP?_**

- ISP (Internet Service Provider) is the local internet company provider.
