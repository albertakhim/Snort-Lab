### Snort-Lab
Objective
Snort is an open-source network intrusion detection system (IDS) and intrusion prevention system (IPS). Its primary objective is to monitor network traffic for suspicious activity and vulnerabilities, providing real-time alerts and allowing network administrators to take action to mitigate threats.

 ### Skills Learned

Network Traffic Analysis: used Snort to  inspect network packets in real time, analyzing them for malicious activities.
Signature-Based Detection: Used a database of known attack signatures to identify threats.
Protocol Analysis: Examined network protocols to detect anomalies or suspicious behaviors.
Content Matching: Searched for specific content patterns within packets, which helped detect known threats.
Alert Generation: Generated alerts for detected threats, This will  enable administrators to respond promptly in real situations.
Intrusion Prevention:  blocked detected threats by using snort rules.
Network Security Monitoring: I continuously monitored and analyzed  network traffic.

### Installation

Installation.
I am using Ubuntu vision Ubuntu 22.04.3 LTS  server. i started by runnung the update and upgrade command and created a directory called snort  with the mkdir command. used the ls command to confirm that the directory has been created i installed the dependecies required for snort withcommand (sudo apt-get install -y build-essential libpcap-dev libpcre3-dev libdumbnet-dev bison flex zlib1g-dev). Also downloaded and install the DAQ (Data Acquisition library) with the command (wget https://www.snort.org/downloads/snort/daq-2.0.7.tar.gz
![snort1](https://github.com/albertakhim/Snort-Lab/assets/174826500/69030f8c-c628-40a8-b494-5ecf0d55dfbb)
![snort2](https://github.com/albertakhim/Snort-Lab/assets/174826500/b5ff96a0-f200-4b9d-b451-3bb040a7d740)
![snort 3](https://github.com/albertakhim/Snort-Lab/assets/174826500/61918858-efcf-4de8-9a24-41eadab19007)

tar -xzvf daq-2.0.7.tar.gz
cd daq-2.0.7
./configure
make
sudo make install
cd ..)

![snort5](https://github.com/albertakhim/Snort-Lab/assets/174826500/4d9ef3d5-07af-4e70-ac82-9b67a3e8e542)
![snort6](https://github.com/albertakhim/Snort-Lab/assets/174826500/129e16c8-da19-4414-973d-c99228c12194)

In the next step, i downloaded and installed snort using the source code (wget https://www.snort.org/downloads/snort/snort-2.9.20.tar.gz
tar -xzvf snort-2.9.20.tar.gz
cd snort-2.9.20
./configure --enable-sourcefire
make
sudo make install
cd ..
) Next i configured snort, updated the rules and tested the config file with the config test command sudo snort -T -c /etc/snort/snort.conf-T. The test was sucessful so i enabled snort monitor my network  with the command (sudo snort -A console -i 172.19.45.68/20 -c /etc/snort/snort.conf)
![snort8](https://github.com/albertakhim/Snort-Lab/assets/174826500/afb70e98-d1db-4899-81bd-a73ee578e3e3)
![snort9](https://github.com/albertakhim/Snort-Lab/assets/174826500/b41fb9c8-498d-4012-b7ba-9e9ca2834606)
![snort output](https://github.com/albertakhim/Snort-Lab/assets/174826500/8ef46c56-a748-4253-8603-0424d70994f3)

### Tools
snort-2.9.20

### Use
Sniffer Mode. I was able to capture packet from my attack machine.. from the attack machine, i pinged 8.8.8.8 and used snort to capture the packet
![sniffer snort1](https://github.com/albertakhim/Snort-Lab/assets/174826500/c1b11488-eece-4e5b-9b77-8d1fe1e8f4f6)
![sniffer snort result](https://github.com/albertakhim/Snort-Lab/assets/174826500/fe4e6e1a-30ab-49d0-ad00-ee3aef16b03c)


Snort in Logger Mode using the -l, -r and -n command. I was able to capture the previous  traffic and log the file in the output folder is /var/log/snort
![snort logger 3](https://github.com/albertakhim/Snort-Lab/assets/174826500/aad998f5-bb95-43a7-bc80-3b3cd4b28859)
![snort logger 2](https://github.com/albertakhim/Snort-Lab/assets/174826500/9b22ff8f-39c5-4a9a-ab80-650fa1ca7801)
![snort logger 1](https://github.com/albertakhim/Snort-Lab/assets/174826500/f1d1fe27-4025-4893-9623-5633331494a3)


