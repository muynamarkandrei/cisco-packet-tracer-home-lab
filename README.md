#cisco-packet-tracer-home-lab# 

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
