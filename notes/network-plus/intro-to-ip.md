# [Intro to IP]

**Source:** Professor Messer Network+ (N10-009)
**Date:** July 31 2026

## The gist
The different types of protocols, which port numbers they use and how to send data across different types of methods, devices through the networks. 


## Key points
Best analogy is network topologyu is the road(Ethernet, DSL, cable system), IP is a truck with boxes, TCP and UDP is Boxes
App info is stuff in the box. 

Ethernet payloads hold the IP and IP payloads, while the IP payload holds the TCP and TCP payload such as http data(Look at example 1.1)

TCP and UDP are two diff ways of moving data from place to place. They're OSI layer 4. This layer allows multiplexing, which is 
Sending data at the same time to multiple diff devices

TCP Transmission Control protocol known as connection oriented protocol. Formal setup and close process. Reliable delivery, so if
data is sent from a sender, it acnkowledges that data was sent, and if not sent, wont say anything, thus can indicate error occurred. 
Also numbered, so receiving end can request data thats been lost along the waey without having to recreate packet or data. Allows flow control
(Send data slower or faster) 

UDP - User datagram protocol is connectionless comm. No formal open or close. Known as "unreliable delivery" due to lack of acknowledgements.
Since no ack, cant perform error recovery or resend data that wasnt transmitted. No flow control either. 

Destination Ip address every computer has an ip address. Each ip is provided TCP or UDP port number(Port 23, 80 etc) to send data
to the right room, like how delivery people can send "Office desk" to "Office room" 

IPv4 sockets have either server or client. Server: server ip address, protocol, server app port number.
Client: client ip address, protocol, client port number

Non-ephemeral ports are permanent port numbers. Ports 0 through 1,023. Usually on server or service.

Ephemeral ports are temporary port numbers. So ports 1024 - 65,535. Not hard rule as servers can use Eph ports 

TCP and UDP ports can be between 0 and 65,535. Most use non-ephemeral, some use eph. Port numbers only for comm,not security. 
Browser already knows to use either port 80 or port 443. "Well known" if change, all clients have to use new port numbers.
TCP port numbers aren't the same as UDP port numbers. TCP 80 is not UDP 80. 

Ports on the network: If a client wants to communicate to a server with a tcp, VoIP server with a udp and an email server with a tcp
and can use all of them at the same time because of the diff port numbers. check 1.2 for the example. 
Essentially, the ip address from the client sends data to the ip address of the server(being the destination IP address), and if
server wants to send data back, it reverses the source IP with destination IP as well as the TCP source port and TCP dest port. 

Well known/common ports

FTP - File transfer protocol. generic file transfer method, uses tcp/20 is file transfer process while tcp/21 is control. uses
username and pass authetnication, and you can list, add delete for file maintenance. 

SSH - Secure shell uses tcp/22 allows you to comomunicate to a remote device form console, able to configure using text based command interface.
All comunication between yours and remote is encrypted.

SFTP - Secure FTP allows transfer files from 1 device to another encrypted. usesSSH protocol, so TCP/22. Allows file management. 
(resuming interrupted transfers, directory listings, remotee file removal)

Uses ssh can use remote file communication using TCP/22, all encrypted.

Telnet - Telecommunication network uses TCP/23. Looks identical to SSH, but no encryption. Not best for production systems. 

SMTP - Simple Mail Transfer Protocol

SMTP is server to server email transfer. TCP/25 uses plaintext SMTP while tcp/587 uses TLS encryption(Transport layer security)
Also used to send mail from device to server, configured on mobile devices and email clients.
Other protocols are used such as IMAP, or POP3

DNS - Domain Name system. uses UDP/53, converts names to ip addresses. www.cybersecjourney.com = 162.159.246.164. If its large transfer,
you can use TCP/53. 
Very critical, multiple DNS servers are in production. 

DHCP configures ip addresses automatically, subnet mask and others. uses udp/67, udp/68. uses dhcp serve. uses SOHO router
dynamic/pooled adressed in real time, and has a lease that must be renewed at intervals. Can also reserve addresses using MAC address of device

TFTP Trivial file transfer protocol. Uses udp/69. used for simple file transfer apps. Reads files and writes files. No AUTH, not secure. uses DHCP to get ip, tftp to transfer files fast and easy. 

