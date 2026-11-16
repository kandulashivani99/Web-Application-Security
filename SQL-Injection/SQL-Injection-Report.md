\# 💉 SQL Injection Testing Report



\## 📌 Objective

To understand SQL Injection vulnerabilities, perform controlled testing against OWASP Mutillidae II, observe application responses, and identify appropriate mitigation techniques.



\## 🛠️ Testing Environment



| Component | Details |

|---|---|

| Operating System | Kali Linux |

| Target Application | OWASP Mutillidae II |

| Application Version | 2.12.5 |

| Testing Tool | Firefox |

| Vulnerability | SQL Injection |

| Environment | Local vulnerable web application |



\## 🔍 Testing Methodology



1\. Accessed the SQL Injection testing page in Mutillidae II.

2\. Submitted normal login credentials to establish baseline behavior.

3\. Tested application input handling using a single-quote character.

4\. Observed application responses and potential database errors.

5\. Evaluated the security implications of unsafe SQL query construction.

6\. Identified appropriate SQL Injection mitigation techniques.



\## 📊 Observations



| Test | Input | Result |

|---|---|---|

| Normal Login | Invalid credentials | To be documented |

| Input Handling | Single quote | To be documented |



\## ⚠️ Security Impact



SQL Injection can allow an attacker to interfere with database queries through improperly handled user input.



Potential impacts include:

\- Unauthorized authentication.

\- Unauthorized access to database records.

\- Data modification or deletion.

\- Exposure of sensitive information.



\## 🛡️ Recommended Mitigation



\- Use parameterized queries and prepared statements.

\- Avoid constructing SQL queries through string concatenation.

\- Implement server-side input validation.

\- Apply least-privilege database permissions.

\- Disable detailed database error messages in production.

\- Conduct regular security testing.



\## 📸 Evidence



Screenshots are stored in the `screenshots` directory.



\## 📝 Conclusion



The exercise demonstrates the importance of secure database query handling and proper input validation. SQL Injection risks can be significantly reduced through parameterized queries, secure database permissions, and appropriate error handling.





