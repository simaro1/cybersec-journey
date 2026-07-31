# [Designing the cloud]

**Source:** Professor Messer Network+ (N10-009)
**Date:** July 30 2026

## The gist
How cloud networks and virtual networks function. How you can deploy them and connect them with one another from the cloud to networks. 

## Key points
Virtual networks are servers with hundreds of virtual servers inside of them linking them all together
NFV replaces physical devices with virutal versions. Routers, switches, load balancers still exist here. Very easily deployable
Virtual private clouds host all the afromentioned such as routers, firewalls etc. Can have many. Need transit gateway to 
connect all the VPC's together. can have multiple VPC's. to connect to the remotely, can use VPN to create tunnel to the VPC's
VPC gateway/internet gateway connects users to the applications, and VPC NAT(Network address translation) allows communication from the VPC outward
VPC endpoints allows connection between cloud provider networks.
Security groups and lists are firewalls for the cloud, allows what goes in and out. can define tcp port number and add to rules
Can also add layer 3 addresses in security groups.
Network security list assigns security rules to an entire ip subnet. Difficult to provide granularity
Network security groups can assign rules to individual network interface cards, or vritual NIC(VNIC). look at example 1.1 for example
better granularity. 

Cloud deployment models public apps available over inetnert, private cloud private for local data center, hybrid for most enterprise
SaaS on demand software, no local installation, stuff like Gmail, M365, data is in cloud and you dont manage it yourself
Infrastructure as service, sometimes Haas, you're responsible with data and installing software. More control for your own data
Middle ground is PaaS(Platform as a service) Someone handles the platform, you handle the development. Building blocks by provider
you build with the blocks. Maintain the apps, provider keeps data safe. SalesForce.com is good example. 

Data, devices and accounts in all 4 are fully controlled by you. On Prem controles everything(On prem being you built it)
Identity and directory infrastructure is half you half provider with SaaS, so is apps and network controls with PaaS
OS, Physical hosts, physical network and physical datacenter provider hosted with SaaS and PaaS, while OS, apps, network controls in laaS is you controlled.
check 1.2 for visual example

## Example
(1.1):
```
  _______________________________________________________________________________________
|| GROUP: NSG-A / Direction: Inbound / Protocol: TCP / Port: 443 / IP Address: 0.0.0.0/0 ||
|| GROUP: NSG-B / Direction: Inbound / Protocol: TCP / Port: 22 / IP Address: 0.0.0.0/0  ||
  _______________________________________________________________________________________
 
 ___________________________________________________________________________________
|| Virtual private cloud:                                                            ||
||  VCN:                                                                             ||
||      NSG-A(10.1.10.1), NSG-A(10.1.10.2), NSG-B(10.1.10.3), NSG-B(10.1.10.4)       || 
||  Subnet X                                                                         ||
|| 10.1.0.0/24                                                                       ||
   __________________________________________________________________________________
  
```
(1.2):
```
                           ON-PREM      IaaS       PaaS       SaaS
┌────────────────────────┬──────────┬──────────┬──────────┬──────────┐
│ Information & data     │   YOU    │   YOU    │   YOU    │   YOU    │
│ Devices (PC, mobile)   │   YOU    │   YOU    │   YOU    │   YOU    │
│ Accounts & identities  │   YOU    │   YOU    │   YOU    │   YOU    │
├────────────────────────┼──────────┼──────────┼──────────┼──────────┤
│ Identity & directory   │   YOU    │   YOU    │  SHARED  │  SHARED  │
│ Applications           │   YOU    │   YOU    │  SHARED  │ PROVIDER │
│ Network controls       │   YOU    │   YOU    │  SHARED  │ PROVIDER │
├────────────────────────┼──────────┼──────────┼──────────┼──────────┤
│ Operating system       │   YOU    │   YOU    │ PROVIDER │ PROVIDER │
│ Physical hosts         │   YOU    │ PROVIDER │ PROVIDER │ PROVIDER │
│ Physical network       │   YOU    │ PROVIDER │ PROVIDER │ PROVIDER │
│ Physical datacenter    │   YOU    │ PROVIDER │ PROVIDER │ PROVIDER │
└────────────────────────┴──────────┴──────────┴──────────┴──────────┘
```



## Didn't stick / revisit
VPC concept

## Links to hands-on
