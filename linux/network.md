# Network Configuration

Primary configuration file for IPv4/IPv6 interfaces (RHEL/CentOS): `/etc/sysconfig/network-scripts/ifcfg-eth0`
*Note: The primary IPv6 configuration file is the same file where IPv4 configuration is stored.*

To configure a static IPv6 address:
```bash
BOOTPROTO=static
IPV6INIT=yes
IPV6ADDR=<IPv6 IP Address/subnet mask>
IPV6_DEFAULTGW=<IPv6 IP Gateway Address>
```

To enable DHCPv6 client mode:
```bash
DHCPV6C=yes
```

Enable IPv6 networking:
```bash
NETWORKING_IPV6=yes
```

Networking Configuration Files:
- /etc/hosts            -> Local hostname resolution 
- /etc/resolv.conf      -> DNS resolver configuration
- /etc/nsswitch.conf    -> Name service switch configuration

| **Command** | **Description** |
|---|---|
| `ip addr show` | Display configuration of network interfaces (modern replacement for `ifconfig`). |
| `ip addr add 192.168.1.1/24 dev eth0` | Configure a static IPv4 address on interface `eth0`. |
| `ip link set eth0 up` | Enable interface `eth0`. |
| `ip link set eth0 down` | Disable interface `eth0`. |
| `iw dev wlan0 link` | Display wireless interface configuration (modern replacement for `iwconfig`). |
| `dhclient eth0` | Enable interface in DHCP mode. |
| `ethtool eth0` | Display statistics and settings of NIC `eth0`. |
| `ip route show` | Display the routing table. |
| `ip route add default via 192.168.1.1` | Configure a default gateway. |
| `ip route add 192.168.0.0/16 via 192.168.1.1` | Configure a static route to network `192.168.0.0/16`. |
| `ping <IP>` | Test connectivity to another host. |
| `ss -tulnp` | Show listening sockets and processes (replacement for `netstat -tulnp`). |
| `ss -s` | Display socket statistics. |
| `dig example.com` | Query DNS information for a domain. |
| `dig @server example.com` | Query DNS information using a specific DNS server. |
| `dig -x <IP>` | Perform reverse DNS lookup. |
| `host www.example.com` | Resolve hostname to IP address. |
| `ssh user@hostname` or `ssh -l user hostname` | Connect to a remote system via SSH. |
| `iptables -t filter -L` | List rules in the filter table (legacy, replaced by `nftables`). |
| `iptables -t filter -F` | Flush all rules in the filter table. |
| `iptables -t filter -X` | Delete user-defined chains in the filter table. |
| `iptables -t nat -L` | List rules in the NAT table. |
| `iptables -t nat -F` | Flush all rules in the NAT table. |
| `tcpdump tcp port 80` | Capture HTTP traffic on port 80. |
| `wget file` | Download a file. |
| `wget -c file` | Resume a stopped download. |
| `whois domain` | Query WHOIS information for a domain. |
| `iwlist scan` | Scan for available wireless networks. |