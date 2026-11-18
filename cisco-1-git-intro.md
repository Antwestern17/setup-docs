# My First Git Lab

This is my first document stored in Git

## Things I Learned

- Git tracks changes to files.
- GitHub stores my repository online.
- **SSH Keys** keep my account secure.
- up arrow reveals past commands
- enable moves you into priv. exec. mode

## Binary to Hexadecimal Cheat Sheet

| Decimal | Binary | Hexadecimal |
|:-------:|:------:|:-----------:|
| 0 | 0000 | 0 |
| 1 | 0001 | 1 |
| 2 | 0010 | 2 |
| 3 | 0011 | 3 |
| 4 | 0100 | 4 |
| 5 | 0101 | 5 |
| 6 | 0110 | 6 |
| 7 | 0111 | 7 |
| 8 | 1000 | 8 |
| 9 | 1001 | 9 |
| 10 | 1010 | A |
| 11 | 1011 | B |
| 12 | 1100 | C |
| 13 | 1101 | D |
| 14 | 1110 | E |
| 15 | 1111 | F |

### 8-Bit Binary Place-Value Table

| Bit position | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|:------------:|---|---|---|---|---|---|---|---|
| Place value  | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

### Binary-to-Decimal Conversion Example

For `11010110`, add the place values where the bit is `1`:

`128 + 64 + 16 + 4 + 2 = 214`

### Conversion Example

Convert binary `11010110` to hexadecimal by grouping the bits into fours:

`1101 0110` → `D 6` → **`D6`**

### IPv4 Address Conversion Example

Convert each decimal octet separately, keeping each binary octet at 8 bits:

| Decimal octet | Binary | Hexadecimal |
|:-------------:|:------:|:-----------:|
| 192 | 11000000 | C0 |
| 168 | 10101000 | A8 |
| 1 | 00000001 | 01 |
| 10 | 00001010 | 0A |

`192.168.1.10` → `11000000.10101000.00000001.00001010` → `C0.A8.01.0A`

# Notes

# Cisco Switch Basic Configuration Guide

A step-by-step reference for configuring basic security, management IP addressing, and saving settings on a Cisco IOS switch from start to finish.

---

### 1. Enter Configuration Mode & Name the Switch
* `enable` — Enters Privileged EXEC mode (`Switch#`).
* `configure terminal` — Enters Global Configuration mode (`Switch(config)#`).
* `hostname S1` — Sets the switch's name to `S1` (`S1(config)#`).
* `no ip domain-lookup` — Prevents the switch from trying to translate mistyped commands as domain names.

### 2. Secure Console Access (Physical Cable Login)
* `line console 0` — Enters Console Line configuration mode (`S1(config-line)#`).
* `password cisco` — Sets the console login password.
* `login` — Requires the password when connecting via the console port.
* `exit` — Returns to Global Configuration mode (`S1(config)#`).

### 3. Secure Remote Access (Telnet / VTY Lines)
* `line vty 0 15` — Selects all 16 virtual terminal lines for remote access (`S1(config-line)#`).
* `password examplepassword` — Sets the password for remote logins.
* `login` — Requires the password for VTY connections.
* `exit` — Returns to Global Configuration mode (`S1(config)#`).

### 4. Set Privileged Password, Encryption & Login Banner
* `enable secret class` — Sets an encrypted password (`class`) to enter Privileged EXEC mode.
* `service password-encryption` — Encrypts all plain-text passwords in the configuration file.
* `banner motd #Authorized Access Only#` — Sets a Message of the Day login banner.

### 5. Configure Management IP Address (SVI)
* `interface vlan 1` — Enters the virtual management interface (`S1(config-if)#`).
* `ip address 192.168.1.253 255.255.255.0` — Assigns the switch a management IP address and subnet mask.
* `no shutdown` — Enables the virtual interface.
* `end` — Exits directly back to Privileged EXEC mode (`S1#`).

### 6. Save & Verify (Run from `S1#`)
* `copy running-config startup-config` — Saves the active configuration to NVRAM so settings persist after a reboot.
* `show running-config` — Displays the active configuration to verify all settings.
* `show startup-config` - displays saved configuration file

## Routing
### Ipv4 Settings
- IP address - addressof the physical computer itself
- Subnet mask - tell our computers what part is the network, what part is the host
- Default Gateway - without a default gateway, if we have a network address not on our local network, it doesnt know where to send it. will not work
### Loopback Address
- IPv4 - 127.0.0.1
- IPv6 - ::1
- Best way to start trouble shooting. Start close and work away.
### Configure router interface
- Router (config)# interface type-and-number
- router(config)# description
- router(config)#ip address ipv4 address subnet mask
- router(config)#ipv6 address ipv6 address/prefix lenght
- router(config)# no shutdown
![My Screenshot](Images/Screenshot%202026-11-17%20180713.png)
### Verify interface configuration.
#### commands
- show ip interface brief
- show ipv6 interface brief. The output displays all interfaces, their ip addresses, and their current status.  The configured and connected interfaces should display a status of "up" and a protocol of "up."  Anything else would indicate a problem with the configuration or cabling

- Show ip route
- Show ipv6 route.  Displays the contents of the IP routing tables stored in RAM.
- Show interfaces "serial 0/0/0" for specific interfaces.
- Show interfaces. Displays statistics for all interfaces on the device.  However, this command will only display the ipv4 addressing information.
- show ip interface. Displays the ipv4 statistics for all interfaces on a router.
- show ipv6 interface. Displays the ipv6 statistics for all interfaces on a router.
### configuring default gateway for layer 2 switch
- enter configuration mode, configure terminal
- S1(config)# ip default-gateway "192.168.10.1"









![My screenshot](Images/Ciscoimage1.png)

