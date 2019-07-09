# Wi-Fi Ethical Hacking (Kali Linux)
*This document is intended for educational purposes only!
It is a criminal offense to crack into someone's WIFI unlawfully
or withouth **written** consent.*

## Basic Linux Commands
- `ls /directory`: Shows list of items in a directory
- `ls -la`: Shows hidden files in a directory 
- `-v`: Gives verbose output to know exactly what's happening in a command
  - i.e. `cp -v filename /var/`
- `clear` or `ctrl + l`: Clear Window
- `cat filename`: Shows file in terminal window
- `less filename`: Shows file in new window, hit "q" to exit
- `touch filename`: Used to quickly create files
- `chown`: Change ownership of a file
- `man -help`: Display manual page for a tool
  - i.e. `man rm`
  
 ## Cracking into WIFI Steps
 1. Setup Proxy 
 2. Spoof MAC Address(Macchanger)
 3. Create Password Wordlist (Crunch)
 4. Crack into Wifi (AirCrack)
 
 
 ## 1. Proxy Chains
 ### Why are they used?
 - Used when want to anonymize oneself on the network
 - Basically uses a series of servers to bounce IP around in order to keeps one's IP unkown
 - Means proxy server connection can be slower
 
 ### How to Access/Setup proxy
 1. Navigate to `nano /etc/proxychain.conf`
    #### Notable Elements
    - **Socks5 Proxy**: Best proxy to use as can anonymize all types of traffic
    - **Socks4 Proxy**: Similar to Socks5 but can't anonymyze UDP and other forms of traffic
    - **Dynamic**: Proxy setting most commonly used as most stable
 2. Uncomment `Dyanmic` and leave the other options commented   
 3. Add a Proxy
    - At EOF add desired proxy with port number
    - `Socks5 127.0.0.1 9050`
      
## 2. Spoof MAC Address
Get your IP: `ifconfig` or `macchanger -s eth0`
  1. Spoof yourself by changing MAC address
      - `maachanger -r eth0`: Assigns random MAC address to device
      - If want to blend in more to network, can pick MAC address with similar beginning numbers. Simply run a `maachanger -help` command to explore options available in tool
  2. Configure Linux to change MAC address on boot
      - Run `crontab -e`
      - Enter `@ reboot macchanger -r eth0`
      - Exit
## 3. Crunch - Password Wordlist Generator
- Crunch generates wordlist based on parameters set on it
- `crunch 3 5 1234567`: Generates 3 - 5 character string using numbers 1-7
- `crunch | aircrack`: Pipe this wordlist into aircrack for it to use

## 4. Aircrack-ng  - Crack into WiFi
- Need to know something about password in order to expedite WiFi cracking process
- If know nothing about password, better off exploiting router vulnerabilty
### Change NIC into Monitor Mode
- Put the Network Interface Card into monitor mode to scann the network
- In steps, used wl01 for NIC name; should substitute with actual name you want to use
1. `ifconfig wl01 down`
2. `ifconfig wl01 mode monitor`
3. `ifconfig wl01 up`
4. ifconfig ==> check to see if NIC running
### Check for Background Services
- Need to kill background services as may hamper with host scanning\
- Should kill network admin first if running
1. `airmon-ng check wl01`: Checks processes currently running
2. `airmon-ng kill wl01`: Kills proccesses running; may need to do repeatedly
###

## Resources
- [Learn Ethical Hacking With Kali Linux](https://youtu.be/0uvWRwLs5Zo)
