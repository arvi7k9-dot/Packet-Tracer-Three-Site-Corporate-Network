[Router-Config 1.txt](https://github.com/user-attachments/files/24435427/Router-Config.1.txt)[Router-Config 1.txt](https://github.com/user-attachments/files/24435414/Router-Config.1.txt)[Router-Config 1.txt](https://github.com/user-attachments/files/24435331/Router-Config.1.txt)[README.md](https://github.com/user-attachments/files/24433712/README.md)# Packet-Tracer-Three-Site-Corporate-Network
Multi-site Cisco Packet Tracer lab featuring static routing, DHCP-managed client networks, and statically addressed infrastructure servers

## Repository Structure

```

packet-tracer-multi-site-network/
│
├── topology/
│   └── [Three Site Corporate network - Zip.zip](https://github.com/user-attachments/files/24433795/Three.Site.Corporate.network.-.Zip.zip)


│
├── configs/
│   ├── [Uploading Router-Config 1

Current configuration : 835 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
no ip cef
no ipv6 cef
!
license udi pid CISCO2811/K9 sn FTX1017906D-
!
spanning-tree mode pvst
!
interface FastEthernet0/0
 ip address 192.168.4.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial0/2/0
 ip address 192.168.1.1 255.255.255.0
!
interface Vlan1
 no ip address
 shutdown
!
router rip
 network 192.168.1.0
 network 192.168.4.0
!
ip classless
ip route 192.168.5.0 255.255.255.0 192.168.1.2 
ip route 192.168.3.0 255.255.255.0 192.168.1.2 
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
enduter-Config 1.txt…]()


│   ├── [Router-Config 2.txt](https://github.com/user-attachments/files/24435383/Router-Config.2.txt)
Router-Config 2

Current configuration : 958 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
no ip cef
no ipv6 cef
!
license udi pid CISCO2811/K9 sn FTX101718JN-
!
spanning-tree mode pvst
!
interface FastEthernet0/0
 ip address 192.168.5.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial0/2/0
 ip address 192.168.1.2 255.255.255.0
 clock rate 2000000
!
interface Serial0/2/1
 ip address 192.168.2.1 255.255.255.0
 clock rate 2000000
!
interface Vlan1
 no ip address
 shutdown
!
router rip
 network 192.168.1.0
 network 192.168.2.0
 network 192.168.5.0
!
ip classless
ip route 192.168.3.0 255.255.255.0 192.168.2.2 
ip route 192.168.4.0 255.255.255.0 192.168.1.1 
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
end
│   ├── [Router-Config 3.txt](https://github.com/user-attachments/files/24435445/Router-Config.3.txt)
Router-Config 3

Current configuration : 835 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
!
!
!
!
!
!
!
no ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2811/K9 sn FTX10172V7B-
!
spanning-tree mode pvst
!
interface FastEthernet0/0
 ip address 192.168.3.1 255.255.255.0
 duplex auto
 speed auto
!
interface FastEthernet0/1
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial0/2/0
 ip address 192.168.2.2 255.255.255.0
!
interface Vlan1
 no ip address
 shutdown
!
router rip
 network 192.168.2.0
 network 192.168.3.0
!
ip classless
ip route 192.168.5.0 255.255.255.0 192.168.2.1 
ip route 192.168.4.0 255.255.255.0 192.168.2.1 
!
ip flow-export version 9
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
end

```

│
├── screenshots/
│   ├── <img width="1835" height="652" alt="Screenshot 2026-01-05 073849" src="https://github.com/user-attachments/assets/d652a2b5-81b1-49de-813e-5d5ae94471e7" />

│   ├── <img width="960" height="652" alt="Screenshot 2026-01-05 074103" src="https://github.com/user-attachments/assets/b5543102-7af3-4de0-845c-98641a5cac67" />

│   ├── <img width="956" height="627" alt="Screenshot 2026-01-05 074207" src="https://github.com/user-attachments/assets/bd38d7d3-b33a-4759-8c77-0cc2dd58ecf8" />

│   ├── <img width="981" height="765" alt="Screenshot 2026-01-05 074517" src="https://github.com/user-attachments/assets/bebbe6b5-f9b1-4980-bea3-592ad31c6fa2" />

|   ├── <img width="1046" height="797" alt="Screenshot 2026-01-05 074601" src="https://github.com/user-attachments/assets/c35b9429-b228-4fc0-8e58-a8900b0e448a" />

│   ├── <img width="909" height="601" alt="Screenshot 2026-01-05 073921" src="https://github.com/user-attachments/assets/e46d59e2-d31d-4e19-9d93-aa4ee2691a50" />

│
└── [Network Build and Configuration Process.txt](https://github.com/user-attachments/files/24436975/Network.Build.and.Configuration.Process.txt)
Network Build and Configuration Process

This section outlines the step-by-step process used to design, configure, and validate the three-site corporate network topology in Cisco Packet Tracer. The goal was to create a realistic multi-site environment with routed connectivity, DHCP-managed client networks, and centralized infrastructure services.

Topology Design and Device Placement

The lab began by placing three routers, one for each site, to represent the core routing devices responsible for inter-site connectivity. Each site was then provisioned with Cisco 3650 switches to act as the primary distribution switches (two at Site 1, and one each at Site 2 and Site 3).

To support end-user access, Cisco 2950T access switches were added at Site 1 and Site 3. These switches were used to connect PCs and laptops to the network, providing a layered access/distribution design similar to a real enterprise environment.

Server Deployment

Dedicated servers were deployed based on their functional role:

Site 1 and Site 3 each received a DHCP server to dynamically assign IP configurations to client devices.

Site 2 was designated as the infrastructure services site and hosted:

A DNS server

An HTTP server (used to simulate access to google.com)

All servers in Site 2 were configured with static IP addresses to ensure stability and predictable addressing for critical services.

Physical Connectivity

Appropriate cabling was used to reflect best practices:

Copper straight-through cables connected routers, servers, and end devices to the primary 3650 switches.

Copper crossover cables connected the 3650 distribution switches to the 2950T access switches.

Serial DCE links were used to interconnect the routers between sites, with Site 2 acting as the central hub connecting to both Site 1 and Site 3.

All devices and links were clearly labeled within Packet Tracer to document IP addressing and interface relationships.

Router Configuration and Routing

Each router was configured with the correct IP addresses on all interfaces and enabled using the no shutdown command. Interface status and addressing were verified using show ip interface brief.

Static routing was implemented on all three routers using the ip route command to ensure that each router was aware of the remote networks in the topology. Connectivity between routers was tested and verified before moving on to client and service configuration.

Service Configuration

The HTTP server at Site 2 was configured with static network settings, and its default web page was customized to represent google.com. The DNS server at Site 2 was also statically configured, with DNS services enabled and an A record created to resolve google.com to the internal HTTP server’s IP address.

DHCP services were configured independently at Site 1 and Site 3. Each DHCP pool was created with the appropriate network address, subnet mask, default gateway, and DNS server to ensure clients received complete and correct IP configurations.

Client Configuration and Validation

PCs and laptops at Site 1 and Site 3 were configured to obtain their IP settings automatically via DHCP. Each client device was labeled with its assigned IP address to simplify validation and troubleshooting.

End-to-end connectivity was tested using ICMP (ping) between routers, servers, and client devices across all three sites. Successful communication confirmed that routing and addressing were correctly configured.

Finally, web connectivity was validated by accessing google.com from client devices using the Packet Tracer web browser, confirming proper DNS resolution and HTTP service availability across routed networks.
