# Netwerkdocumentatie

## Basis configuratie switch
enable
configure terminal
line console 0
password pxl
login
enable secret pxl
interface vlan 1
ip address 192.168.1.2 255.255.255.0
ipv6 address 2001:db8:1::2/64
no shutdown
ip default-gateway 192.168.1.1
ip domain-name cisco.com
crypto key generate rsa
modulus 1024
username admin
secret pxl
line vty 0 15
login local
transport input ssh
end

## Basis configuratie router
enable
configure terminal
line console 0
password pxl
login
enable secret pxl
interface GigabitEthernet0/0/0
ip address 192.168.1.1 255.255.255.0
ipv6 address 2001:db8:1::1/64
no shutdown
interface GigabitEthernet0/0/1
ip address 192.168.2.1 255.255.255.0
ipv6 address 2001:db8:2::1/64
no shutdown
hostname S1
ip domain-name cisco.com
crypto key generate rsa
modulus 1024
username admin secret pxl
line vty 0 15
login local
transport input ssh
end

