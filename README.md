# 🔍 Advanced Bug Bounty Reconnaissance Script

**Version:** 4.0  
**License:** For educational use only. Run on systems you have explicit permission to test.

---

## 📌 Overview

`recon_script1_Final.py` is a powerful and modular bug bounty reconnaissance automation script designed for ethical hackers, penetration testers, and bug bounty hunters. It performs **both passive and active reconnaissance** on a target domain and generates a detailed Markdown report.

---

## 🛠 Features

- ✅ WHOIS Information Gathering  
- ✅ DNS Record Enumeration (A, MX, TXT, NS, etc.)  
- ✅ HTTP Header & Security Header Extraction  
- ✅ Basic Port Scanning (Multithreaded)  
- ✅ Directory Brute Forcing (with customizable wordlists)  
- ✅ Subdomain Enumeration via `subfinder`, `assetfinder`, `amass`  
- ✅ Live Host Detection with `httpx`  
- ✅ Active Recon with `nmap`, `naabu`, `nikto`, `nuclei`, and `ffuf`  
- ✅ Wayback Machine & Sensitive File Discovery  
- ✅ Auto-generated Markdown Summary Report  

---

## 🧰 Requirements

### 🔧 Python 3 Dependencies

Install with:

```bash
pip install -r requirements.txt
```
### Requirements:

- requests
- python-whois
- dnspython
- termcolor

## 🧪 External Tools (optional but highly recommended)

#### Ensure these tools are installed and in your $PATH:

- subfinder
- assetfinder
- amass
- httpx
- naabu
- nmap
- nikto
- nuclei
- ffuf
- waybackurls
- whois
- dig

## 🚀 Usage
```bash
python3 recon.py -t https://example.com
```

## 🔘 Options
| Flag                | Description                                        |
| ------------------- | -------------------------------------------------- |
| `-t, --target`      | Target URL (required), e.g., `https://example.com` |
| `-o, --output`      | Custom output directory name                       |
| `--no-active`       | Skip all active scans (ports, directories, etc.)   |
| `--config`          | Path to a JSON config file to override defaults    |
| `--skip-tool-check` | Skip verification of external tool availability    |

## ⚙️ Sample JSON Config
```json
{
  "ports": [80, 443, 8080],
  "directory_wordlists": ["wordlists/common.txt"],
  "active_threads": {
    "port_scan": 30,
    "directory_discovery": 75
  }
}
```

## 📁 Output

```php
recon_<domain>_<YYYY-MM-DD_HH-MM>/
├── dns_external.txt
├── live.txt
├── nuclei.txt
├── nikto_<host>.txt
├── subdomains.txt
├── wayback.txt
├── interesting.txt
├── recon.log
└── summary_report.md
```

## 📓 Report Sample
A `summary_report.md` is generated at the end of the scan, providing:

- Domain details
- Subdomain and live host counts
- Vulnerability summary (Nuclei, Nikto)
- Interesting Wayback URLs
- Full file index

> ⚠️ Disclaimer:
This tool is for educational and authorized security testing purposes only. Ensure you have explicit permission to run scans on any target.

## 🤝 Contributions
Suggestions and improvements welcome! Feel free to fork and enhance.

📄 License
MIT License (For educational use; do not use on unauthorized targets.)
