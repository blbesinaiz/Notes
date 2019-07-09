# WIFI Ethical Hacking (Kali Linux)
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
    
 2. Add a Proxy
    - At EOF add desired proxy with port number
      - ie Socks5 127.0.0.1 9050
      


## Resources
- [Learn Ethical Hacking With Kali Linux](https://youtu.be/0uvWRwLs5Zo)
