# Firewall Configuration Report

## Firewall Rules

### 1. Allow SSH (Port 22)
```bash
sudo ufw allow 22/tcp
```
**Explanation:** This rule allows SSH connections to ensure remote access to the server.

### 2. Allow HTTP (Port 80) and HTTPS (Port 443)
```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```
**Explanation:** These rules allow web traffic to the server for hosting websites and secure connections.

### 3. Block All Other Incoming Traffic
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
**Explanation:** Denying all incoming connections by default enhances security by only allowing explicitly defined services. Outgoing connections are allowed for server operations.

### 4. Enable Logging for Blocked Traffic
```bash
sudo ufw logging on
```
**Explanation:** Logging blocked connections helps in monitoring and identifying unauthorized access attempts.

### 5. Prevent SYN Flood Attacks
```bash
sudo ufw limit 22/tcp
```
**Explanation:** This rule limits SSH connection attempts to mitigate brute force and SYN flood attacks.

### 6. Block ICMP Echo Requests (Ping)
```bash
# Block ICMP echo requests (ping)
-A ufw-before-input -p icmp --icmp-type echo-request -j DROP
```
**Explanation:** This rule prevents ICMP echo requests (ping), mitigating ICMP flood attacks.

### 7. Limit Excessive HTTP/HTTPS Requests
```bash
sudo ufw limit 80/tcp
sudo ufw limit 443/tcp
```
**Explanation:** This rule limits excessive requests to prevent basic DoS attacks.

## Conclusion
These firewall rules effectively secure the server by allowing necessary services while blocking unauthorized access and common network attacks.

