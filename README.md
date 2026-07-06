# ai_security_testing_lab
AI-augmented cybersecurity testing pipeline using Splunk ML anomaly detection, Nmap, Nikto, and VirusTotal to simulate and analyze real-world attacks against DVWA.

## Environemnt Architecture:
Attacker Machnine: MacBook Pro M2 running Ubuntu VM (UTM)
Target: DVWA running in Docker container
SIEM: Splunk Enterprise with native ML anoaly detection
Network Capture: Wireshark on Ubunutu VM

## Tools Used:
| Tool | Purpose |
| Nmap | Network reconnaissance and port scanning |
| Nikto | Automated web vulernerability scanning |
| Wireshark | Network traffic capture and analysis | 
|Splunk | SIEM and ML anomaly detection | 
| DVWA | Deliberately vulnerable web application target | 
| Docker | Container hostin DVWA target |
| VirusTotal | AI-powered threat intelligence enrichment |

## Attack Simulations Performed:
- SQL Injection - returned all 5 database records
- Command Injection - executed whoami returning www-date
- Brute Force - 5 failed authenication attempts against admin
- Network Reconnaissance - Nmap 3-scan methodology
- Automated Vulnerability Scanning - Nikto web scanner

## Key Findings:
| Metric | Result |
| Total security events generated | 114+ |
|Nmap open ports discovered | 12 | 
| DVWA vulernabilities confirmed | 3 | 
| VirusTotal engines analyzed | 91 |
| Splunk ML anomaly score | -1.3863 |

## AI Detection Methodology:
I ran Splunk's built-in AI on my 114 attack events. The AI gave each event a score of -1.3683 meaning
it flagged them as statistically unusual, and identified the source host as a probable cause of the anomaly.

## Lessons Learned:
- AI anomaly detection adds staticstical context traditional rules cannot provide
- VirusTotal correctly classified all private IPs as clean confirming AI distinguishes
  internal vs external threats
- Combining Nmap reconnaissance, Splunk ML anomaly detection, and VirusTotal threat intelligence provides
  more comprehensive security coverage than any single tool alone
