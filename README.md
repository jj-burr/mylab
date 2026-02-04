# My Lab Projects
My Lab Projects &amp; Documents

### Home Network Projects and Upgrades
- Applied VLAN segmentation - Isolated IoT devices, work devices, guest devices and protected devices into separate VLANs
- Enable adblock DNS server and DNS resolver on a network level
- Setup regional blocking to protect against crawlers and bad actors
- Setup crowdsec service to log and auto-ban bad actors scan/pinging the home network
- Enable mesh VPN using Tailscale(peer-to-peer connection) to securely connect to home network remotely
- Applied MFA and SSO capabilities on hosted services

### Network Level AdBlocker and DNS Resolver via [Raspbery Pi 3b+]([url](https://docs.pi-hole.net/))
- Deployed RaspberryPi with Raspberry Pi OS Lite, Pi-Hole DNS Server and Unbound DNS Resolver installed
- Manages local DNS records to redirect domain names to local service host
- Rerouting all client devices within specified vlan to Adblocker as the DNS Server to filter traffic requests based on blocklist
- Retrieves ip addresses from root authorized DNS servers instead of upstream ISP or third party DNS providers(ensures third party providers from logging browsing history)

### Services (managed with Docker)
- Audio Book Server
- Library Server
- Game Rom Manager and Flash Web Player
- Tailscale Exit Node
- PocketId(Enables SSO)
- TinyAuth(forward auth service to enable SSO for non sso compatible services)
- Reverse Proxy Manager
- Photo Library
- NAS 
