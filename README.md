# Network-Analysis-Lab

## Objective

The Network Analysis Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to analyze and monitor network security within Snort, Zeek, and Wireshark, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

Project 1: Brute-Force & Reverse Shell (Snort)

### Skills Learned

- Advanced understanding of IDS/IPS concepts.
- Proficiency in analyzing and interpreting network logs.
- Advanced understanding of writing Snort rules.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- IDS/IPS.
- Network analysis tools (such as Snort,Wireshark,Zeek) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
Project 1: Brute-Force & Reverse Shell (Snort)  

||  Objective: Observe the live traffic with Snort and create a rule to stop the brute-force attack. 

![image](https://github.com/user-attachments/assets/6cd4d4cc-ad55-47a5-baad-1507cedc1cd9)
*Ref 1: Start Snort in sniffer mode and log the data*

![image](https://github.com/user-attachments/assets/073e77c9-1a55-4a24-9084-f41bf54a2955)
*Ref 2: Run Snort for a while then read the log file.*

After doing manual inspection on a couple of packets I've noticed a pattern of two ports(80 & 22) sending and receiving data. I then monitored a couple of packets from each port using a filter to look for suspicious content.
![image](https://github.com/user-attachments/assets/298dabd2-601c-4cbc-b717-09a783fbf427)
*Ref 3: Suspicious packet (very large packet)*

After further analysis, I have determined that the attacker is attempting to gain unauthorized access via port 22 (SSH). The next step is to block incoming traffic on port 22 and halt the ongoing brute force attempt.

![image](https://github.com/user-attachments/assets/5e79284c-69f7-4d09-921b-3de3089bec01)
*Ref 4: Open the text editor to create a new rule*

![image](https://github.com/user-attachments/assets/07b51c0f-55ed-47e1-ae2c-328a4cb52492)

This rule will drop all incoming SSH traffic. Now we need to activate the IPS to be able to use the rule.

![image](https://github.com/user-attachments/assets/966ab1ff-7761-4af2-8888-b7c99f3fd527)


