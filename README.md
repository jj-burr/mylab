# My Lab Projects
My Lab Projects &amp; Documents

## High Level Home Network Projects
- Applied VLAN segmentation - Isolated IoT devices, work devices, guest devices and protected devices into separate VLANs
- Enable adblock DNS server and DNS resolver on a network level
- Setup regional blocking to protect against crawlers and bad actors
- Self Hosted Server(Services hosted: NAS, AudioBook, Library Server, Reverse proxy, Authentication Service, Tailscale)
- Setup crowdsec service to log and auto-ban bad actors scan/pinging the home network
- Enable mesh VPN using Tailscale(peer-to-peer connection) to securely connect to home network services remotely
- Implemented a reverse proxy to manage traffic access between clients and internal services(Allows for local & wan access management to specific server hosted services w/ ACL rules)
- Enabled SSO capabilities on hosted services, additional layer of security, registered device that passed ACL needs to have their user info registered within Authentication Service(PocketID)

## VLAN Setup
Regional IP blocking applied on all network at the firewall level
 1) Protected Network - Manual LAN Assignment, Wifi 5/6Ghz bands, Restricted network for trusted devices, adblock enabled, dns resolved applied
 2) Primary Network - Default LAN,Wifi 5/6 Ghz bands, isolated network, main wifi network, adblock enabled, dns resolved applied
 3) Work Network - LAN Only, applied /29 subnet to limit number of usable ip address, limit network speed, isolated network
 4) Guest Network - WiFi 2.4 Ghz only, limited network speeds, different password, isolated network, force traffic through VPN Service
 5) IoT Network - Limited network speeds, isolated network

### Network Level AdBlocker and DNS Resolver via [Raspbery Pi 3b+]([url](https://docs.pi-hole.net/))
- Deployed RaspberryPi with Raspberry Pi OS Lite, Pi-Hole DNS Server and Unbound DNS Resolver installed
- Manages local DNS records to redirect domain names to local service host
- Rerouting all client devices within specified vlan to Adblocker as the DNS Server to filter traffic requests based on blocklist
- Retrieves ip addresses from root authorized DNS servers instead of upstream ISP or third party DNS providers(ensures third party providers from logging browsing history)

### Services (managed with Docker)
- Audio Book Server(Web Service that uses web socket connection to enable media streaming and sync progress_
- Library Server(Web Service that supports reading epub, pdf, and cbz file formats)
- Game Rom Manager and Flash Web Player(Manages game roms by system, can play via web browser, supports remote multi player)
- Tailscale VPN(Remote connection between registered devices)
- PocketId(Enables SSO)
- TinyAuth(forward auth service to enable SSO for non sso compatible services)
- Reverse Proxy Manager
- Photo Library
- NAS 