HTTP and HTTPS - Hyper text transfer Protocol. communication through browser. If no encryption, uses tcp/80, if encrypted, uses SSL(Secure sockets layer) or TLS(Transport layer security), uses tcp/443. sends HTTPS for secure. 

NTP - Network time protocol. any devices(Switches routers, firewalls, servers etc) has its own synchronized clock using udp/123. Critical for log files, auth info, outage details. updates automatically, also flexible and you can control how they are upodated. Very accurate, 1 ms difference between devices on a network. 

SNMP - Simple Network management Protocol. uses udp/161 to query devices and receive info on device performance. Diff versions may be used, v1 is original. alows single query for single response, in the clear. V2 allows bulk transfers, receive and send large data, still in the clear(no encrypt). V3 secure standard, message integrity, authentication, and encryption. 

LDAP / LDAPS (Lightweight directory access protocol) uses tcp/389. A form of database, store and retrieve info in a network directory. LDAPS is secure, nonstandard version. uses tcp/636. LDAP is hiearchal, look at example (2.1). For example, O would be organization, OU would be under O for example "production" or "Engineering" and CN(Common name) would be a device or a file directory like "Tech docs".

SMB - Server Message block. Microsoft unique feature for file sharing, printer sharing. also called CIFS (COmmon Internet file system). integrated into windows OS. Allows file share, remote printing, and file locking. direct over tcp/445

Syslog - standard for message logging. Diverse systems, consolidates log. uses udp/514. Central log collecter, integrated into SIEM(Security info and event manager) Need a lot of disk space. 

Databases - collection of info. SQL (Structure Query Language) standard language across database servers.
MS-SQL uses tcp/1433.
RDP - Remote Desktop Protocol. Uses tcp 3389. Allows you to view remote desktop. RDP clients exist for Windows, MacOS, iphone etc. 

SIP - Session intiiation protocol. VoIP signaling. uses tcp/5060 and tcp/5061. used as control protocol. (Call, ring, play b usy signal, hangup) can video conference, instant message, file transfer etc. 

ICMP Internet control message protocol. Text messaging for your network devivces. Not for data transfer, carried by IP. A way to send a msg to device to see if its alive. For example, ping command. uses ICMP. Can also tell you if a network is unreachable, or TTL expired in a deveice. 

GRE Generic routing encapsulation. Tunnel between two endpoints. Encapsulate info, send across tunnel, and decapsulate. Not encrypted. 

VPNs, encrypted data traversing public network. Can use concentrators that encrypt/decrypt access device. 

IPSec(Internet protocol security) Security for OSI layer 3. Authentication and encryption for every packet. provides signatures for every packet. Very standard protocol, two diff manufacture firewalls can communicate. Authentication Header(AH) and Encapsulation Payload(ESP) 

For IPSec to send data, create tunnel using Internet Key exchange(IKE), allows both side to agree on decrypt/encrypt keys.
Builds security association (SA). First Phase uses Diffie-Hellman to create shared secret key. uses udp/500. Rferred to as ISAKMP(Internet security assoctiatoinon and key maangement protocol) Phase 2. Coordinates ciphers and key sizes, negotriates an inbound and outbound SA for IPsec. look at example (3.1) 

Transport mode and tunnel mode. If we wanna send data using transport mode, use IPsec Header between IP header and data, but its in the clear.
Tunnel mode all data is encrypted. Adds New IP header(Includes destination of IPsec trailer) 

