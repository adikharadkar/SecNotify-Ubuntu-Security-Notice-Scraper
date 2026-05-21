# SecNotify — Ubuntu Security Notice Scraper

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-4-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

A Python script that automates the extraction of security vulnerability data from Ubuntu's official Security Notices webpage — eliminating the need for manual monitoring of security advisories.

---

## 📌 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Data Extracted](#data-extracted)
- [Getting Started](#getting-started)
- [Logging](#logging)
- [Roadmap](#roadmap)
- [License](#license)

---

## 📖 About the Project

SecNotify scrapes the live [Ubuntu Security Notices](https://ubuntu.com/security/notices) webpage and extracts structured vulnerability data including notice names, affected Ubuntu releases, package details, CVE IDs, and advisory links. All output is logged to a dedicated log file for traceability and downstream processing.

---

## ✨ Features

- 🔍 **Live Scraping** — Fetches real-time data directly from Ubuntu's official security notices page
- 🗂️ **Structured Data Extraction** — Parses and organises notice names, release versions, packages, CVE IDs, and advisory links
- 📚 **Ubuntu Version Mapping** — Builds a dictionary of affected Ubuntu release names mapped to their advisory links
- 🔐 **CVE ID Mapping** — Extracts all CVE identifiers and their corresponding links into a structured dictionary
- 📝 **Logging Pipeline** — Records all extracted data and execution events to a `scraper.log` file with timestamps and log levels
- 🛡️ **Robust Error Handling** — Gracefully handles missing elements and parsing failures at every extraction step

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `requests` | HTTP requests to fetch live webpage content |
| `BeautifulSoup (bs4)` | HTML parsing and structured data extraction |
| `logging` | File-based logging of output and execution events |
| `lxml` | High-performance HTML parser used with BeautifulSoup |

---

## 📊 Data Extracted

The script extracts and organises the following data from each security notice:

| Field | Description |
|---|---|
| **Notice Name** | Title of the security advisory |
| **Advisory Link** | Direct URL to the full security notice |
| **Date** | Publication date of the notice |
| **Summary** | Brief description of the vulnerability |
| **Ubuntu Versions** | Affected release names mapped to their links |
| **CVE IDs** | All associated CVE identifiers mapped to their links |

All data is stored in structured Python lists and dictionaries and logged to `scraper.log`.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip

### 1. Clone the Repository

```bash
git clone https://github.com/adikharadkar/Python-Web-Scraper.git
cd Python-Web-Scraper
```

### 2. Install Dependencies

```bash
pip install requests beautifulsoup4 lxml
```

### 3. Run the Scraper

```bash
python scraper.py
```

### 4. View the Output

All extracted data is logged to `scraper.log` in the same directory:

```bash
cat scraper.log
```

---

## 📋 Logging

The script uses Python's built-in `logging` module with the following configuration:

| Setting | Value |
|---|---|
| Log Level | `DEBUG` |
| Log File | `scraper.log` |
| Format | `%(asctime)s %(levelname)s %(message)s` |
| Handlers | File handler (timestamped entries) |

Sample log output:
```
2023-10-01 12:00:01 INFO ['USN-XXXX-1', '/security/notices/USN-XXXX-1', 'October 2023', 'Summary text...']
2023-10-01 12:00:01 INFO UBUNTU VERSION - {'Ubuntu 22.04 LTS': '/security/notices/...'}
2023-10-01 12:00:01 INFO CVE IDs: {'CVE-2023-XXXX': 'https://ubuntu.com/security/CVE-2023-XXXX'}
```

---

## 🗺️ Roadmap

- [x] Scrape latest security notices from Ubuntu's official page
- [x] Extract notice names, dates, summaries, and advisory links
- [x] Map affected Ubuntu versions to their advisory links
- [x] Map CVE IDs to their respective links
- [x] Log all output and errors to a structured log file
- [ ] Export extracted data to CSV or JSON format
- [ ] Add support for paginated scraping across multiple notice pages
- [ ] Schedule automated runs via cron job
- [ ] Add email or Slack alerts for newly published CVEs

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 🙋‍♂️ Author

**Aditya Kharadkar**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)]([https://www.linkedin.com/in/your-profile](https://www.linkedin.com/in/aditya-kharadkar-6352ba174/))
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/adikharadkar)
