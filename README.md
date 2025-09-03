# cisco

# console cisco memakai kabel console utp to serial atau utp to usb serial
# colok kabel console yang utp ke port rj45 belakang cisco yang ada label console
# colok kabel serial atau usb serial ke port usb laptop
dmesg | grep ttyUSB
# misal dari hasil dmesg didapatkan ttyUSB0
screen /dev/ttyUSB0

# rubah ip cisco
conf t
interface vlan 10
no ip address
end
conf t
interface vlan 1
ip address 10.11.8.3 255.255.255.0
end
conf t
ip default gateway 10.11.8.1
show ip interface
copy running-config startup-config
reload
