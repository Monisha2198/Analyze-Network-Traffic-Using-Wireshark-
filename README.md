 Analyze-Network-Traffic-Using-Wireshark-
 Task 5: Capture and Analyze Network Traffic Using Wireshark (VMware Linux)
Objective
Capture live network packets in a Linux VM using Wireshark and identify at least 3 different protocols.
 Environment
- OS: Linux (Kali VMware)
- Tool: Wireshark
- Network Mode: NAT / Bridged
Steps Followed
 if not installed 
Install Wireshark in Linux
Open Terminal and run:
sudo apt update
sudo apt install wireshark -y

1. Open Wireshark  
  In root terminal type
   wireshark

2. Checked active network interface  
   open another root terminal type to find the active network interface
   ip a
   Selected the one with an IP address (e.g., `ens33`)

3. Started packet captureon the active interface.

4. Generated traffic  
   in root terminal
   ping google.com
       or
   curl http://example.com
 
   Also browsed websites using Firefox.

5. Stopped capture after ~1 minute.

6. Filtered packets using:
   - dns
   - http
   - tcp
   - icmp

Protocols Identified:
1. DNS
   - Function: Domain Name Resolution
   - Example: Query for google.com seen in Packet 

2. TCP
   - Function: Connection-oriented data transfer
   - Example: SYN, SYN-ACK, ACK sequence in Packets

3. ICMP
   - Function: ICMP is used to send control messages and error reports between network devices. 
               It does not carry application data like HTTP or DNS — instead, it helps manage and troubleshoot the network.
     Example: 
               Packet Type: Echo Request (Type 8)
               Description: A ping was sent from my system to google.com to check if it’s reachable.
               Packet Type: Echo Reply (Type 0)
               Description: google.com responded to the ping, confirming it is online.


