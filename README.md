# DNS Masq
> [!NOTE]\
> This is a mirror of the dnsmasq repository found [here.](https://thekelleys.org.uk/gitweb/?p=dnsmasq.git;a=summary)

> [!IMPORTANT]\
> No contributions will be accepted into this repository for this is just a mirror of the upstream repository.

> [!TIP]\
> Latest code is on the [`master`](https://github.com/repo-mirrorer/dnsmasq/tree/master) branch.

This repository is a mirror of the official `dnsmasq` repository for ease of access and development.

## Download

You can clone this repo through the official `dnsmasq` repository or this repository.
```bash
git clone git://thekelleys.org.uk/dnsmasq.git
```

### OR
```bash
git clone http://thekelleys.org.uk/git/dnsmasq.git
```

## About

### Overview
Dnsmasq provides network infrastructure for small networks: DNS, DHCP, router advertisement, and network boot. It is designed to be lightweight and have a small footprint, suitable for resource-constrained routers and firewalls. It has also been widely used for tethering on smartphones and portable hotspots, and to support virtual networking in virtualization frameworks.

### Supported Platforms
Supported platforms include Linux (with glibc and uclibc), Android, *BSD, and Mac OS X. Dnsmasq is included in most Linux distributions and the ports systems of FreeBSD, OpenBSD, and NetBSD. Dnsmasq provides full IPv6 support.

### DNS Subsystem
The DNS subsystem provides a local DNS server for the network, with forwarding of all query types to upstream recursive DNS servers and caching of common record types (A, AAAA, CNAME, and PTR, also DNSKEY and DS when DNSSEC is enabled).

Local DNS names can be defined by:
- Reading `/etc/hosts`
- Importing names from the DHCP subsystem
- Configuration of a wide range of useful record types

Upstream servers can be configured in a variety of convenient ways, including dynamic configuration as these change on moving upstream network.

### Authoritative DNS Mode
Authoritative DNS mode allows local DNS names to be exported to a zone in the global DNS. Dnsmasq acts as an authoritative server for this zone and also provides zone transfer to secondaries for the zone, if required.

### DNSSEC
DNSSEC validation may be performed on DNS replies from upstream nameservers, providing security against spoofing and cache poisoning.

### Sub-Domains
Specified sub-domains can be directed to their own upstream DNS servers, making VPN configuration easy. Internationalized domain names are supported.

### DHCP Subsystem
The DHCP subsystem supports DHCPv4, DHCPv6, BOOTP, and PXE. Both static and dynamic DHCP leases are supported, along with stateless mode in DHCPv6.

### PXE System
The PXE system is a full PXE server, supporting netboot menus and multiple architecture support. It includes proxy-mode, where the PXE system cooperates with another DHCP server. There is a built-in read-only TFTP server to support netboot.

### DHCP and DNS Integration
Machines configured by DHCP have their names automatically included in the DNS. The names can be specified by each machine or centrally by associating a name with a MAC address or UID in the dnsmasq configuration file.

### Router Advertisement Subsystem
The Router Advertisement subsystem provides basic autoconfiguration for IPv6 hosts. It can be used stand-alone or in conjunction with DHCPv6.

- The M and O bits are configurable, to control hosts' use of DHCPv6.
- Router advertisements can include the RDNSS option.
- There is a mode which uses name information from DHCPv4 configuration to provide DNS entries for autoconfigured IPv6 addresses which would otherwise be anonymous.

### Compactness
For extra compactness, unused features may be omitted at compile time.
