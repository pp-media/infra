# VLANs

* 100: WAN (Polar nett)
* 101: PP Media host
* 102: KANDU video rigs

# Ports

## ER-X

* eth0: WAN setup link (no VLAN)
* eth1: Bootstrapper (untag VLAN 101)
* eth2: PP hosts (untag VLAN 101, tag everything else)
* eth4: KANDU video rig (untag VLAN 102)
* eth5: WAN permanent link (VLAN 100)

# Routing

## ER-X

* eth0: No VLAN
  - Mode: DHCP
  - Route for 0.0.0.0/0

* VLAN 100
  - Mode: Static
  - Address: 256.256.256.130/27
  - GW: 256.256.256.129
  - Route for 0.0.0.0/0

* VLAN 101
  - Mode: Static
  - Address: 192.168.111.1/24

* VLAN 102
  - Mode: Static
  - Address: 192.168.10.1/24
  

# IP ranges

* 192.168.10.0/24: KANDU video rigs
* 192.168.111.0/24: PP Media host network
* 256.256.256.128/27: Media WAN (PLACEHOLDER)

# Media internal: 192.168.111.0/24

* 192.168.111.1: Ubiquity ER-X router
* 192.168.111.2: Bootstrapper
* 192.168.111.3: uis-01
* 192.168.111.4: uis-02
* 192.168.111.5: uis-03
* 192.168.111.6: uis-04
* 192.168.111.7: uis-05
* 192.168.111.8: uis-06
* 192.168.111.9: uis-07
* 192.168.111.150-200: DHCP (on ER-X)

# Media host WAN 256.256.256.128/27

* 256.256.256.130: Ubiquity ER-X (eth0)
* 256.256.256.131: uis-01
* 256.256.256.132: uis-02
* 256.256.256.133: uis-03
* 256.256.256.134: uis-04
* 256.256.256.135: uis-05
* 256.256.256.136: uis-06
* 256.256.256.137: uis-07

# Tailnet 100.111.0.0-100

* 100.111.0.1 Bootstrapper
* 100.111.0.2 uis-01
* 100.111.0.3 uis-02
* 100.111.0.4 uis-03
* 100.111.0.6 uis-04
* 100.111.0.7 uis-05
* 100.111.0.8 uis-06
* 100.111.0.9 uis-07

# KANDU video rigs: 192.168.10.0/24

* 192.168.10.1: ER-X (VLAN 102)

## Misc .2-15

* 192.168.10.2: ATEM 1 M/E Broadcast Panel
* 192.168.10.3: X32 Flight
* 192.168.10.4: X32 Briefcase
...
* 192.168.10.10: GreenGo
* 192.168.10.11: VideoHub 16x16

## Rig A .16-31

* 192.168.10.16: Atem 2 M/E Production Studio 4K
* 192.168.10.17: Smart Videohub 40x40
* 192.168.10.18: Smartscope Duo 
* 192.168.10.19: Smartscope Duo
* 192.168.10.20: SmartView Duo
* 192.168.10.21: SmartView Duo
* 192.168.10.22: SmartView HD
* 192.168.10.23: SmartView HD
* 192.168.10.24: SmartView HD
* 192.168.10.25: SmartView HD
* 192.168.10.26: Hyperdeck Studio
* 192.168.10.27: Teranex 2D Processor
* 192.168.10.28: Teranex 2D Processor
* 192.168.10.29: Server: GFX (prod-nett)
* 192.168.10.30: Server: VB (prod-nett)

## Cameras .128-160

* 192.168.10.128: AW-RP120
* 192.168.10.129: HE-130 (Cam 1)
* 192.168.10.130: HE-130 (Cam 1)
* 192.168.10.131: HE-130 (Cam 3)
* 192.168.10.132: HE-130 (Cam 4)
* 192.168.10.133: HE-130 (Cam 5)
* 192.168.10.134: HE-130 (Cam 6)
* 192.168.10.135: HE-130 (Cam 7)

