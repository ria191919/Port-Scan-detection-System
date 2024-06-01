# Spans vs Taps Role in Packet Analysis (White Paper)

<p style="margin-bottom: 20px; margin-left: 150px;"><img src="./images for md file/img1.png" alt="ex" width="150"height="232"> <img src="./images for md file/img2.png" alt="ex" width="150"></p>


- Network taps: Physical devices capturing all traffic on a network segment.
- SPANs: Copy specific port traffic to a monitoring port on switches or routers.
- Both aim to facilitate PCAP analysis but in different ways.
- TAPs provide comprehensive analysis by capturing all traffic.
- SPANs offer targeted data for further analysis by copying specific port traffic.


## Points

- Traditional methods like using hubs, SPAN ports, or in-line taps have their pros and cons. While hubs are inexpensive but limited in functionality, SPAN ports are readily available but can cause oversubscription and configuration complexities.
- Network taps provide visibility without relying on SPAN ports. They connect directly to a network link, forwarding a copy of the signal to monitoring ports without actively participating in network operations.

---

# Detection of Slow Port Scanning Attacks (Paper 2)
2020

- Packet-based analysis used to detect the different types of port scan attacks.
- Scanning attacks performed through communication protocols i.e. TCP, UDP, ICMP, SCTP, and FTP, etc.
- General common methods cannot detect scans that evade detection by increasing the time randomly between probes or by originating from more than one source that is known as a slow port scan attack.
- The main difficulty of detecting the slow port scan attack is uncertainty: there is no standard of judgment about a slow port scan attack.
- Slow port scan attack detection is a widely studied area where detection solutions are proposed for different types of scanning attacks in static time duration.
- The proposed solution addresses the two challenges.
- Firstly, due to the unusual nature of port scan attempts using different channels only a limited number of techniques exist, moreover, these techniques are either not efficient or not reliable to operate on TCP header fields especially when timestamp values are random.
- Therefore, to address this limitation, we proposed a reliable framework for the detection and analysis of outliers, this framework does not only overcome the existing problems but also able to give accurate results.
- Packet data analysis offers techniques in literature from realms of machine learning that shows the deterministic results having low accuracy.
- The motivation is to overcome the flaws of existing techniques that are unable to detect slow port scanning attacks made on random time intervals as well as with a gradual increase or decrease in the time interval.
- The proposed technology will not only identify the slow port scanning attacks with random time intervals but also by applying the statistical techniques would be able to offer higher accuracy thus yields to low false alarms.
- This framework is constructed by combining three modules: Intrusion detection module (perform packet analysis and detects intrusions using analyzing results), Intrusion prevention module (manages the attack and abnormal traffic by blocking the packets that are identified as attack and decreasing the bandwidth if series of packets is suspicious) and decreasing the bandwidth if series of packets is suspicious) and Control module (perform logging and configuration tasks).
- A total of sixteen test scenarios were implemented in the testing phase.
- Fuzzy terms were mentioned as Normal, Suspicious, and Attack in a short, middle, and longer period.
- The guidelines on which it is further determined whether to classify an IP as scanner IPs, suspicious IPs and valid customers are shown with a mathematical perception under:

<p style="margin-bottom: 20px; margin-left: 100px;"> <img src="./images for md file/img3.png" alt="ex" width="400"> </p>


- The time gap of four seconds, four minutes, and six minutes is taken as a threshold value.
- Now Profiler filters out every day and suspicious packets on the premise of LTP (Long Term Profiler) and the STP (Short Term Profiler).
- After that, the Anomaly Detector decides on the idea of experiment sports which ones are the fast scans and which ones must be marked as gradual scans.
- Stealthy scans are captured on the premise of a threshold as low as the edge is as excessive as the accuracy is.


<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img4.png" alt="ex" width="400"> </p>


