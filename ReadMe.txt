# 🛡️ SOC Automation with Wazuh + Shuffle SOAR  
### 🚀 Detecting & Responding to Credential Theft (Mimikatz) and Malicious IP Traffic

## 📌 Project Overview
In this project, I built a **mini-SOC automation pipeline** using **Wazuh SIEM** and **Shuffle SOAR**.  

The system detects and automatically responds to:  
- **Mimikatz Process Execution** → Custom rule + Active Response kills the process.  
- **Suspicious Network Connections** → Outbound/inbound IP reputation checked with **VirusTotal API**.  
- **Malicious IP Detection** → Wazuh creates an alert and triggers an Active Response to block the IP temporarily (firewall rule).  

This project showcases how open-source tools can be orchestrated to provide **endpoint and network defense automation**, similar to real SOC workflows.



## 🎯 Use Cases Implemented
- ✅ **Custom Process Detection** → Detect & kill `mimikatz.exe` (or renamed versions).  
- ✅ **IP Reputation Check** → Outbound/inbound IPs checked against VirusTotal.  
- ✅ **Malicious IP Blocking** → Temporary block (firewall rule) when malicious IP detected.  
- ✅ **Shuffle SOAR Integration** → Analyst email workflow with one-click Active Response.  
- ✅ **Centralized Rule Management** → Using Wazuh `agent.conf` for consistent policy deployment.  

## 🛠️ Tools & Technologies
- **Wazuh 4.7.5** (Manager & Agent)  
- **Shuffle SOAR** – Orchestration & automation platform  
- **Windows 11** – Endpoint with Wazuh agent  
- **PowerShell / Batch scripting** – Custom active responses  
- **VirusTotal API** – Threat intelligence integration  



