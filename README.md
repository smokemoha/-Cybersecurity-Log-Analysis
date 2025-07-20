# 🛡️ Cybersecurity Log Analysis: Web Activity Incident Investigation

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Key Findings](#key-findings)
- [Analysis Methodology](#analysis-methodology)
- [Tools & Technologies](#tools--technologies)
- [How to View the Report](#how-to-view-the-report)
- [Screenshots & Evidence](#screenshots--evidence)
- [Contact](#contact)

## Overview

This repository contains a detailed cybersecurity analysis of `web_requests.log`, focusing on identifying suspicious activities and potential security vulnerabilities. The investigation uncovered a critical insight into automated process behavior and session management within the network.

## Project Structure

deloitte-cybersecurity-analysis/
├── web_requests.log # Original web activity log file analyzed
├── report/ # Contains the detailed cybersecurity analysis report
│ └── cybersecurity_analysis_report.md
├── screenshots/ # Directory for all evidential screenshots
│ ├── 01_initial_401_search.png
│ ├── 02_ip_identification.png
│ ├── 03_suspicious_ip_activity.png
│ ├── 04_normal_user_comparison.png
│ └── 05_all_unique_ips.png
└── README.md # Project overview and documentation (this file)

## Key Findings

Through meticulous log analysis, the primary finding is related to an automated process (associated with `authorizedUserId: "mdB7yD2dp1BFZPontHBQ1Z"`) originating from IP address `192.168.0.101`. This process experienced prolonged authentication failures (64 consecutive `401 (UNAUTHORIZED)` responses) over a 16-hour period due to an expired session token. This highlights a potential vulnerability in session management for automated tasks, leading to unnecessary resource consumption and potential alert fatigue.

**Risk Level:** Medium
**Recommendation:** Implement robust session management for automated processes, including token refresh mechanisms or dedicated service accounts with non-expiring credentials.

## Analysis Methodology

The analysis was conducted using a systematic approach, leveraging powerful command-line tools available in Kali Linux:

1.  **Log File Examination**: Initial review of `web_requests.log` structure and volume.
2.  **Unauthorized Access Detection**: Identification and quantification of `401 (UNAUTHORIZED)` errors.
3.  **Source IP Identification**: Tracing suspicious user IDs to their originating IP addresses.
4.  **Behavioral Analysis**: In-depth examination of the suspicious IP's activity timeline.
5.  **Comparative Analysis**: Contrasting suspicious behavior with normal user patterns across different IPs.
6.  **Reporting**: Documenting findings, impact, and recommendations in a professional report.

## Tools & Technologies

- **Operating System**: Kali Linux
- **Log Analysis**: `grep`, `awk`, `sed`, `sort`, `uniq`, `wc`, `head`
- **Version Control**: Git
- **Documentation**: Markdown
- **Screenshot Utility**: `gnome-screenshot` (or `scrot`)

```bash
git clone  https://github.com/smokemoha/-Cybersecurity-Log-Analysis

```

## How to View the Report

For a detailed breakdown of the analysis, findings, and recommendations, please refer to the main report:

➡️ [**View the Full Cybersecurity Analysis Report**](report/cybersecurity_analysis_report.md)

## Screenshots & Evidence

Key visual evidence supporting the analysis is provided in the `screenshots/` directory and linked within the main report. These include:

- [Initial 401 Error Search Output](screenshots/01_initial_401_search.png)
- [Suspicious IP Identification Command Output](screenshots/02_ip_identification.png)
- [Full Activity Log for 192.168.0.101](screenshots/03_suspicious_ip_activity.png)
- [Comparison with Normal User Activity (192.168.0.102)](screenshots/04_normal_user_comparison.png)
- [List of All Unique IP Addresses in Logs](screenshots/05_all_unique_ips.png)

## Contact

For any questions or further discussion, please open an issue on this repository.

---

_This project was completed as part of a cybersecurity challenge/learning exercise._