Authentication Header(AH) used to valdiate info receiving over IPsec tunnel. if only using AH, you send data in the clear but using additional hashing for keeping integrity of data. 
Encapsulation Security Payload(ESP encrypts the packet, puts ESP Header infront of data, and New IP Header infront of ESP header and Integrity check value at end of packet. 

Unicast 1:1 relationship. Sent between 2 stations. If web surfing, file transfering or email, all uses unicast. Does not scale optimally for real time streaming media. IPv4 and IPv6 uses it.,

Multicast - one to many of many. Multimedia delivery, stock exchange uses this. Very specialized. Hard to scale across large networks. used in both IPv4 and IPv6(a lot)

Anycast - one-to-one-of-many. Uses ipv4 and ipv6. Sends to single unicast address, whatever devices is closest receives traffic. For example anycast DNS requests. 

Broadcast One-to-all. One received by everyone, limimted to a broadcast domain, good for routing updates, ARP requests. used in IPv4, not used in IPv6. 


## Example
(1.1): 

````
Client ──────────────────────────────────────────────────────► Server

┌──────────┬──────────────────────────────────────────┬──────────┐
│ Ethernet │            Ethernet Payload              │ Ethernet │
│  Header  │                                          │ Trailer  │
└──────────┴──────────────────────────────────────────┴──────────┘

┌──────────┬──────┬───────────────────────────────────┬──────────┐
│ Ethernet │  IP  │            IP Payload             │ Ethernet │
│  Header  │      │                                   │ Trailer  │
└──────────┴──────┴───────────────────────────────────┴──────────┘

┌──────────┬──────┬──────┬────────────────────────────┬──────────┐
│ Ethernet │  IP  │ TCP  │        TCP Payload         │ Ethernet │
│  Header  │      │      │                            │ Trailer  │
└──────────┴──────┴──────┴────────────────────────────┴──────────┘

┌──────────┬──────┬──────┬────────────────────────────┬──────────┐
│ Ethernet │  IP  │ TCP  │         HTTP data          │ Ethernet │
│  Header  │      │      │                            │ Trailer  │
└──────────┴──────┴──────┴────────────────────────────┴──────────┘
````
(1.2):

Common server ports:
- Web server   — tcp/80
- VoIP server  — udp/5004
- Email server — tcp/143

````
Client                                                          Server
10.0.0.1  ──────────────────────────────────────────────────►  10.0.0.2

┌──────────────────────────┬────────────────────────┬──────────────────┐
│ Source IP = 10.0.0.1     │ TCP Source Port = 3000 │    HTTP data     │
│ Dest   IP = 10.0.0.2     │ TCP Dest   Port = 80   │                  │
└──────────────────────────┴────────────────────────┴──────────────────┘

┌──────────────────────────┬────────────────────────┬──────────────────┐
│ Source IP = 10.0.0.1     │ UDP Source Port = 7100 │    VoIP data     │
│ Dest   IP = 10.0.0.2     │ UDP Dest   Port = 5004 │                  │
└──────────────────────────┴────────────────────────┴──────────────────┘

┌──────────────────────────┬────────────────────────┬──────────────────┐
│ Source IP = 10.0.0.1     │ TCP Source Port = 4407 │    Email data    │
│ Dest   IP = 10.0.0.2     │ TCP Dest   Port = 143  │                  │
└──────────────────────────┴────────────────────────┴──────────────────┘
        IP layer                  TCP/UDP layer            payload
````

(2.1):
````
                          [ Root ]
                     ┌───────────────┐
                     │ Messer Studios│  (O)
                     └───────┬───────┘
             ┌───────────────┼────────────────┐
             │               │                │
      ┌──────┴─────┐  ┌──────┴─────┐   ┌──────┴──────┐
      │ Production │  │  Support   │   │ Engineering │
      │    (OU)    │  │    (OU)    │   │    (OU)     │
      └──────┬─────┘  └────────────┘   └──────┬──────┘
         ┌───┴────┐              ┌────────────┼────────────┐
         │        │              │            │            │
      ┌──┴──┐ ┌───┴───┐      ┌───┴───┐  ┌─────┴─────┐  ┌───┴──┐
      │Jack │ │Daniel │      │Teal'c │  │ Tech Docs │  │ Sam  │
      │(CN) │ │ (CN)  │      │ (CN)  │  │   (CN)    │  │(CN)  │
      └─────┘ └───────┘      └───────┘  └───────────┘  └──────┘
                                          [resource]
````

(3.1): 
````
PHASE 1
                 ╭──────────────────────────────────╮
  ┌────────┐     │        ISAKMP Tunnel             │     ┌────────┐
  │ Router │·····│           udp/500                │·····│ Router │
  └────────┘     ╰──────────────────────────────────╯     └────────┘


PHASE 2
                 ╭──────────────────────────────────╮
  ┌────────┐     │        ISAKMP Tunnel             │     ┌────────┐
  │ Router │·····│ ┌──────────────────────────────┐ │·····│ Router │
  └────────┘     │ │        ESP Tunnel            │ │     └────────┘
                 │ └──────────────────────────────┘ │
                 ╰──────────────────────────────────╯
````

## Didn't stick / revisit


## Links to hands-on
