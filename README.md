# Netwerkdocumentatie

## basis configuratie switch
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
ip defaultgateway 192.168.1.1
ip domain-name cisco.com
crypto key generate rsa
modulus 1024
username admin
secret pxl
line vty 0 15
login local
transport input ssh
end
