# 🔐 Web Application Penetration Testing & Vulnerability Assessment

![Status](https://img.shields.io/badge/status-completed-brightgreen)
![Type](https://img.shields.io/badge/engagement-black--box-blue)
![Classification](https://img.shields.io/badge/classification-sanitized--for--portfolio-orange)

> A 5-day black-box web application penetration test and vulnerability assessment performed against a healthcare web application, conducted as part of the **NetworkWalks Cybersecurity Internship (Batch B084)**.
>
> ⚠️ **Note:** The client name, domain, and any identifying details have been withheld/generalized in this public repository, as the original report is classified Confidential. All methodology, findings, and recommendations below are presented as documented in the full assessment.

---

## 📋 Overview

This repository documents a practical web application security assessment covering reconnaissance, patient-portal inspection, PDF document password security testing, and exposed-backup analysis.

| | |
|---|---|
| **Assessment Type** | Web Application Security Assessment |
| **Engagement Model** | Black-box |
| **Duration** | 5 days |
| **OS Used** | Kali Linux |
| **Prepared By** | Christopher Ifeanyichukwu Stephen |
| **Program** | NetworkWalks Cybersecurity Internship, Batch B084 |

Full write-up: [`docs/full-report.md`](docs/full-report.md)

---

## 🎯 Objectives

- Identify publicly exposed services and information associated with the target domain
- Perform DNS reconnaissance and network enumeration
- Examine the web application for common security weaknesses
- Assess the patient portal's error-handling mechanisms
- Evaluate password protection of selected PDF documents
- Inspect publicly accessible directories and database backup files
- Document findings and provide remediation recommendations

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Testing OS |
| Nmap | Network scanning & service enumeration |
| DNSRecon / Nslookup / Dig | DNS reconnaissance |
| cURL | HTTP request/response inspection |
| WhatWeb | Technology fingerprinting |
| WAFW00F | WAF detection |
| John the Ripper | Password recovery testing |
| PDF hash utilities | Hash extraction from protected PDFs |

---

## 🧭 Methodology

The assessment was carried out in four phases:

1. **Reconnaissance & Network Enumeration** — DNS lookups, record analysis, port scanning, service detection
2. **Patient Portal Assessment** — error-handling review, dashboard/document access inspection
3. **PDF Document Password Security Testing** — hash generation + dictionary attacks on 3 protected documents
4. **Legacy Directory & SQL Backup Exposure** — public directory listing review, exposed backup analysis

Full phase-by-phase detail, screenshots, and evidence are in [`docs/full-report.md`](docs/full-report.md).

---

## 🚨 Summary of Findings

| ID | Finding | Severity |
|---|---|---|
| F-01 | Publicly Accessible SQL Backup | 🔴 Critical |
| F-02 | Weak / Recoverable PDF Passwords | 🟠 High |
| F-03 | Verbose PHP/MySQL Error Disclosure | 🟡 Medium |
| F-04 | Potential Patient Report Access-Control Risk | ⚪ Requires Further Validation |
| F-05 | Public Directory Listing | 🟠 High |
| F-06 | Exposed Network Services | ℹ️ Informational |

> Severity ratings are preliminary assessments based on observations made during testing; final severity would require controlled validation in a live engagement.

---

## ✅ Key Recommendations

- Remove publicly accessible database backups and store them outside the web root
- Disable directory indexing and clean up legacy files
- Enforce strong, unique passwords on confidential PDF documents
- Disable verbose error output in production; log errors server-side instead
- Implement/verify server-side access control on all document requests
- Use prepared statements to guard against SQL injection
- Establish continuous monitoring and periodic follow-up testing

Full recommendations: [`docs/full-report.md#9-general-security-recommendations`](docs/full-report.md)

---

## 📁 Repository Structure

```
.
├── README.md              # This file — project summary
├── docs/
│   └── full-report.md     # Full technical report (methodology, findings, threat analysis)
└── screenshots/
    └── README.md           # Evidence index (screenshots redacted/excluded from public repo)
```

---

## ⚖️ Ethics & Scope

This assessment was conducted under written client authorization, within an agreed scope and rules of engagement. No denial-of-service testing, social engineering, or out-of-scope systems were involved. All sensitive data (patient records, credentials, organizational information) encountered during testing has been excluded or redacted from this public repository.

---

## 👤 Author

**Christopher Ifeanyichukwu Stephen**
Cybersecurity Intern — NetworkWalks (Batch B084)
Undergraduate Computer Science Student, Hezekiah University

*Connect with me on [LinkedIn](#) for the full case-study post.*
