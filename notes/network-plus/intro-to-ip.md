# [Intro to IP]

**Source:** Professor Messer Network+ (N10-009)
**Date:** July 31 2026

## The gist



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

DHCP(continue from where you left off, minute 6:22) 

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


## Didn't stick / revisit


## Links to hands-on
