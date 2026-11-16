# 🔐 Web Application Security Testing

\<p align="center">   \<strong>ApexPlanet Cybersecurity Internship · Task 3\</strong>   \<br>   Practical Web Application Vulnerability Assessment & Security Testing \</p>

\<p align="center">   \<img src="[https://img.shields.io/badge/Domain-Web%20Application%20Security-blue?style=for-the-badge](https://img.shields.io/badge/Domain-Web%20Application%20Security-blue?style=for-the-badge)" alt="Domain">   \<img src="[https://img.shields.io/badge/Platform-OWASP%20Mutillidae%20II-orange?style=for-the-badge](https://img.shields.io/badge/Platform-OWASP%20Mutillidae%20II-orange?style=for-the-badge)" alt="Platform">   \<img src="[https://img.shields.io/badge/Tools-Burp%20Suite%20%7C%20Apache-red?style=for-the-badge](https://img.shields.io/badge/Tools-Burp%20Suite%20%7C%20Apache-red?style=for-the-badge)" alt="Tools">   \<img src="[https://img.shields.io/badge/Status-Completed-success?style=for-the-badge](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)" alt="Status"> \</p>

---

## 📌 Project Overview

This repository contains the practical implementation and documentation of **Task 3 – Web Application Security**, completed as part of the ApexPlanet Cybersecurity Internship.

The project focuses on understanding common web application vulnerabilities, analysing HTTP communication, performing controlled security testing, and exploring defensive security configurations.

Practical exercises were conducted primarily using **OWASP Mutillidae II** in a local testing environment, supported by Burp Suite and Apache.

The repository includes testing methodologies, observations, screenshots, vulnerability analysis, mitigation recommendations, and a demonstration script.

## 🎯 Objectives

- Understand common web application vulnerabilities, including SQL Injection, XSS, and CSRF.
- Intercept and analyse HTTP requests and responses using Burp Suite.
- Explore request replay and manual testing with Burp Repeater.
- Perform controlled input fuzzing using Burp Intruder.
- Explore advanced Burp Suite features for application traffic analysis.
- Understand HTTP security headers and their security benefits.
- Configure additional security headers in Apache.
- Document security observations, potential impacts, and mitigation techniques.
- Maintain practical evidence and technical documentation.

## 🛠️ Tools & Technologies

| Tool / Technology   | Purpose                                      |
| ------------------- | -------------------------------------------- |
| Kali Linux          | Security testing environment                 |
| OWASP Mutillidae II | Intentionally vulnerable web application     |
| Burp Suite          | HTTP interception and analysis               |
| Burp Repeater       | Manual HTTP request testing                  |
| Burp Intruder       | Automated payload testing                    |
| Apache              | Web server and security-header configuration |
| MariaDB             | Database service for the local lab           |
| Firefox             | Web application testing                      |
| Git & GitHub        | Version control and project documentation    |

## 📂 Repository Structure

```text
Web-Application-Security/
│
├── README.md
│
├── SQL-Injection/
│   ├── SQL-Injection-Report.md
│   └── SQL-Injection-Mitigation.txt
│
├── Burp-Suite/
│   └── Request-Interception.md
│
├── Intruder-Fuzzing/
│   └── Intruder-Testing.md
│
├── Advanced-Burp-Suite/
│   └── Advanced-Testing.md
│
├── Security-Headers/
│   ├── Header-Analysis.md
│   └── Apache-Configuration.md
│
├── XSS-and-CSRF/
│   └── XSS-CSRF-Testing.md
│
├── Security-Testing-Report/
│   └── Final-Report.md
│
├── Demo/
│   └── Demo-Script.md
│
└── Screenshots T3/
    ├── SQL-Injection/
    ├── Burp-Suite/
    ├── Intruder/
    ├── Advanced-Burp-Suite/
    ├── Security-Headers/
    └── XSS-CSRF/
```

## 🔍 Practical Activities

### 1. SQL Injection Testing

**Focus:** Understanding database-related vulnerabilities and insecure input handling.

Activities:

- Explored SQL Injection functionality in the local Mutillidae application.
- Inspected login and user lookup interfaces.
- Observed application responses to test inputs.
- Studied SQL Injection risks and preventive techniques.

**Testing outcome:** SQL Injection was explored, but successful exploitation was not conclusively verified.

Documentation: `SQL-Injection/`

### 2. Burp Suite – HTTP Request Analysis

**Focus:** Understanding communication between a browser and a web application.

Activities:

- Intercepted HTTP requests using Burp Proxy.
- Inspected captured request parameters and headers.
- Forwarded requests to Burp Repeater.
- Examined request and response information.

**Testing outcome:** Request interception and Repeater analysis were performed. Successful request modification was not confirmed.

Documentation: `Burp-Suite/`

### 3. Intruder – Input Fuzzing

**Focus:** Exploring automated payload testing.

Activities:

- Configured payload positions.
- Added payload lists.
- Executed an Intruder attack.
- Analysed response information, including status codes and response lengths.

