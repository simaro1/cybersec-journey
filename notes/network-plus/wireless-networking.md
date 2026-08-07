# [Wireless/Wired Networking]

**Source:** Professor Messer Network+ (N10-009)
**Date:** August 6th 2026

## The gist
How wifi cant be sent wirelessly and through wires, the different types of wires and ethernet types and the different
types of wireless types. 

## Key points
IEEE(the Institute of Electrical and Electronics Engineers) Create the manage the standard of wifi(eg, IEEE 802)
Wi-Fi Alliance handles interoperability testing. (Check example 1.1)

4G or LTE is used in cellphones or tablets, supports 150mbits/s download, while LTE-A supports 300mbits/s. GSM and CDMA providers
converged into standard. GSM and EDGE(Enhanced Data rates for GSM evolution)

5G, introduced in 2020, is much faster, theotirically up to 10Gbits/s. Higher frequencies, larger data transfers, faster and more
cloud processing. 
- 
Satelite technology can be used if traditional tech isnt available. Known as Non-terrestrial. 100mbit/s and 250ms up and down latenncy
but starlink is advertising 40ms and tryna go down to 20. 

Ethernets come in diff shapes and sizes, most popular standard, types like fiber optic are examples of ethernet. Standard
created by IEEE 802.3 committee. For example, 1000BASE-T is a gigabit ethernet that operates on Copper cabling and speeds at 1 gigabit per second.
See (2.1) for example. 

Deciphering a standard i.e 1000BASE-T, 100 refers to 1000mbit/s. if starts with 10G its 10 gbit/s. Base means baseband, which is a single frequency
using whole medium, broadband uses many frequencies and shares medium
the "-T" means its a twisted pair Copper, f is fiber, SX would be short for wavelength light. read entire standard, dont only rely on name.  

fiber comms use light to transmit. can be sent over long distances. immune to radio interference.

Fiber optic cables one end have LED other end is receiver, light goes through core, core covered by cladding and cladding covered by buffer coating
connector has a fiber core surrounded by ferrule. 

multimode fibers are short range, 2km, uses LED. core of fiber is large, so light can go through multiple different modes. 

single-mode fiber goes up to 100km without processing. smaller core, so single mode of light propagates through fiber. 

Copper Cabling
cabling is funadmental to network communication. always have right cables installed in right places to have best network
Twisted pair copper cabling.
Cables are twisted with one signal and the opposite signal so that when theres an issue, you can determine how the signal
is meant to be on the receiving end because one signal is always moving away from the interference. 
Signals are sent over the cable. Cables are also categorized by the IEEE 802.3. Such as category 5, category 6 etc.
1000BASE-T is categorized as category 5 for example. 

Coaxial Cables means the two or more forms share a common axis for example wire conductors, metal shielding etc.
RG-6 is whats used by television or digitial cable for high speed. 
If two conductors, its twinaxial(twwinax), means that theres two conductors, low cost, can 10gbit/s at lower cost but shorter distaqnce(five meters)

Space between drop ceiling and ceiling is plenum space. Network cables, heat signals, power cables are in this space.
If dead/noncirculating airspace is above the ceiling then thats no plenum. If active /circulating plenum airspace, then theres plenum

Plenum rated cables are made with polyvinyl chloride(PVC), thats traditional jacket. as well as fluorinated ethylene polymer (FEP) or 
low-smoke PVC. Plenum rated cables arent as flexible. Always use correct table, check where its beign run through before installing.


Transceiver
Combo fo transmitter and receiver. Provides modularity by adding the transceiver that matches my network. for example, i can use ethernet
or fibre channels, not compatible but different media types. 

SFP and SFP+(Small form-factor pluggable/ Enhanced Small form-factor pluggable) For example if you wanna connect fiber, you can
plug into your fiber sfp, and as well as copper to copper sfp. Transmits Gbit ethernet. SFP+ goes up to 16, common with 10gbit/s.

QSFP allows 4 channels of SFP, so 4Gbit/s. QSFP+ is 40Gbit/s. Q stand for quad. Saves cost 
SFP/SFP+ use same form factor, QSFP/QSFP+ use same form factor but larger than SFP. not 4x size. 

Types of fiber connectors
SC connectors are locked by pushing it in and they lock. commonly used in data centers. pull it to unlock. AKA subscriber
connector or square connector. 
LC connector locks in place and you need to press onto a clip to release it. AKA little connector or local connector. 
both combined in pair, plugged at the same time. one end is transmitter other is receive.
ST-Straight tip connector. You twist to lock it in place, turn to unlock.Uses bayonet connector.
MPO - Multi-fiber push on. Has 12 fibers in a single conector. saves spcae, manage one cable. Push to lock in place, pull to unlock.
AKA MTP abbreviation, or MTP MPO connector(Provided by corning) 

Copper connectors
RJ11 - Registered jack type 11. has 6 positions and 2 conductor(6p2C) uses by telephones and DSL connections. 
If ethernet, you use RJ45. Registered Jack type 45. Uses 8 position, 8 conductors. Modular connector. (8P8C) 
F-Connector is a coaxial cable. Standard threaded connector. AKA DOCSIS connector)Data over cable service interface specification) 
connects to cable modem. 
BNC(Bayonet Neill-concelman). Created by paul Neill(bell labs) and carl concelman (Amphenol)
common with twinax and DS3, twist and lock in place. USed for video connections. 

## Example

(1.1) Wi-Fi Standards (802.11)

| IEEE Standard | Generation Name | Frequencies                | Max theoretical link rate   |     Status     |
|----------------|-----------------|---------------------------|-----------------------------|----------------|
| 802.11a        | –               | 5 GHz                     | 6–54 Mbit/s                 | ⚠️ Outdated    |
| 802.11b        | –               | 2.4 GHz                   | 1–11 Mbit/s                 | ⚠️ Outdated    |
| 802.11g        | –               | 2.4 GHz                   | 6–54 Mbit/s                 | ⚠️ Outdated    |
| 802.11n        | Wi-Fi 4         | 2.4 GHz / 5 GHz           | 72–600 Mbit/s               | Legacy, still in use |
| 802.11ac       | Wi-Fi 5         | 5 GHz                     | 433–6,933 Mbit/s            | Common today   |
| 802.11ax       | Wi-Fi 6 and 6E  | 2.4 GHz / 5 GHz / 6 GHz   | 574–9,608 Mbit/s            | Current        |
| 802.11be       | Wi-Fi 7         | 2.4 GHz / 5 GHz / 6 GHz   | 1,376–46,120 Mbit/s         | Newest         |

(2.1) Ethernet Standards (802.3)

| IEEE Standard  | Description         | Media  | Network Speed         |
|-----------------|----------------------|--------|-------------------------|
| 1000BASE-T      | Gigabit Ethernet     | Copper | 1 gigabit per second    |
| 10GBASE-T       | 10 Gigabit Ethernet  | Copper | 10 gigabits per second  |
| 1000BASE-SX     | Gigabit Ethernet     | Fiber  | 1 gigabit per second    |

## Didn't stick / revisit


## Links to hands-on
