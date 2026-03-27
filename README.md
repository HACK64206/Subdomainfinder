<div align="center">

# 🔍 Subdomain Finder

### *Advanced Subdomain Discovery & Reconnaissance Framework*

[![Python Version](https://img.shields.io/badge/python-3.7+-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-linux%20%7C%20macos%20%7C%20windows%20%7C%20android-lightgrey.svg)]()
[![Status](https://img.shields.io/badge/status-stable-brightgreen.svg)]()

</div>

---

## 📖 Overview

**Subdomain Finder** is a high-performance reconnaissance tool for bug bounty hunters that discovers subdomains by aggregating 8+ public APIs, performing DNS resolution, and probing live endpoints. Multi-threaded with color-coded output, it generates JSON reports and helps map attack surfaces efficiently.

---

## ✨ Features

| Category | Features |
|----------|----------|
| **Data Sources** | crt.sh, AlienVault OTX, CertSpotter, BufferOver, ThreatCrowd, AnubisDB, HackerTarget, Wayback Machine |
| **Performance** | Multi-threaded architecture, configurable thread count (up to 100), asynchronous API requests |
| **Analysis** | DNS resolution, HTTP/HTTPS probing, response time tracking, title extraction, interesting endpoint detection |
| **Output** | JSON exports, text lists, colored terminal output, structured reports |
| **Usability** | Simple CLI, progress indicators, error handling, graceful interrupt support |

---

## 🚀 Quick Start Guide

### Step 1: Prerequisites

Ensure you have Python 3.7+ installed:

```bash
python3 --version
```

Step 2: Clone the Repository

```bash
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder
```

Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

Step 4: Run Your First Scan

```bash
python subdomain_finder.py -d example.com
```

---

📋 Platform-Specific Installation & Usage

🐧 Linux (Kali Linux, Ubuntu, Debian, Parrot OS)

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Python and pip if not installed
sudo apt install python3 python3-pip git -y

# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install requirements
pip3 install -r requirements.txt

# Make executable
chmod +x subdomain_finder.py

# Run scan on www.example.com
python3 subdomain_finder.py -d www.example.com

# Save results to custom directory
python3 subdomain_finder.py -d www.example.com -o ./results

# High-speed scan with 100 threads
python3 subdomain_finder.py -d www.example.com -t 100

# Full scan with all options
python3 subdomain_finder.py -d www.example.com -t 100 -o kiran_scan
```

🎯 Kali Linux Specific

```bash
# Install from repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install dependencies
sudo apt install python3-pip -y
pip3 install -r requirements.txt

# Run scan
python3 subdomain_finder.py -d www.example.com

# View results
cat mr_kiran_output/subdomains.txt
```

🐉 BlackArch Linux

```bash
# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install dependencies
sudo pacman -S python-pip
pip install -r requirements.txt

# Run scan
python subdomain_finder.py -d www.example.com

# Save results
python subdomain_finder.py -d www.example.com -o blackarch_results
```

📱 Termux (Android)

```bash
# Update Termux packages
pkg update && pkg upgrade -y

# Install required packages
pkg install python git -y

# Install pip
pkg install python-pip

# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install requirements
pip install -r requirements.txt

# Run scan on www.example.com
python subdomain_finder.py -d www.example.com

# Save results to internal storage
python subdomain_finder.py -d www.example.com -o /sdcard/subdomain_results

# High-speed scan
python subdomain_finder.py -d www.example.com -t 100

# View results in Termux
cat mr_kiran_output/subdomains.txt

# Copy results to internal storage for easy access
cp -r mr_kiran_output /sdcard/
```

🪟 Windows (CMD & PowerShell)

Command Prompt (CMD)

```cmd
# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install Python dependencies
pip install -r requirements.txt

# Run scan on www.example.com
python subdomain_finder.py -d www.example.com

# Save results to specific folder
python subdomain_finder.py -d www.example.com -o C:\Users\YourName\Desktop\results

# Scan with custom threads
python subdomain_finder.py -d www.example.com -t 100

# View results
type mr_kiran_output\subdomains.txt
```

PowerShell

```powershell
# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install requirements
pip install -r requirements.txt

# Run scan
python subdomain_finder.py -d www.example.com

# Save to custom location
python subdomain_finder.py -d www.example.com -o "$env:USERPROFILE\Desktop\subdomain_results"

# High-performance scan
python subdomain_finder.py -d www.example.com -t 100

# View results
Get-Content .\mr_kiran_output\subdomains.txt

# Export results to CSV format (using PowerShell)
Get-Content .\mr_kiran_output\subdomains.txt | Export-Csv -Path results.csv
```

🍎 macOS

```bash
# Install Homebrew if not installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Python and git
brew install python git

# Clone repository
git clone https://github.com/HACK64206/Subdomainfinder.git
cd Subdomainfinder

# Install requirements
pip3 install -r requirements.txt

# Run scan
python3 subdomain_finder.py -d www.example.com

# Save results
python3 subdomain_finder.py -d www.example.com -o ~/Desktop/results
```

---

💡 Complete Usage Examples

Finding Subdomains for www.example.com

```bash
# Basic scan for www.example.com
python subdomain_finder.py -d www.example.com

# Scan with specific thread count
python subdomain_finder.py -d www.example.com -t 75

# Save results to specific directory
python subdomain_finder.py -d www.example.com -o example_com_scan

# Full scan with maximum performance
python subdomain_finder.py -d www.example.com -t 100 -o full_scan

# Scan multiple domains (using bash script)
for domain in example.com test.com demo.com; do
    python subdomain_finder.py -d $domain -o "${domain}_results"
done
```

Saving and Managing Results

```bash
# Save results to desktop (Linux/macOS)
python subdomain_finder.py -d www.example.com -o ~/Desktop/subdomain_results

# Save results to desktop (Windows CMD)
python subdomain_finder.py -d www.example.com -o C:\Users\%USERNAME%\Desktop\results

# Save results to desktop (Windows PowerShell)
python subdomain_finder.py -d www.example.com -o "$env:USERPROFILE\Desktop\results"

# Save results to SD card (Termux)
python subdomain_finder.py -d www.example.com -o /sdcard/subdomain_scan

# View discovered subdomains
cat mr_kiran_output/subdomains.txt

# Count discovered subdomains
wc -l mr_kiran_output/subdomains.txt

# Filter specific subdomains (e.g., admin, api)
grep -E "admin|api|dev|test" mr_kiran_output/subdomains.txt

# Export to CSV format
awk '{print $0}' mr_kiran_output/subdomains.txt > subdomains.csv

# Create timestamped results
python subdomain_finder.py -d www.example.com -o "scan_$(date +%Y%m%d_%H%M%S)"
```

---

🛠️ Requirements

Create a requirements.txt file with:

```txt
requests>=2.28.0
dnspython>=2.3.0
urllib3>=1.26.0
```

---

📊 Command Line Arguments

Argument Flag Description Default Example
Domain -d, --domain Target domain to scan Required -d example.com
Threads -t, --threads Number of concurrent threads 50 -t 100
Output -o, --output Output directory name mr_kiran_output -o results
Help -h, --help Show help message - -h

---

📁 Output Structure

After a successful scan, you'll find:

```
output_directory/
│
├── subdomains.txt          # 📝 All discovered subdomains (plain text)
├── resolved.json           # 🌐 Subdomains with IP addresses (JSON)
├── alive.json              # ✅ Live endpoints with metadata (JSON)
│
└── reports/                # 📊 Summary reports
    └── report.json         # Complete mission report
```

Output Files Explained

File Description
subdomains.txt Plain text list of all discovered subdomains (one per line)
resolved.json JSON file containing subdomains with their resolved IP addresses
alive.json Detailed information about live hosts including URL, status code, title, response time, IP
report.json Complete mission summary with statistics and top findings

---

📈 Sample Output for www.example.com

```bash
$ python subdomain_finder.py -d www.example.com -t 50

╔═══════════════════════════════════════════════════════════════════════════════╗
║   ███╗   ███╗██████╗     ██╗  ██╗██╗██████╗  █████╗ ███╗   ██╗                ║
║   ████╗ ████║██╔══██╗    ██║ ██╔╝██║██╔══██╗██╔══██╗████╗  ██║                ║
║   ██╔████╔██║██████╔╝    █████╔╝ ██║██████╔╝███████║██╔██╗ ██║                ║
║   ██║╚██╔╝██║██╔══██╗    ██╔═██╗ ██║██╔══██╗██╔══██║██║╚██╗██║                ║
║   ██║ ╚═╝ ██║██║  ██║    ██║  ██╗██║██║  ██║██║  ██║██║ ╚████║                ║
║   ╚═╝     ╚═╝╚═╝  ╚═╝    ╚═╝  ╚═╝╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝                ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║   ⚡ TARGET: www.example.com         ⚡ THREADS: 50                          ║
║   ⚡ START TIME: 14:32:15                                                    ║
╚═══════════════════════════════════════════════════════════════════════════════╝

[14:32:16] [✓] CRT.SH found 12 subdomains
[14:32:17] [✓] AlienVault found 8 subdomains
[14:32:18] [✓] CertSpotter found 15 subdomains
[14:32:19] [✓] Discovered 45 total subdomains!

════════════════════════════════════════════════════════════════════════════════
  PHASE 1: SUBDOMAIN ENUMERATION
════════════════════════════════════════════════════════════════════════════════

[14:32:16] [✓] CRT.SH found 12 subs
[14:32:17] [✓] AlienVault found 8 subs
[14:32:18] [✓] CertSpotter found 15 subs
[14:32:19] [👑] MR KIRAN discovered 45 subdomains!

════════════════════════════════════════════════════════════════════════════════
  PHASE 2: DNS RESOLUTION
════════════════════════════════════════════════════════════════════════════════

[14:32:20] Resolving 45 subdomains
[14:32:23] Resolved: 38/45

════════════════════════════════════════════════════════════════════════════════
  PHASE 3: HTTP PROBING
════════════════════════════════════════════════════════════════════════════════

[14:32:24] Probing 38 targets
[14:32:26] [⚠] Interesting: https://admin.example.com
[14:32:30] Alive hosts: 32

════════════════════════════════════════════════════════════════════════════════
  PHASE 4: GENERATING REPORT
════════════════════════════════════════════════════════════════════════════════

📊 Statistics:
   • Subdomains Found: 45
   • Resolved: 38
   • Live Hosts: 32
   • Runtime: 0:00:15

Top Targets:
  1. [200] https://www.example.com
  2. [200] https://mail.example.com
  3. [200] https://api.example.com
  4. [403] https://admin.example.com
  5. [200] https://blog.example.com

[✓] Report saved to mr_kiran_output/reports/

════════════════════════════════════════════════════════════════════════════════
  🏆 MISSION ACCOMPLISHED! 🏆
════════════════════════════════════════════════════════════════════════════════
```

---

🔍 View and Analyze Results

Linux/macOS/Termux

```bash
# View all subdomains
cat mr_kiran_output/subdomains.txt

# Count subdomains
wc -l mr_kiran_output/subdomains.txt

# Search for specific patterns
grep "admin" mr_kiran_output/subdomains.txt
grep "api" mr_kiran_output/subdomains.txt
grep "test" mr_kiran_output/subdomains.txt

# View alive hosts
cat mr_kiran_output/alive.json | python -m json.tool

# Extract only URLs from alive.json
grep -o '"url": "[^"]*"' mr_kiran_output/alive.json | cut -d'"' -f4
```

Windows CMD

```cmd
# View all subdomains
type mr_kiran_output\subdomains.txt

# Count subdomains (using find)
find /c /v "" mr_kiran_output\subdomains.txt

# Search for specific patterns
find "admin" mr_kiran_output\subdomains.txt
find "api" mr_kiran_output\subdomains.txt
```

Windows PowerShell

```powershell
# View all subdomains
Get-Content .\mr_kiran_output\subdomains.txt

# Count subdomains
(Get-Content .\mr_kiran_output\subdomains.txt).Count

# Search for patterns
Select-String -Path .\mr_kiran_output\subdomains.txt -Pattern "admin|api|test"

# Export to CSV
Get-Content .\mr_kiran_output\subdomains.txt | Export-Csv -Path subdomains.csv -NoTypeInformation
```

---

⚠️ Important Legal Notice

<div align="center">

Icon Notice
⚠️ This tool is for authorized security testing only
🔒 Only scan domains you own or have explicit written permission to test
⚖️ Unauthorized scanning may violate laws and terms of service
📝 Always obtain proper authorization before conducting security assessments

</div>

By using this tool, you agree that:

· You will only use it against systems you own or have permission to test
· The author assumes no liability for misuse or damage caused by this tool
· You are responsible for complying with all applicable laws and regulations

---

🚧 Roadmap & Future Enhancements

Priority Feature Status
High Custom wordlist support 🔜 Planned
High Proxy configuration (HTTP/SOCKS) 🔜 Planned
High Wildcard detection and filtering 🔜 Planned
Medium Screenshot capture of live hosts 📅 Roadmap
Medium Port scanning integration 📅 Roadmap
Medium CSV export option 📅 Roadmap
Low Web dashboard for visualization 🎯 Future
Low Machine learning-based subdomain prediction 🎯 Future

---

🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Commit changes:
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. Push to branch:
   ```bash
   git push origin feature/amazing-feature
   ```
5. Open a Pull Request

Contribution Guidelines

· Follow PEP 8 style guidelines
· Add comments for complex logic
· Update documentation for new features
· Test thoroughly before submitting

---

📞 Support

Resource Link
📧 Issues GitHub Issues
💬 Discussions GitHub Discussions
📖 Documentation Wiki

---

🙏 Acknowledgments

· All the public APIs that make this tool possible
· The bug bounty and security research community
· Open source contributors

---

📄 License

Distributed under the MIT License. See LICENSE for more information.

---

<div align="center">

⭐ Star this repository if you find it useful!

Built with ❤️ for the security community

</div>