Documentation: `Intruder-Fuzzing/`

### 4. Advanced Burp Suite

**Focus:** Application mapping and HTTP traffic analysis.

Features explored:

- **Site Map:** Examined application structure and available endpoints.
- **HTTP History:** Reviewed browser-generated HTTP requests.
- **Request/Response Analysis:** Inspected application communication.

Documentation: `Advanced-Burp-Suite/`

### 5. HTTP Security Headers & Apache Configuration

**Focus:** Understanding and configuring browser security-related HTTP headers.

Activities:

- Explored HTTP security-header analysis.
- Enabled Apache's `mod_headers` module.
- Added security-header directives to the Apache configuration.
- Validated the Apache configuration and restarted the service.

Headers configured:

| Header                 | Security Purpose                      |
| ---------------------- | ------------------------------------- |
| X-Content-Type-Options | Helps prevent MIME-type sniffing      |
| X-Frame-Options        | Helps protect against clickjacking    |
| Referrer-Policy        | Controls referrer information sharing |
| Permissions-Policy     | Restricts selected browser features   |

**Testing outcome:** Apache configuration validation succeeded. Actual response-header verification is documented as pending.

Documentation: `Security-Headers/`

### 6. Cross-Site Scripting (XSS) & CSRF

**Focus:** Understanding client-side script injection and request-forgery risks.

**Reflected XSS**

- Tested the Echo Message functionality.
- Submitted a JavaScript test payload.
- Observed JavaScript alert execution.

**Stored XSS**

- Tested the Add to Your Blog functionality.
- Submitted a JavaScript test payload.
- Confirmed that the alert appeared again after refreshing the page.

**CSRF**

- Explored the Add Your Blog functionality under the CSRF section.
- Captured the application request for inspection.
- Detailed token analysis and exploitation were not completed.

**Testing outcome:** Reflected and Stored XSS were successfully demonstrated. CSRF testing remained inconclusive.

Documentation: `XSS-and-CSRF/`

## 🛡️ Vulnerability Mitigation

| Vulnerability | Recommended Security Measures                                    |
| ------------- | ---------------------------------------------------------------- |
| SQL Injection | Prepared statements, parameterized queries, input validation     |
| Reflected XSS | Context-aware output encoding and input validation               |
| Stored XSS    | Safe output rendering, sanitization, and Content Security Policy |
| CSRF          | Anti-CSRF tokens and secure SameSite cookie attributes           |
| Clickjacking  | Appropriate X-Frame-Options or CSP frame-ancestors policy        |
| MIME Sniffing | X-Content-Type-Options: nosniff                                  |

## 📸 Screenshots & Evidence

Practical screenshots are organised by testing category in the `Screenshots T3/` directory.

| Directory           | Evidence                                                            |
| ------------------- | ------------------------------------------------------------------- |
| SQL-Injection       | Mutillidae pages, login and user lookup testing                     |
| Burp-Suite          | Intercepted requests, Repeater requests and responses, HTTP History |
| Intruder            | Payload positions, payload lists, attack results                    |
| Advanced-Burp-Suite | Site Map and HTTP History                                           |
| Security-Headers    | Initial header analysis and Apache configuration                    |
| XSS-CSRF            | Echo Message, Reflected XSS and Stored XSS demonstrations           |

Each screenshot provides supporting evidence for the corresponding practical activity.

## 📄 Security Testing Report

The consolidated report is available at:

[`Security-Testing-Report/Final-Report.md`](Security-Testing-Report/Final-Report.md)

It includes:

- Testing objectives and methodology
- Vulnerability testing procedures
- Observations and outcomes
- Security impact
- Mitigation recommendations
- Overall testing summary

## 🎥 Video Demonstration

An approximately **8-minute practical demonstration** was recorded for this task.

The demonstration covers the local testing environment, XSS demonstrations, Burp Suite features, vulnerability-testing activities, and Apache security-header configuration.

*The video can be linked here when it is uploaded to an accessible hosting platform.*

## ⚖️ Ethical Testing Disclaimer

All security testing activities were performed in a controlled, authorised educational environment using intentionally vulnerable local applications.

This project is intended solely for cybersecurity education, practical skill development, vulnerability awareness, and defensive security learning.

No unauthorised testing against public websites or third-party systems was performed.

## 👩‍💻 Internship Information

| Detail                      | Information                              |
| --------------------------- | ---------------------------------------- |
| Internship Program          | ApexPlanet Cybersecurity Internship      |
| Task Number                 | Task 3                                   |
| Task Title                  | Web Application Security                 |
| Project Focus               | Web Application Vulnerability Assessment |
| Primary Testing Application | OWASP Mutillidae II                      |
| Documentation               | Markdown and GitHub                      |

---

\<p align="center">
&#x20; \<strong>Learning by Testing · Securing by Understanding\</strong>
&#x20; \<br>
&#x20; Web Application Security | Vulnerability Assessment | Defensive Security
\</p>
