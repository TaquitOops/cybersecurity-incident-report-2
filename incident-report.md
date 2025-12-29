# Cybersecurity Incident Report
## SYN Flood Denial-of-Service Attack

---

## Section 1: Identify the type of attack that caused the network interruption

### One potential explanation for the website's connection timeout error message is:
A denial-of-service (DoS) attack that overwhelmed the web server and prevented it from responding to legitimate user requests.

### The logs show that:
The network logs show an unusually high number of TCP SYN packets originating from a single unknown IP address within a short period of time. Many of these SYN requests are not followed by completed TCP handshakes. As the traffic increases, legitimate employee connections begin to fail and time out.

### This event could be:
A **TCP SYN flood attack**, which is a type of **Denial-of-Service (DoS)** attack.

---

## Section 2: Explain how the attack is causing the website to malfunction

### TCP Three-Way Handshake Explanation

1. **SYN** – The client sends a SYN packet to the server to initiate a connection.
2. **SYN-ACK** – The server responds with a SYN-ACK packet, acknowledging the request and reserving system resources.
3. **ACK** – The client sends an ACK packet to complete the connection and begin data transmission.

---

### Effect of a SYN Flood Attack

When a malicious actor sends a large number of SYN packets without completing the handshake, the server allocates resources for each half-open connection. As these incomplete connections accumulate, the server’s available resources become exhausted.

---

### What the logs indicate and how it affects the server

The logs indicate a sustained flood of SYN requests coming from a single IP address at a rate much higher than normal traffic. As a result, the server is unable to maintain legitimate TCP connections. This leads to failed handshakes, reset connections, and timeout errors for employees attempting to access the website. Eventually, the server becomes unresponsive due to resource exhaustion.

---

## Impact on the Organization

- Employees are unable to access the company sales website.
- Customers may experience service outages.
- Business operations and productivity are negatively affected.
- Prolonged downtime could impact revenue and reputation.

---

## Mitigation and Prevention (Optional)

- Implement SYN flood protection and rate limiting on the firewall.
- Enable intrusion detection and prevention systems (IDS/IPS).
- Use load balancers and DDoS protection services.
- Monitor network traffic for abnormal connection patterns.

---

## Disclaimer

This report is based on a simulated academic exercise. No real systems, organizations, or sensitive data are involved.
