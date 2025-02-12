### notes, command for cisco

- LAYER 1, Physical Layer
    - just some cable stuff
    - hub
    - repeaters

- LAYER 2: Data Link, Ethernet Header
    - Switch
        enable
    - Mac Address, example: 0009.7ce3.3271
    - example cli in switch      
        ```
        enable
        show mac-address-table
        ```    
    - ARP Packet
    - Frame

- LAYER 3: Network, IP Header
    - Router
    - IP Address, 
        - ping 10.1.1.0 - 10.1.1.225
    ```
    enable
    show ip route
    ```
    - Packet
    - Advance Switch: Layer 3 Switch

- LAYER 4: TCP
    - https == port 443
    - http == port 80
    - Segment

- LAYER 6: Presentation , SSL
    - Convert data

- LAYER 7: Application



## Network Design

- don't use single point failure
- recomendation: 
    - 2 tier architecture network design, use advance switch(L3 Switch)
    - 3 tier architecture network design

- Campus Network Design
    - Access Layer, Tier 1
    - Distribution Layer, Tier 2
    - Core Layer, Tier 3
        - example, Cisco Catalyst 9600 Series

Data Center Design
    - Spine-Leaf Design


### Additional
- range 127.0.0.1 ~ 255 == loop back address, for network testing