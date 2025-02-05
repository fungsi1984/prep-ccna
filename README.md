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

- LAYER 3: Network, IP Header
    - Router
    - IP Address, 
        - ping 10.1.1.0 - 10.1.1.225
    ```
    enable
    show ip route
    ```

- LAYER 4: TCP
    - https == port 443
    - http == port 80