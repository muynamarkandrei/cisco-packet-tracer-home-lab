Cisco Packet Tracer Home LAN

A beginner networking lab created in Cisco Packet Tracer to understand how a basic home/local area network works.

## 🖥️ Network Topology

```text
                    Router
                 192.168.1.1
                       │
                       │
                    Switch
               ┌───────┼───────┐
               │       │       │
              PC     Laptop  Printer
             DHCP     DHCP   Static IP
```

## 🔧 Devices Used

* Cisco 2911 Router
* Cisco 2960 Switch
* PC
* Laptop
* Printer-PT
* Copper Ethernet cables

## ⚙️ Configuration

### Router

Configured the router's `GigabitEthernet0/1` interface:

```text
IP Address:   192.168.1.1
Subnet Mask:  255.255.255.0
```

The router was also configured as a DHCP server for the LAN:

```text
Network:       192.168.1.0/24
Default Gateway: 192.168.1.1
```

### End Devices

The PC and laptop were configured to obtain their IP addresses through DHCP.

The printer was configured with a static IP address so it could have a predictable address on the network.

## 🧪 Testing

### Router Connectivity

Tested connectivity from the PC to the router using ICMP:

```text
ping 192.168.1.1
```

The PC successfully received replies from the router.

### Printer Connectivity

Tested connectivity from the PC to the printer using its static IP address:

```text
ping 192.168.1.10 (static)
```

The printer successfully responded, confirming that the PC and printer could communicate through the switch.

### CDP Neighbor Discovery

Used:

```text
show cdp neighbors
```

## 📚 What I Learned

This lab helped me understand the difference between a router and a switch, how devices obtain IP addresses through DHCP, and how devices on the same LAN communicate through a switch.

I also practiced basic Cisco IOS commands such as `show ip interface brief`, `show cdp neighbors`, `show ip dhcp binding`, and `ping`.

Most importantly, I learned how to troubleshoot connectivity by checking the physical connection, interface status, IP configuration, and network reachability step by step.

Lab 02: Wireless LAN with Access Point
Overview

Built a small wireless LAN in Cisco Packet Tracer to understand how wired and wireless devices communicate through an Access Point, switch, and router.

The lab demonstrates how a laptop can connect to the same LAN as a wired PC through Wi-Fi while receiving its network configuration from the router's DHCP service.

Network Topology
                    Router
                 192.168.1.1
                       │
                    Switch
                   /      \
                 PC        Access Point
               Ethernet       )))
                              Wi-Fi
                               )))
                             Laptop
                            WPC300N
Devices Used
Cisco Router
Cisco Switch
Access Point
PC
Laptop
WPC300N wireless module
Configuration
Router

Configured the router's LAN interface:

GigabitEthernet0/1
IP Address: 192.168.1.1
Subnet Mask: 255.255.255.0

Configured DHCP for the LAN:

DHCP Pool: HOME-WIFI
Network: 192.168.1.0/24
Default Gateway: 192.168.1.1
Access Point

Configured the wireless network and connected the Access Point to the switch through Ethernet.

Laptop

Installed the WPC300N wireless module and connected the laptop to the Access Point through Wi-Fi.

The laptop was configured to obtain its IP address automatically through DHCP.

PC

Connected the PC to the switch through Ethernet and configured it to obtain its IP address through DHCP.

Testing

Connectivity was tested between the devices and the router.

The PC successfully obtained an IP address through Ethernet, while the laptop successfully connected through Wi-Fi and obtained its network configuration through DHCP.

What I Learned
An Access Point provides wireless connectivity to devices with a wireless network adapter.
A switch connects wired devices and Access Points within the LAN.
A router interface can serve as the default gateway for devices on the LAN.
DHCP automatically provides IP addresses and network configuration to clients.
Wired and wireless devices can communicate on the same LAN.
A device such as the WPC300N provides wireless connectivity to a laptop that does not have a built-in wireless interface.
Skills Practiced

Cisco Packet Tracer IPv4 DHCP LAN Wi-Fi Access Points Ethernet Basic Router Configuration Network Troubleshooting
