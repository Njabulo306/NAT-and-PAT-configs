# NAT-and-PAT-configs
Dynamic NAT on router “LAN” , Static NAT on router “DATA” and  Test


1. Dynamic NAT
Access List
LAN(config)#ip access-list stan 1
LAN(config-std-nacl)#permit 192.168.0.0 0.0.0.255
NAT command
LAN(config)#ip nat inside source list 1 interface FastEthernet 0/0 overload
Interfaces
LAN(config)#interface FastEthernet 0/0
LAN(config-if)#ip nat outside
LAN(config)#interface FastEthernet 0/1
LAN(config-if)#ip nat inside

3. Static NAT
Static NAT mappings
DAT(config)#ip nat inside source static 192.168.100.1 15.0.0.11
DAT(config)#ip nat inside source static 192.168.100.12 15.0.0.12
DAT(config)#ip nat inside source static 192.168.100.13 15.0.0.13
DAT(config)#ip nat inside source static 192.168.100.14 15.0.0.14
Interfaces
DAT(config)#interface FastEthernet 0/0
DAT(config-if)#ip nat outside
DAT(config)#interface FastEthernet 0/1
DAT(config-if)#ip nat inside
