# Basic Cisco Device Security and Hostname Configuration

This README walks through essential router and switch configuration tasks on Cisco equipment (as shown in the topology).
Each step includes both the **task** and the **required command(s)**.

<img width="424" height="287" alt="image" src="https://github.com/user-attachments/assets/357ce921-469c-41b8-aedb-6318d1f801a4" />

---
1. Change the hostnames of the router and switch to the appropriate names (R1, SW1)
   ON ROUTER
   ```
   Router> enable
   Router# configure terminal
   Router(config)# hostname R1
   ```
   ON SWITCH
   ```
   Switch> enable
   Switch# configure terminal
   Switch(config)# hostname SW1
   ```
2. Configure an unencrypted enable password of 'CCNA' on both devices
   On R1 and SW1
   ```
   enable password CCNA
   ```
3. Exit back to user EXEC mode and test the password
   ```
   end
   exit
   ```
   At the prompt:
   ```
   Switch> enable
   Password: CCNA
   ```
   
4. View the password in the running configuration
   ```
   show running-config
   ```

5. Ensure that the current password, and all future passwords, are encrypted
   ```
   service password-encryption
   ```
   
6. View the password in the running configuration
   ```
   show running-config
   ```

7. Configure a more secure, encrypted enable password of 'Cisco' on both devices
    ```
    enable secret Cisco
    ```

8. Exit back to user EXEC mode and then return to privileged EXEC mode.
   Which password do you have to use?
   ```
   end
   exit
   enable
   ```
   > **Answer:** Use the password `Cisco` (enable secret overrides enable password).

9. View the passwords in the running configuration.
   What encryption type number is used for the encrypted 'enable password'?
   What encryption type number is used for the encrypted 'enable secret'?
   ```
   show running-config
   ```
   ```
   > - `enable password`: type **7** encryption.
   > - `enable secret`: type **5** encryption.
   ```

10. Save the running configuration to the startup configuration
    ```
    copy running-config startup-config
    ```
    
