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

## Basic configuration for a switch
- enter <b>enable</b> to enter privilege exec. mode
- Enter conf t to enter global configuration mode
- enter: hostname ex:S1 (make sure your commands and switches match the source text letter-for-letter.)

## Configure the console and encrypted privileged EXEC mode passwords
### Console
- in global configuration mode enter # line console 0
- then enter # password ex:cisco
- then enter # login
### privilege exec mode passwords
- enter # enable secret ex:class
-encrypt all passwords with # service password-encryption
### setting up a banner
- banner motd "example banner"
### Save configuration file to NYRAM.
- copy run start
### Configure the switch management interface.
- (in configuration mode) enter # interface vlan1
- enter ip address ex: 192.168.1.253 255.255.255.0
- No shutdown
- password for VTY 0.  enter # line vty 0 15. ex:ASw-2(config-line)#password example password.
### domain name problem
- no ip domain-lookup
## Start up
### tera term
- serial, com4
- control panel
- ethernet properties
- ipv4
- computer
### running config
- enter show run priv. exec mode

- Console cable out of band
- telnet in band
### Computer terminal
- computer terminal ipconfig /all to view mac address of  your nic.
### tera terminal
- ex: S1: show interfaces vlan 1 to view mac address on your switch, also show arp.

- Mac address for vlan 1 and mac serial number for vlan 1 are the same

### end lab
-switch#erase startup-config
- switch#reload












![My screenshot](Images/Ciscoimage1.png)

