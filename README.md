# iproute2mac

CLI wrapper for basic network utilities on Mac OS X inspired with iproute2 on Linux systems - `ip` command.

Provided functionality is limited and command output is not fully compatible with [iproute2](http://www.policyrouting.org/iproute2.doc.html).

Goal of this project is to make basic network configuration/debug tasks on Mac OS X easy for admins who already use Linux systems.

For advanced usage use `netstat`, `ifconfig`, `ndp`, `arp`, `route` and `networksetup` directly.

## Installation

A) Using [Homebrew](http://brew.sh):

```bash
# [Optional] Install Homebrew first - see http://brew.sh for more options
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
# Install iproute2mac
brew install iproute2mac
```

B) Manual installation:

```bash
curl --remote-name -L https://github.com/SpinlockLabs/iproute2mac/raw/master/src/ip.py
chmod +x ip.py
mv ip.py /usr/local/bin/ip
```

## Supported Commands / Example Usage

Goal of this utility is to provide compatible CLI with [iproute2](http://www.policyrouting.org/iproute2.doc.html), supporting same command shortcuts and user experience.

* Help
  * `ip help`
  * `ip link help`
  * `ip addr help`
  * `ip route help`
  * `ip neigh help`
* Link module (Interfaces)
  * List local interfaces `ip link`
  * Show one interface `ip link show en0`
  * Shutdown interface `ip link set dev en0 down`
  * Start interface `ip link set dev en0 up`
  * Set custom MAC address `ip link set dev en0 address 00:12:34:45:78:90`
  * Set **Random MAC** address `ip link set en0 address random`
  * Set **Factory default MAC** address `ip link set en0 address factory`
  * Set MTU `ip link set dev en0 mtu 9000`
* Neighbour module (ARP/NDP)
  * Show all neighbours `ip neigh`
  * Show all IPv4 (ARP) neighbours `ip -4 neigh`
  * Show all IPv6 (NDP) neighbours `ip -6 neigh`
  * Show all IPv4 (ARP) neighbours for a specific interface `ip -4 neigh show dev en0`
  * IPv6 (NDP) neighbours cannot be currently shown for a specific interface
  * Flush all neighbours (IPv4 + IPv6) for a specific interface `ip neigh flush dev en0`
  * Flush all IPv4 (ARP) neighbours for a specific interface `ip -4 neigh flush dev en0`
  * IPv6 (NDP) neighbours are currently flushed for all interfaces
* Address module
  * List all addresses `ip addr`
  * List IPv4 addresses `ip -4 addr`
  * List IPv6 addresses `ip -6 addr`
  * Add address to interface `ip addr add 10.0.0.5/24 dev en0`
  * Remove address to interface `ip addr del 10.0.0.5 dev en0`
* Route module
  * List IPv4 addresses `ip route`
  * List IPv6 addresses `ip -6 route`
  * Get route for destination `ip route get 8.8.8.8`
  * Add static route `ip route add 192.168.0.0/16 nexthop 10.0.0.1`
  * Add default route `ip route add default nexthop 10.0.0.1`
  * Remove static route `ip route del 192.168.0.0/16`

## Authors

See AUTHORS.

Used software/code:

* [macgen.py](http://www.linux-kvm.com/sites/default/files/macgen.py) - Function for generating random MAC address
* [SpoofMAC](https://github.com/feross/SpoofMAC) - Code for obtaining factory default MAC address for interface

## License

The MIT License (MIT)
