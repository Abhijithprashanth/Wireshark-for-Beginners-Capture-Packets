# Wireshark-for-Beginners-Capture-Packets

## Objective
To gain hands-on experience with Wireshark, a network protocol analyzer, by learning how to capture, filter, and analyze network packets. This project aims to provide a foundational understanding of network traffic inspection, packet structures, and protocol analysis, which are essential skills for network security, troubleshooting, and cybersecurity investigations.

### Skills Learned

- Wireshark Installation & Setup – Learn how to install and configure Wireshark on Ubuntu.
- Packet Capture & Analysis – Capture real-time network packets and analyze them.
- Network Traffic Inspection – Understand how to monitor and interpret network activity.
- Protocol Analysis – Identify and analyze different network protocols (HTTP, HTTPS, TCP, etc.).
- Packet Filtering – Use Wireshark display filters to focus on specific network traffic.
- IP Address Identification – Track and analyze communication between devices using IP addresses.
- Cybersecurity Awareness – Learn how to use Wireshark for basic network security monitoring.

### Tools Used

- **Kali Linux** for penetration testing and security auditing.
- **Wireshark** for network traffic analysis.
- **TCP/IP Protocol Suite** – Includes protocols like HTTP, HTTPS, TCP, and IP for network analysis.

## Steps

Below are the key steps taken in the VAPT process:

### 1. Install and set up Wireshark on Ubuntu.
In the first step we need to install wireshark. basically wireshark is an inbuilt software in kali linux. If wireshark is not installed we need to install it first. 

Step 1: Update your Kali Linux system
**sudo apt-get update && sudo apt-get upgrade**

Step 2: Install Wireshark
**sudo apt-get install wireshark**

Step 3: Configure Wireshark
**sudo dpkg-reconfigure wireshark-common**

Step 4: Launch Wireshark
**wireshark**

### 2. Start a packet capture on an ethernet port and save it to file.
Step 1: Launch Wireshark
Step 2: Select the Ethernet Interface
Step 3: Start Capturing Packets
Step 4: Stop the Capture
Step 5: Save the Capture to a File

### 3. Use a display filter to detect HTTPS packets. 
Step 1: Open Wireshark and Load a Capture File
Step 2: Apply a Display Filter for HTTPS Traffic
        in the filter bar use filter as **tls** or **tcp.port == 443**
Step 3: Apply the Filter
Step 4: Analyze the Packets

also use filter **https**

### 4. Visit a web page and detect its IP address using a display filter

**tls.handshake.type ==1**


### 5. Locate all HTTPS packets from a capture not containing a certain IP address.
Step 1: We can use a conditional statement in Wireshark to include or exclude packets from the capture.
**!(ip.addr == <ip>) and tcp.port == 443**
Step 2: We can add multiple conditions by using parentheses to prevent excustion errors
**!(ip.addr == <ip>) and (tcp.port == 80 or tcp.port == 443)**

### 6. Capstone Task: Use Wireshark to capture and observe ethernet packets on HTTP and HTTPS ports
