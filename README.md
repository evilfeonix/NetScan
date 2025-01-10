![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg) 

# NetScan

NetScan is a simple Python-based script that can be used as a port scanner to grab and print open ports along with banners. This script uses the `socket` library for checking open ports and the `telnetlib` library to grab banners from those ports. 

NetScan make used of a Python's library known as `threading`, means that NetScan scan multiple ports in parallel, which speeds up the process. Just 1 minute, 1 minute is enough for NetScan to scan all the posible port range from `0` to `65535` and return their banners.

# How It Works:
1. Port Scanning: The script attempts to connect to each port in the specified range. If the connection is successful (i.e., the port is open), it prints that the port is open.

2. Banner Grabbing: If a port is open, the script will attempt to retrieve a banner from that port. The banner is usually some kind of identifying text returned by the service running on that port (e.g., HTTP headers, SSH version, etc.).

3. Multithreading: The script uses Python's threading library to scan multiple ports in parallel, which speeds up the process.

# NetScan Installation:
```bash
apt update && apt upgrade -y
apt install python3
git clone https://github.com/evilfeonix/NetScan.git
```

# NetScan Usage:
Run the script by Provide the target IP address, range of ports to scan and your hacker nickname.

## For example:

```bash 
cd NetScan
python3 scann.py 192.168.1.1 20 1024 evilfeonix
```

### Where as:
* `192.168.1.1` is the target ip address (requested)
* `20` is the minimum port to start the scan (optional)
* `1024` is the maximum port to end the scan (optional)
* `evilfeonix` is the hacker nickname (optional)

If ports are not provided, NetScan gonna scan all posible ports (`0` - `65535`)

# NetScan Output

The script will print the open ports and their corresponding banners (if available). This can help identify services running on the open ports.

```shell
===========================================================   
[+] HOST: www.evilfeonix.com, IP: 192.168.56.1  [+]
===========================================================   
[+] Started Scanning at 03:00:30, 09-01-2025...
[+] 192.168.56.1:80 - OPENNED
[+] 192.168.56.1:135 - OPENNED
[+] 192.168.56.1:139 - OPENNED
[+] 192.168.56.1:445 - OPENNED
[+] 192.168.56.1:2179 - OPENNED
[+] 192.168.56.1:5040 - OPENNED
[+] 192.168.56.1:7680 - OPENNED
[+] 192.168.56.1:49664 - OPENNED
[+] 192.168.56.1:49665 - OPENNED
[+] 192.168.56.1:49666 - OPENNED
[+] 192.168.56.1:49667 - OPENNED
[+] 192.168.56.1:49668 - OPENNED
[+] 192.168.56.1:54267 - OPENNED
[+] Saved result\www.evilfeonix.com_2025-01-09_03-01-30.853445.txt
[+] Finished Scanning at 03:01:31, 09-01-2025...
===========================================================
[+]         65535 Port are Scanned Successfully         [+]
[+]             13 of 65535 Port are Openned            [+]
[+]            Duration Taken: 0:01:00.155326           [+]
[+]  You gotta open result directory in order to check  [+]
[+]   the complete result that include targets banner   [+]
===========================================================
       (:     G00D BYE AGENT evilfeonix!
               ^_^       have a nice day...     :)      
===========================================================
```

# Important Notes:

> Timeouts: The timeout is set to 2 seconds, but you may adjust it depending on the network conditions.

> Banner Grabbing: Some services may not provide a banner or might restrict banner grabbing, in which case the script will just skip that port.

> Legal Use: Always have permission before scanning ports on any network or system. Unauthorized scanning can be considered illegal in many jurisdictions.
