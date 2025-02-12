## Reset Router
- enable
- show ip rout
- write erase
- reload

### router 0/0
- enable
- configure terminal
- hostname home-router
    ```
    home-router could change depend what you want
    ```
- interface fastEthernet 0/0
- ip address 192.168.1.2 255.255.255.0
- ip nat outside
- exit

### router 0/1
- interface fastEthernet 0/1
- ip address 192.168.100.1 255.255.255.0
- ip nat inside
- no shutdown
- exit

### add some config
- ip route 0.0.0.0 0.0.0.0 192.168.1.1
- do show ip route
- exit

### check 
- ping 192.168.1.1
- show ip inter bri

### name-server
- conf t
- ip name-server 8.8.8.8 4.2.2.2
- exit

### check
- ping bbc.com
- ping facebook.com

## Reset Switch
- enable
- show ip inter bri
    ```
    check if there is ip address
    ```
- show vlan
- erase startup-config
- delete flash:vlan.dat
- reload

### 
- conf t
- hostname Home-Switch
- interface fastEthernet 0/48
- no switchport
- ip address 192.168.100.2 255.255.255.0
- no shutdown
- exit

### 
- ip route 0.0.0.0 0.0.0.0 192.168.100.1
- no shutdown
- exit

###
- do ping 192.168.100.1

###
- vlan 10
- name PC
- exit

- vlan 20
- name wifi
- exit

- vlan 30
- name printer
- exit

###
- exit

###
- show vlan

###
- conf t
- interface range fastEthernet 0/1-16
- switchport mode access
- switchport access vlan 10
- exit

###
- interface range fastEthernet 0/17-32
- switchport mode access
- switchport access vlan 20
- exit

###
- interface range fastEthernet 0/33-42
- switchport mode access
- switchport access vlan 30
- exit

###
- exit
- show vlan

###
- conf t
- interface vlan 10
- ip address 10.10.10.1 255.255.255.0
- no shutdown
- exit

###
- interface vlan 20
- ip address 10.10.20.1 255.255.255.0
- no shutdown
- exit

###
- interface vlan 30
- ip address 10.10.30.1 255.255.255.0
- no shutdown
- exit

### 
- exit
- show ip interface brief

###
- ip routing 
- ip sh
- ip dhcp pool
- ip dhcp pool 10
- network 10.10.10.0 255.255.255.0
- default-router 10.10.10.1
- dns-server 8.8.8.8 4.2.2.2
- exit

###
- ip dhcp pool
- ip dhcp pool 20
- network 10.10.20.0 255.255.255.0
- default-router 10.10.20.1
- dns-server 8.8.8.8 4.2.2.2
- exit

###
- ip dhcp pool
- ip dhcp pool 30
- network 10.10.30.0 255.255.255.0
- default-router 10.10.30.1
- dns-server 8.8.8.8 4.2.2.2
- exit

### exit from priviledge mode
- exit

###
- show run

### Router 
- enable
- conf t
- ip route 10.10.10.0 255.255.255.0 192.168.100.2
- ip route 10.10.20.0 255.255.255.0 192.168.100.2
- ip route 10.10.30.0 255.255.255.0 192.168.100.2
- exit
- show ip route
- conf t
- ip access-list standard 
- ip access-list standard 1
    ```
    1 is just a name, we could custom
    ```
- permit 192.168.100.0
- permit 192.168.100.0 0.0.0.255
- permit 10.10.10.0 0.0.0.255
- permit 10.20.10.0 0.0.0.255
- permit 10.30.10.0 0.0.0.255
- exit

###
- ip nat inside source list 1 interface fastEthernet 0/0 overload
- exit

### save config startup
- copy running-config startup-config

## Switch
- copy running-config startup-config









### for better documentation
- https://www.cisco.com/c/en/us/td/docs/routers/access/800M/software/800MSCG/routconf.html