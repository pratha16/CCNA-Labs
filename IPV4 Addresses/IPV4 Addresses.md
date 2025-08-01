IPV4 Addresses Lab

This lab demonstrates the process of configuring a Cisco router’s hostnames, interfaces, and IP addresses, as well as setting up end devices to test basic network connectivity.


<img width="718" height="317" alt="image" src="https://github.com/user-attachments/assets/1e002ada-6822-479a-af5a-a21c9a1c5cff" />

1. Configure R1's hostname.
   On router CLI:
   ```
   enable
   configure terminal
   hostname R1
   ```

   
3. Use a 'show' command to view a list of R1's interfaces, their IP addresses, status, etc.
   ```
   show ip interface brief
   ```
   This command summarizes all interfaces, their IP addresses, and whether they are up/down.


5. Configure the appropriate IP addresses on R1's interfaces, and enable the interfaces. Configure appropriate interface descriptions.
   ```
   interface g0/0
   description Link to SW1
   ip address 15.255.255.254 255.0.0.0
   no shutdown

   interface g0/1
   description Link to SW2
   ip address 182.98.255.254 255.255.0.0
   no shutdown
 
   interface g0/2
   description Link to SW3
   ip address 201.191.20.254 255.255.255.0
   no shutdown
   exit

   end
   ```


7. Use a 'show' command to verify R1's interfaces again.
   ```
   show ip interface brief
   show interfaces
   ```
   Using the first command for summaries, others for details and descriptions.


9. View the running config to confirm the configuration changes, then save the config.
    ```
    show running-config
    write
    ```    


11. Configure the IP addresses of PC1, PC2, and PC3.
    - Click on each PC.
    - Go to Config, and then to FastEthernet0.
    - Then enter the assigned IP address and subnet mask of the PC.
   
      PC1:
         ```
         IP: 15.0.0.1
      
         Subnet mask: 255.0.0.0
         ```
      PC2:
         ```
         IP: 182.98.0.1
      
         Subnet mask: 255.255.0.0
         ```
      PC3:
         ```
         IP: 201.191.20.0
      
         Subnet mask: 255.255.255.0
         ```

13. Ping from PC1 to PC2 and PC3 to test connectivity.
    
