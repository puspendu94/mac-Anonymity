# mac Anonymity
 *Network Hack - Pre Condition*
##### Markdown Writing guide: [link to guide](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)
---
## ***What***:
* MAC : Media Access Control
* Permanent ,Physical, Unique
---
## ***Why***:
* Increase anonymity
* Impaesonate other devices.
* Bypass filters.
---
## ***How***:
>~# apt-get install terminator
>~# ifconfig
* Network Interface
* Example: eth0; as a wifi card / ethernet card
* **ether** holds MAC
> ~# ifconfig wlan0 down
* ifconfig interface-name disable-option
>~# ifconfig wlan0 hw ether 00:11:22:33:44:55
* ifconfig interface-name hardware-option  new-address
> ~# ifconfig wlan0 up
* ifconfig interface-name enable-option
---
*** N.B. These changes will revert back to original once we restart the computer. Because we only changed the mac address in memory. We can't change the physical MAC address.
# If the network manager refresing our MAC address:
> ~# leafpad /etc/NetworkManager/NetworkManager.conf
* Use any text editor to open and edit the Network Manager config file
> ADD the following lines to the above mentioned file
>>[device]\
wifi.scan-rand-mac-address=no\
[connection]\
ethernet-mac-address=preserve\
wifi.cloned-mac-address=preserve
* Now restart the network manager in terinal
> ~# service network-manager restart
---