Network Simulation: Switch MAC Address Learning and Ping Process

This guide walks through a classic Packet Tracer lab involving a simple switch network with four PCs and two switches. Steps demonstrate ARP and MAC learning using 'ping' and relevant show/clear commands.

![image](https://github.com/user-attachments/assets/f91764cf-d264-4791-8f99-b7d59d868705)

Both switches have an empty MAC address table, and all PCs have an empty ARP table.

1. If PC1 pings to PC3, what messages will be sent over the network, and which devices will receive them?

Message Sequence:

    PC1 sends an ARP request:

        Who has 192.168.1.3 (PC3)?

        This is a Layer 2 broadcast (FFFF:FFFF:FFFF).

        All devices on the LAN (PC2, SW1, SW2, PC3, PC4) will receive the ARP request.

    PC3 replies with an ARP reply (unicast):

        Sent only to PC1's MAC address.

    PC1 sends ICMP Echo Request ("ping") to PC3:

        Now knows PC3's MAC, so the packet is unicast.

    PC3 sends ICMP Echo Reply to PC1:

        Also unicast, delivered back across switches.

  
3. Send the ping and use Packet Tracer's 'simulation mode' to verify your answer.

4. Use pings to generate network traffic and allow the switches to learn the MAC addresses 
   of all PCs on the network.

5. Use 'show' commands on the switches to identify the MAC address of each PC.

6. Clear the dynamic MAC addresses from the MAC address table of each switch.
