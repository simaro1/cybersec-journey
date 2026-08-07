# [Network topologies and Architectures]

**Source:** Professor Messer Network+ (N10-009)
**Date:** August 6 2026

## The gist
The different types of archietctures and topologies that networks use to distribute, deliver, transfer traffic within and between
one another. 

## Key points
Star/ hub and spoke network. Used in most large networks. 
One central hub that are connected through ethernet to onto devices. The central hub is central device, while its in the middle
Mesh has multiple links to the same place. If one link fails, other links can complete it. LOAD BALANCING. used in wide area netowkrs (WAN)
fully and partially meshed. 

Hybrid could have star or mesh. 
Spine and leaf architecture. You have the spine switches which are at the top, connected below it are the leaf switches
which connected below the leaf switches can be the devices such as image server, web server etc. Fast and redundant, but costly
if you wanna add switches to it. Simple cabling tho
Point-to-point is old, "Point-to-point T1". can be used on campus if you wanna connect from one building to another. 

Network architectures:
Three-tier architectures.
  Starts with core. This is the center of the network, Web servers, databases, applications
  Then the distrubter, a mid point between core and user, manages the path to the end users
  Then the access where users connect. think end stations or printers.
look at example (1.1) for diagram.
For example on campus building, users can be connected to access switches which are connected to distrubutors in the building
and the building can be coinnected to cores located at some central data center. 

Smaller orgs may use Collapsed core architecture. 
Two tier model:
Collapsed core 
Access point
Cheaper but not as redundant, harder to manage if you lose any component. 

Traffic flows - 
Important to know where they come from. One way is east west traffic. Means traffic is from the same data center, so 
fast response time.
If its leaving or coming into datacenter, known as north-south traffic. Different security posture, so a bit less secure. 
## Example

(1.1) Three tier architecutre:
````
 CORE            ┌───────┐              ┌───────┐
                  │ Core  │              │ Core  │
                  │Router │              │Router │
                  └───┬───┘              └───┬───┘
                      │                      │
──────────────────────┼──────────────────────┼──────────────────────
                      │                      │
 DISTRIBUTION    ┌────┴────┐            ┌────┴────┐
                  │  Dist   │────────────│  Dist   │
                  │ Switch  │╲          ╱│ Switch  │
                  └──┬───┬──┘ ╲        ╱ └──┬───┬──┘
                     │    ╲    ╲      ╱    ╱    │
──────────────────────┼─────╲────╲──╱────╱─────┼──────────────────────
                     │      ╲    ╲╱    ╱      │
 ACCESS         ┌────┴───┐ ┌──╲───/─┐ ┌────┴───┐  ┌────────┐
                 │ Access │ │ Access │ │ Access │  │ Access │
                 │ Switch │ │ Switch │ │ Switch │  │ Switch │
                 └─┬────┬─┘ └─┬────┬─┘ └─┬────┬─┘  └─┬────┬─┘
                   │    │     │    │     │    │      │    │
                  💻   🖥️    💻   🖥️    💻   🖥️     💻   🖥️
````

## Didn't stick / revisit


## Links to hands-on
