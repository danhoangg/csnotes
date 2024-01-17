Subjects/ Topics: #Network #TCPIP #OSI
Links: [[Networks 2]]

- Multiple computers that are connected together and can share information and resources
- Internet is a network of networks

**WAN** - Wide Area Network
- A network that extends over a large geographic area
**LAN** - Local Area Network
- A network that covers a small geographic area
**MAN** - Metropolitan Area Network
**PAN** - Personal Area Network
- Short-range network around a person

- Networking is embedded in many computing paradigms
- Networking issues can make otherwise correct code misbehave or go slow

#### Layered Network Models

- OSI model
	- Application
	- Presentation
	- Session
	- Transport
	- Network
	- Data Link
	- Physical
- TCP/IP mode
	- Application
	- Transport
	- Internet
	- Link

**What is a layered model**
- Abstraction
- Irrespective of the underlying hardware and topology
	- Applications can talk to each other
	- Hosts can talk to each other

- The network
	- Is responsible for providing best-effort connections
	- Should be essentially transparent
- End hosts are responsible for reliability and security

**Layer Encapsulation**
- Each layer in the TCP/IP stack adds it's own header to the data
- This becomes the payload for the next layer
![[tcpip.png]]

**Network Access Layer**
- Deals with the local link that a host is connected to
- Each host has a link-unique address (48-bit MAC address)

**Physical Standards**
- LAN defined by the IEEE 802 family of standards
	- Ethernet
	- Wireless LAN
	- Wireless Personal Area Networks
		- Bluetooth
		- Low-rate WPAN

**Internet Layer**
- Three basic functions
	- Handles next-hop routing
	- Provides unique addressing
	- Passes a received packet's payload to the correct transport layer
 - Facilitates connection of different types of network
 - The Internet layer only provides a 'best-effort' packet delivery

**IPv4**
- Internet Protocol version 4
- Each node has a unique 32-bit IP address
- Written in octet-grouped dotted-decimal notation
- Variable length header, minimum of 20-bytes
However
- 32-bit address space = about 4.3 billion addresses
- Exhaustion anticipated since 1980s
- IANA allocated their last blocks to RIRs on 3/02/2011
- Two solutions
	- Address reclamation/ recycling
	- IPv6

**NAT & NAPT**
- A way to share one IPv4 address between multiple computers
	- e.g. a home router shares one public IPv4 address with multiple devices with private IPv4 addresses
- RFC1918 'private' address space
- Not a real solution:
	- NAPT breaks the end-to-end principle and some protocols
	- Even with NAT, we still have IPv4 exhaustion
	- Gives a false sense of security - NAT is not a replacement for a properly configured firewall

**Address Recycling**
- There is a booming market in used IP address space
- Some registrars can only give you recycled address space

**IPv6**
- Each node has a unique 128-bit IP address
- Written in colon-delimited hexadecimal
- 40-byte header

**Subnets**
- You will come across addresses written like 2001:730:d0::/64
- For IPv4 you might see something like 192.168.0.0/24 or with another number like 255.255.255.0 following them
- These indicate how many bits of the address are shared by computers in the same subnet
- A subnet(work) is a logical subdivision of a network
- Traffic between two subnets has to go via a router

**Routing**
- Occurs where there is a change in IP address spaces
- Routing occurs at the internet layer
- Each router has an IP address in each address space it routes between
- Routers can also have other functions: Firewalling, DNS, DHCP, etc.
Multiple routes
- There can be multiple possible paths between two hosts
- This is for redundancy, improved performance of commercial reasons

**Transport layer**
- Provides host-to-host communication
- TCP and UDP
- Some other specialised protocols
	- Point to Point tunnelling protocol
	- Cubesat Space Protocol

**TCP and UDP**

|  | Transmission Control Protocol | User Datagram Protocol |
| ---- | ---- | ---- |
| Connection | Connection oriented | Connectionless |
| Reliability | Handles ACK and retransmissions | Application needs to handle ACK and retransmissions if needed |
| Data Order | Guaranteed arrives in the order sent | No guarantee data received is in order sent |
| Header | 20-bytes minimum | 8-bytes |
| Good for | Applications that need high reliability | Applications that need fast and efficient transmission |
| Example Protocols | HTTP(S), FTP, SMTP, Telnet, SSH | DHCP, TFTP, SNMP, RIP, RTP, COAP |
**TCP Flow/Congestion Control**
- Flow Control
	- Prevents a fast sender overwhelming a slow receiver
- Congestion control
	- Reduces send rate to cope with network congestion

- TCP uses a sliding window protocol to control the sending rate
- Sender should only send if the receiver indicates it has buffer space to accept data
- The sliding window is effectively the buffer space the receiver says it has available

- Sender starts by sending small packets
- Sender increases the size of each subsequent packet until there is packet loss
- Sender restarts the cycle with a lower threshold
- Causes TCP's typical sawtooth throughput
![[congestion control.png]]

**Application layer**
- Software that uses the network
- Generally, programmers will use pre-made libraries BUT need to choose appropriate modes