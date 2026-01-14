# SPLUNK BOSS OF THE SOC LABS
# RANSOMWARE ANALYSIS WITH SPLUNK

## Scenario
After the excitement of yesterday, Alice has started to settle into her new job. Sadly, she realizes her new colleagues may not be the crack cybersecurity team that she was led to believe before she joined. Looking through her incident ticketing queue she notices a “critical” ticket that was never addressed. Shaking her head, she begins to investigate. Apparently on August 24th Bob Smith (using a Windows 10 workstation named we8105desk) came back to his desk after working-out and found his speakers blaring (click below to listen), his desktop image changed (see below) and his files inaccessible.

Alice has seen this before... ransomware. After a quick conversation with Bob, Alice determines that Bob found a USB drive in the parking lot earlier in the day, plugged it into his desktop, and opened up a word document on the USB drive called "Miranda_Tate_unveiled.dotm". With a resigned sigh she begins to dig into the problem...




### Skills Learned



### Tools Used
- SPL Splunk
## Steps
# 001 Question:
What was the most likely IPv4 address of we8105desk on 24AUG2016?
- <img width="437" height="232" alt="image" src="https://github.com/user-attachments/assets/acd2eeea-a169-4111-9945-0627ac7118f9" />
- <img width="405" height="131" alt="image" src="https://github.com/user-attachments/assets/2f427de5-df01-4bb5-a7c4-4bbc890dd967" />
through src_ip, notice only one IP valid

# 002 Question:
Amongst the Suricata signatures that detected the Cerber malware, which one alerted the fewest number of times? Submit ONLY the signature ID value as the answer.
- <img width="564" height="331" alt="image" src="https://github.com/user-attachments/assets/903b0229-3334-46e2-bfa6-c381071ace20" />
The SPL returns all Suricata alerts triggered by Cerber malware.
With main focus on alerts.signature_id , aggregate the results statistically and on the table notice count with the lowest figure
- <img width="856" height="199" alt="image" src="https://github.com/user-attachments/assets/694fb065-02a5-46d0-8ea3-8594019ec628" />

# 003 Question:
What was the first suspicious domain visited by we8105desk on 24AUG2016?
- Suspicious domains are typically found in DBS logs meaning using the sourcetype=stream dns.
- Narrowing the results to specific host and date 
- <img width="640" height="282" alt="image" src="https://github.com/user-attachments/assets/13933fa5-4164-449e-9388-017c13c5ad65" />

# 003 Question:
During the initial Cerber infection a VB script is run. The entire script from this execution, pre-pended by the name of the launching .exe, can be found in a field in Splunk. What is the length of the value of this field?
-





