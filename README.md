# Task1-Network-scanning
# 🎯 Objective
To scan the local network for open TCP ports using Nmap and analyze potential security risks based on the findings.

# 🛠 Tools Used
Nmap v7.95 / v7.97
Operating Systems: Windows 10, Kali Linux (VirtualBox)
Terminal / Command Prompt
Optional: Wireshark (not used in this case)
# 🔄 Steps Performed
Installed Nmap on both Windows and Kali Linux systems.
Identified local IP addresses and subnet range.
Ran TCP SYN scan using nmap -sS <IP-range>.
Saved scan results as text files.
Took screenshots of scanning and setup.
Researched and analyzed open ports for potential vulnerabilities.
# 📊 Scan Results Summary
# 🖥️ Windows Host (10.145.94.123)
Port	Service	Description	Risk Level
| **Port** | **Service**    | **Description**                        | **Risk Level** | **Recommendation**                                                                    |
| -------- | -------------- | -------------------------------------- | -------------- | ------------------------------------------------------------------------------------- |
| **135**  | MSRPC          | Windows RPC – used for DCOM services   | ⚠️ Medium      | Restrict access via firewall; required for some Windows functions but often targeted. |
| **139**  | NetBIOS-SSN    | File/Printer sharing (legacy systems)  | ❌ High         | Disable if not needed; legacy protocol vulnerable to various exploits.                |
| **445**  | Microsoft-DS   | SMB over TCP (file sharing)            | ❌ High         | Block externally; patch regularly. Exploited by ransomware like WannaCry.             |
| **902**  | ISS RealSecure | VMware ESXi remote management          | ⚠️ Medium      | Disable if VMware is not in use; restrict access internally.                          |
| **912**  | Apex Mesh      | Used by VMware/other internal services | ⚠️ Medium      | Verify usage; restrict or disable if not required.                                    |

# 🐧 Kali Linux Host (10.145.94.21)
Port	Service	Description	Risk Level
53	DNS	Domain Name System	⚠️ Medium – Secure if properly configured
# 🖼️ Screenshots
All screenshots are available in the 'Screenshot for Windows' and 'Screenshot for Linux' folder:

Windows and Linux terminal scans
Nmap installation confirmation
IP range detection
# 📁 Files Included
scan_results_windows.txt – Full Nmap output from Windows
scan_results_kali.txt – Full Nmap output from Kali Linux
'Screenshot for Windows.pdf'
'Screenshot for Linux.pdf'
# ✅ Conclusion
This task helped identify live hosts and exposed ports within the local network. Ports like 445, 135, and 139 pose potential security risks and should be monitored or blocked if unnecessary.
