## Networking Concepts: DNS, IP, Subnets & Ports
### Task 1: DNS – How Names Become IPs
1. When you type google.com in your browser, your computer first looks for the IP address of Google using DNS. After getting the IP address, the browser connects to Google’s server over the internet using HTTPS. Google’s server then sends the website data back to your browser.Finally, the browser reads that data and displays the Google homepage on your screen.
2. A: Maps a domain name to an IPv4 address.
- AAA: Maps a domain name to an IPv6 address.
- CNAME: Creates an alias from one domain name to another.
- MX: Specifies mail servers responsible for handling email for the domain.
- NS: Defines the authoritative name servers for the domain.

3. Run dig.google.com
<img width="570" height="394" alt="image" src="https://github.com/user-attachments/assets/1cde078c-a593-48c7-a457-47fe29532ff6" />

### Task 2: IP Addressing
1. An IPv4 address is a unique address used to identify a device on a network or the internet. It helps computers communicate with each other
2. A public IP address is used on the internet and can be accessed globally. It is assigned by an Internet Service Provider (ISP).
3. A private IP address is used inside local networks like homes, offices, or companies and is not directly accessible from the internet.
4. Run show ip addr
<img width="975" height="435" alt="image" src="https://github.com/user-attachments/assets/e3ec6668-aaad-4a00-a873-acac0d8c9649" />

### Task 3: CIDR & Subnetting
1.   /24 is CIDR notation. It tells us how many bits of the IP address are used for network portion. Here first 24 bits (out of 32) are reserved for network. That leaves 8 bits for the host address. IP range : (192.168.1.0 - 192.168.1.255) Total :256 IP's
2.   How many usable hosts in :
- /24 : 254
- /16 : 65,534
- /28 : 14
3. Subnet divides one large network into small, manageable and efficient sub-networks.
4. Quick exercise — fill in:
  
| CIDR | Subnet Mask     | Total IPs | Usable Hosts |
|------|-----------------|-----------|--------------|
| /24  | 255.255.255.0   | 256       | 254          |
| /16  | 255.255.0.0     | 65,536    | 65,534       |
| /28  | 255.255.255.240 | 16        | 14           |

### Task 4: Ports – The Doors to Services
1. A port is a logical communication endpoint used by computers to identify which application or service should receive network data.
2.  Document these common ports:

| Port | Service |
|------|---------|
| 22   | SSH     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 53   | DNS     |
| 3306 | MYSQL   |
| 6379 | Redis   |
| 27017| MongoDB |
3. Run ss -tulpn — match at least 2 listening ports to their services
tcp        LISTEN      0           4096                      [::]:80                        [::]:*
tcp        LISTEN      0           4096                      [::]:3306                      [::]:*

### Task 5: Putting It Together
1. When you run http://my-app.com:8080

protocol: HTTP
DNS: myapp.com is a domain name.
IP address: After getting the IP address, your computer knows which server to contact on the internet.
Port number: 8080 (often use for backend server)
2. Your app can't reach a database at 10.0.1.50:3306 — what would you check first?

sudo systemctl status mysql
journalctl -u mysql - Check Logs
Verify Credentials
