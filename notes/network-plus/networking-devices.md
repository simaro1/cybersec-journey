# [Networking devices    ]

**Source:** Professor Messer Network+ (N10-009)
**Date:** July 26 2026

## The gist
One or two lines. What is this thing, in plain language?

## Key points
Router routes traffic between ip subnets, aka "layer 3 switches" layer2/layer3. connects LAN, WAN, copper, fiber
Switch is layer 2, can give PoE and multilayer ones include routing function
Trad firewalls filters TCP and port number, new ones also filter applications. Sits on ingress/egress of network, 
provides NAT and dynamic routing.
IDS detects and alarms, IPS prevents before getting in network. detects/prevents exploits against apps.
Load balancer distributes load across multople servers using web servers and database farms. If one server fails, it can take out 
bad server using remaining devices. can perform tcp offload, SSL offload, caching for fast response, and QoS prioritzation

Proxies sit between user and external network, receives and sends requests on their behalf. Can cache info, URL filter and scan content
some proxies may need you to configure app or os, but invisible proxies dont. 

NAS provides file level access. So when tryna access info in a file in NAS, bring out whole file into system memory and to change or 
write in it, write the entire file back to NAS.

SAN(Storage area network) is just efficient reading and writing. The two require a lot of bandwith, so it may use an isolated netowrk
and high-speed network tech. 

Access point used for wireless communication and wireless communication only. Layer 2 device that is a bridge between wireless and wired, connected to ethernet
Wireless networks everywhere. Very pervasive, not a single access point. May not even be in the same building, One or more at every remote site. Configs may change at any moment. Seamless to suers
Wireless LAN controllers centralized management of access points. Can deploy new Access points, performance and security monitoring, config and deploy to all sites, report access point use and usually proprietary system

network functions

CDN(Content delivery network) speeds up process of data being geographically distrubted. can be a CDN in NA, africa, asia etc. used on many sites
VPN encrypt communication on insecure mediusm. Uses contentrators/head-ends that is an access device for encrypt/decrypting. integrated in firewalls, deployed either thru software or cryptographic hardware. sometimes
built in OS. 
QoS (Quality of service) controls bandwith usage or data rates and you can manage it based on priority between apps. to control it you can use router,switch or firewalls. 
TTL(Time to live) some systems just keep going and going with tasks so we can create timers that can stop these systems from occuring or we can also put them in a cache for like a minute or two before its cleared
Routing loops is basically when a system loops back from route 1 to route 2 for example continuously unless there is a TTL implemented to stop that loop
IP TTL is used in hops. Mac has 64, windows has 128. Each time a router processes packet, it decreases TTL by one. then once it reaches zero, it drops the packet. 
DNS TTL is in seconds. For example, you use dig command and it outputs the IP address for the specific website, it'll tell you 300 for example. that 300 means keep this in the cache for 300s(5m) and then delete
and if we want it back again, we use the command again. 



## Example


## Didn't stick / revisit


## Links to hands-on
