# CIDR
- Classless Inter-Domain Routing : Method for allocating IP
- Used Security Group
- Contains:
1. Base IP:
- Represents an IP
- Eg: 10.0.0.0, 192.168.0.0,...

2. Subnet Mask:
- How many bits can change in IP
- Eg: /0, /24, /32
- Can take two forms:
  - /8 -> 255.0.0.0
  - /16 -> 255.255.0.0
  - /24 -> 255.255.255.0
  - /32 -> 255.255.255.255

![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/fdf5e0a7-bc7b-43d6-97e6-1224379666fd)

## Note:
![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/d8327436-c6ea-429d-8fbc-e36663184bf5)


# Private IP can only allow certain values:
- 10.0.0.0 –> 10.255.255.255 (10.0.0.0/8) : used in big networks
- 172.16.0.0 –> 172.31.255.255 (172.16.0.0/12) : AWS default VPC in that range
- 192.168.0.0 –> 192.168.255.255 (192.168.0.0/16) : e.g., home networks
- All the rest of IP are public

  
