### 🐧 Day 11: Networking Basics

## Today's Objective
To check the system's network configuration and troubleshoot basic connectivity using standard Linux networking tools.

## Key Learnings
IP Address & Interfaces: I learned that ip addr show is the modern and preferred command to find your machine's IP address and view the status of its network interfaces (like eth0 or wlan0).

Connectivity Test (ping): The ping command is the first tool to use for troubleshooting. It sends a small packet to a target host and waits for a reply, confirming that a network path exists between the two.

Listening Ports (ss): The ss (socket statistics) command is a powerful tool to see which network ports are open and listening for incoming connections on your system. This is crucial for security and for verifying that server applications are running correctly.

DNS Lookup (dig): The dig (Domain Information Groper) command is used to query DNS servers. It translates human-friendly domain names (like google.com) into computer-friendly IP addresses (like 142.250.196.110).

## Commands Practiced

ip addr show
ping
ss
dig

## Task Walkthrough: Checking Network Status
Today's tasks involved using these tools to get a complete picture of my machine's network status.

1. Find My IP Address:
I used ip addr show to find the IP address assigned to my main network interface.

$ ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 ...
    inet 127.0.0.1/8 scope host lo
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 ...
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic enp0s3
In this case, my IP address on the local network is 10.0.2.15.

2. Test Internet Connectivity:
Next, I used ping to confirm I could reach the internet. I had to press Ctrl+C to stop it.

$ ping google.com
PING google.com (142.250.196.110) 56(84) bytes of data.
64 bytes from del11s13-in-f14.1e100.net (142.250.196.110): icmp_seq=1 ttl=116 ms
64 bytes from del11s13-in-f14.1e100.net (142.250.196.110): icmp_seq=2 ttl=116 ms
...
--- google.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
3. Check for Listening Ports:
Finally, I used ss -tl to see which services were listening for TCP connections on my machine.

$ ss -tl
State      Recv-Q     Send-Q         Local Address:Port           Peer Address:Port
LISTEN     0          4096           127.0.0.53%lo:domain               0.0.0.0:*
LISTEN     0          128                  0.0.0.0:ssh                  0.0.0.0:*
LISTEN     0          128                     [::]:ssh                     [::]:*

This output shows that my system is listening for DNS queries (domain) on the loopback address and for SSH connections on all interfaces.

## Personal Reflections
These command-line tools provide so much clarity about what's happening on the network. Being able to quickly find my IP, confirm my connection is live, and see exactly which ports are open feels empowering. It's easy to see how these simple commands form the foundation of all network troubleshooting. ss -tl is particularly interesting, as it gives you a quick security overview of your machine.
