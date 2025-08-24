[HackTheBox Profile Page](https://app.hackthebox.com/users/2141921)

# Notes

## Conceptual

### TCP vs UDP
TCP is generally used for applications requiring reliable, ordered data transmission. The most common TCP ports include:

* **HTTP/HTTPS (ports 80 and 443)**: Web browsing
* **FTP (port 21)**: File Transfer Protocol for transferring files
  * On a misconfigured FTP server, after connecting can use the username `anonymous` to attempt login without an account. In this case use any password.
  * It's standard to be encrypted via SSL/TLS as SFTP or FTP over SSH (likely not port 21). TCP protocol (commonly used in port 21) is plain text.
  * Once authenticated, if needed use `help` for a list of possible actions.
* **SMTP (port 25)**: Simple Mail Transfer Protocol for outgoing email
* **SSH (port 22)**: Secure Shell for secure remote administration of devices
* **Telnet (port 23)**: Specifically designated for Telnet, which is designed for command-line interface access to remote systems
  * root, admin, administrator may be default user names, which may also have a blank password

UDP is preferred for applications prioritizing speed and low latency over perfect reliability. Common UDP ports include:

* **DNS (port 53)**: Domain Name System used for domain name resolution
* **DHCP (port 67)**: Dynamic Host Configuration Protocol for issuing IP addresses
* **NTP (port 123)**: Network Time Protocol
* **VoIP (port 56)**: Voice over Internet Protocol used for phone conversations

## Tools

### nmap (Network Mapper)
* `nmap -sV {target_IP}` - Probe open ports to determine service/version info