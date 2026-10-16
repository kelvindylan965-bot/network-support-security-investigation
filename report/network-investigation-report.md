\# Network Support, Security and Incident Investigation



\*\*Author:\*\* Kelvin Kiptoo Ngetich  

\*\*Tools Used:\*\* Wireshark, Windows PowerShell and nslookup  

\*\*Date:\*\* 16 October 2026



\## 1. Introduction



This project was about learning how to investigate network traffic using Wireshark. I looked at DNS queries, IP addresses and QUIC traffic while visiting example.com in my browser.



My goal was to understand how computers find websites and how to identify different types of network traffic.



\## 2. Tools Used



\- Wireshark for capturing and examining network packets.

\- nslookup for checking DNS records.

\- Windows PowerShell for running commands and organizing project files.

\- A web browser for visiting example.com.



\## 3. What I Did



First, I installed Wireshark and selected my Wi-Fi network interface. I started capturing traffic and used nslookup to check the IP addresses associated with example.com.



Next, I applied Wireshark filters to examine DNS queries and responses. I also visited the website while capturing traffic and investigated TCP connection packets.



Finally, I examined QUIC packets and saved screenshots of the DNS and QUIC traffic as evidence.



\## 4. DNS Investigation



The nslookup command returned these IPv4 addresses for example.com:



\- 104.20.23.154

\- 172.66.147.243



It also returned two IPv6 addresses. The DNS server shown in the command output was 192.168.100.1.



I used Wireshark to find DNS packets related to example.com and saved a screenshot as evidence.



\## 5. QUIC Traffic Investigation



I found QUIC packets travelling between my computer, which had the IP address 192.168.100.5, and the address 172.66.147.243.



Two packets were particularly useful:



\- Packet 180385 travelled from 172.66.147.243 to my computer.

\- Packet 180387 travelled from my computer to 172.66.147.243.



The packets contained QUIC handshake-related information. Their connection ID fields also supported treating them as related traffic.



QUIC is commonly used for modern web communication, including HTTP/3. However, I could not conclusively prove that these packets belonged to my specific visit to example.com.



I saved a screenshot showing both packets.



\## 6. TCP Traffic Investigation



I used Wireshark filters to examine TCP connection establishment and connection-termination packets.



I observed SYN, SYN-ACK, ACK, FIN and RST traffic. However, I could not confidently link every packet to the website I was testing.



I therefore avoided treating the reset packets as evidence of an attack or website failure.



\## 7. What I Learned



Through this project, I practised how to:



\- Use Wireshark to capture and filter network traffic.

\- Examine DNS queries and responses.

\- Identify source and destination IP addresses.

\- Recognize TCP connection-handshake packets.

\- Investigate QUIC traffic.

\- Save evidence and write a technical report.

\- Avoid making security conclusions without enough evidence.



\## 8. Challenges and Limitations



My capture contained traffic from other network activities, which made it difficult to identify every packet associated with the website.



I also learned that finding an IP address in a DNS response does not automatically prove that a particular connection belongs to that website. More evidence is needed to make that connection confidently.



\## 9. Conclusion



This project helped me gain practical experience with Wireshark and basic network investigation. I learned how to examine DNS, TCP and QUIC traffic and how to use packet details to support my findings.



The main lesson was to investigate carefully, document what I can actually observe and avoid making assumptions about suspicious traffic.



\## 10. Evidence



The following screenshots support my investigation:



\- `evidence/dns-lookup-evidence.png`

\- `evidence/quic-connection-evidence.png`



This project was completed as a beginner networking lab exercise to practise network support, troubleshooting and traffic analysis.