- Each terminal is now linked to the Linux shell of each VM and on the routers, the software protocols are enabled.
- On the other side, we made the victim machine vulnerable by disabling SELinux on Linux Operating System and the other victim machine that is running on Windows XP is also made vulnerable by switching off its firewall.
- The GNS3 network simulator makes it easy to capture and view data that is flowing between the interfaces of devices running on its simulation.However, on Virtual Box, the data is captured.

The guidelines on which it is further determined whether to classify an IP as scanner IPs, suspicious IPs and valid customers are shown with a mathematical perception under:

- The time gap of four seconds, four minutes, and six minutes is taken as a threshold value.
- Now Profiler filters out every day and suspicious packets on the premise of LTP (Long Term Profiler) and the STP (Short Term Profiler). After that, the Anomaly Detector decides on the idea of experiment sports which ones are the fast scans and which ones must be marked as gradual scans.
- Stealthy scans are captured on the premise of a threshold as low as the edge is as excessive as the accuracy is.

Each terminal is now linked to the Linux shell of each VM and on the routers, the software protocols are enabled. On the other side, we made the victim machine vulnerable by disabling SELinux on Linux Operating System and the other victim machine that is running on Windows XP is also made vulnerable by switching off its firewall. The GNS3 network simulator makes it easy to capture and view data that is flowing between the interfaces of devices running on its simulation. However, on Virtual Box, the data is captured.

## Packet Capturing

Some open-source sniffer software is quite helpful in achieving this task of data capturing, for example, Wireshark, TCPDUMP, Soft Perfect Network Protocol Analyzer, Ethereal, and Capsa. The live network data packets capturing is performed in two ways, the first approach to capture data packets is performed using C# code while the second approach we used to capture the network data packets is through the Wireshark network sniffer (also known as network analyzer) tool to intercept and log traffic that passes over the digital network.

## Packet Recognition

Mentioned features are important to gather while implementing the scanning filter as well as it is of great help in the detection filter too:

- Source IP
- Destination IP
- Source port
- Destination port
- The cumulative sum of TCP flags
- Timestamp

## Scanning Filter

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img5.png" alt="ex" width="400"> </p>

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img6.png" alt="ex" width="400"> </p>

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img7.png" alt="ex" width="400"> </p>

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img8.png" alt="ex" width="400"> </p>

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img9.png" alt="ex" width="400"> </p>


## Detection Filter

Detection filter is responsible for the identification of the type of scans performed by scanner IP (single or parallel). This filter will not only classify the single and parallel port scan attacks but also takes into account the number of hits attempted on a victim machine.

1. Fast Scan: Fast port scans are characterized by a simple feature, these types of scan attacks try to connect too many targets in a smaller period of duration. Fast Scan is easiest to be detected because the attempts made by the same IP are higher in number and are performed one after another with the time gap of only 30 seconds.
2. Slow Scan: The main contribution of this research work is to identify the slow port scan attacks. The slow port scan attacks can be identified by examining the specific IP’s behavior over a large time frame, for instance, one hour. The difficulty of detecting the slow port scan attack is the uncertainty of these types of scan attempts, there is no standard of judgment about slow port scan attacks. An attacker may send a scanning probe by the difference of 10 sec, 20 sec or 1 day.

<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img10.png" alt="ex" width="400"> </p>
<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img11.png" alt="ex" width="400"> </p>
<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img12.png" alt="ex" width="400"> </p>

The table shows the comparison of the previous scan detector’s duration gap results as compared to the proposed system. Using the Nmap tool, 13 different types of scan activities have done in a victim machine from the attacker machine. Scan type shows different types of scan details. The third column shows the time taken for scan activities(in sec).

<<<<<<< HEAD
<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img13.png" alt="ex" width="400"> </p>
=======
<p style=" margin-top: 50px; margin-bottom: 40px; margin-left: 100px;"> <img src="./images for md file/img13.png" alt="ex" width="400"> </p>

>>>>>>> 848e578a75c60a24ebb83e575f7fb623b1d2ee29