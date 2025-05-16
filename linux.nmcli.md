```
nmcli con modify "Wired connection 2" ipv4.addresses 10.59.132.211/24
nmcli con modify "Wired connection 2" ipv4.gateway 10.59.132.1
nmcli con modify "Wired connection 2" ipv4.dns "8.8.8.8 8.8.4.4"
nmcli con modify "Wired connection 2" ipv4.method manual
nmcli con modify "Wired connection 2" connection.autoconnect yes
nmcli con up "Wired connection 2"
```
```
# cat /etc/NetworkManager/system-connections/'Wired connection 2.nmconnection'
[connection]
id=Wired connection 2
uuid=19d0c626-5a83-3e1e-bf2a-c55c5573150f
type=ethernet
autoconnect-priority=-999
interface-name=enp65s0f1

[ethernet]

[ipv4]
address1=10.59.132.211/24,10.59.132.1
dns=8.8.8.8;8.8.4.4;
method=manual

[ipv6]
addr-gen-mode=stable-privacy
method=auto

[proxy]
```
