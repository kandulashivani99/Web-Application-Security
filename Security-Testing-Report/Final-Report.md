\# WEB APPLICATION SECURITY TESTING REPORT



\## Task 3 – Web Application Security



\*\*Name:\*\* Shivani Kandula  

\*\*Project:\*\* ApexPlanet Cybersecurity Internship – Task 3  

\*\*Testing Environment:\*\* OWASP Mutillidae II (Local Lab)  

\*\*Tools Used:\*\* Burp Suite, OWASP Mutillidae II, Apache, Kali Linux, Web Browser  

\*\*Date:\*\* 15 November 2026



\---



\## 1. Introduction



Web application security testing is the process of identifying vulnerabilities that could allow attackers to access sensitive information, manipulate application data, or execute unauthorized actions.



This task focused on understanding common web application vulnerabilities and practising security testing techniques in a controlled local environment. The activities included SQL Injection testing, Cross-Site Scripting (XSS), request interception, Intruder fuzzing, advanced Burp Suite analysis, and HTTP security-header configuration.



\## 2. Objectives



\- Understand common web application vulnerabilities.

\- Practise intercepting and analysing HTTP requests.

\- Explore SQL Injection testing techniques.

\- Demonstrate Reflected and Stored Cross-Site Scripting.

\- Perform basic fuzzing using Burp Suite Intruder.

\- Analyse application endpoints and HTTP history.

\- Configure security headers in Apache.

\- Document observations, potential impacts, and mitigation techniques.



\## 3. Testing Environment and Tools



| Component | Description |

|---|---|

| Operating System | Kali Linux / Windows |

| Vulnerable Application | OWASP Mutillidae II |

| Proxy and Testing Tool | Burp Suite |

| Web Server | Apache |

| Database Service | MariaDB |

| Browser | Burp Suite Embedded Browser / Web Browser |



All vulnerability testing was performed against the local training application.



\## 4. SQL Injection Testing



\### 4.1 Objective



To understand how SQL Injection vulnerabilities can occur when an application uses untrusted input in database queries without appropriate validation or parameterisation.



\### 4.2 Testing Procedure



1\. Opened the local OWASP Mutillidae II application.

2\. Navigated to the SQL Injection testing section.

3\. Inspected the available input fields.

4\. Explored how user-supplied input could affect application behaviour.



\### 4.3 Observation



SQL Injection testing was explored in the local application. However, a successful SQL Injection exploit was not conclusively verified during the practical session.



\### 4.4 Mitigation



\- Use parameterised queries and prepared statements.

\- Validate input on the server side.

\- Apply least-privilege database permissions.

\- Avoid constructing SQL queries through direct string concatenation.

\- Use secure error handling to prevent database details from being exposed.



\## 5. Cross-Site Scripting (XSS) Testing



\### 5.1 Reflected XSS



\*\*Objective:\*\* To check whether user-supplied input is reflected by the application and executed as JavaScript in the browser.



\*\*Testing Location:\*\* Mutillidae – OWASP 2017 – A7 Cross-Site Scripting – Reflected (First Order) – Echo Message.



\*\*Payload Used:\*\*



```html

<script>alert('XSS Test')</script>

```



\*\*Observation:\*\* After submitting the payload, the browser displayed a JavaScript alert containing the message "XSS Test".



\*\*Result:\*\* Reflected XSS was successfully demonstrated in the local training application.



\*\*Impact:\*\* Malicious JavaScript may execute in a victim's browser when an application reflects untrusted input without appropriate output encoding.



\### 5.2 Stored XSS



\*\*Objective:\*\* To test whether an application stores malicious input and executes it when the stored content is displayed.



\*\*Testing Location:\*\* Mutillidae – OWASP 2017 – A7 Cross-Site Scripting – Persistent (Second Order) – Add to Your Blog.



\*\*Payload Used:\*\*



```html

<script>alert('Stored XSS Test')</script>

```



\*\*Observation:\*\* The JavaScript alert appeared after submitting the blog entry. The alert appeared again after refreshing the page, indicating that the payload remained stored and was executed when the content was displayed.



\*\*Result:\*\* Stored XSS was successfully demonstrated in the local training application.



\*\*Impact:\*\* Stored malicious scripts may execute in the browsers of users who view the affected content, potentially enabling session-related attacks or unauthorised actions.



\### 5.3 XSS Mitigation



\- Apply context-aware output encoding.

\- Validate and sanitise untrusted input.

\- Implement a restrictive Content Security Policy (CSP).

\- Avoid inserting untrusted content into executable HTML or JavaScript contexts.

\- Use secure frameworks and safe rendering methods.



\## 6. Cross-Site Request Forgery (CSRF) Testing



\### 6.1 Objective



To understand how Cross-Site Request Forgery can cause an authenticated user's browser to submit an unwanted request to an application.



\### 6.2 Testing Procedure



1\. Navigated to the CSRF section in Mutillidae.

2\. Opened the Add Your Blog functionality.

3\. Entered harmless test content.

4\. Attempted to inspect the generated HTTP request through Burp Suite Proxy.



\### 6.3 Observation



The application request was captured for inspection. However, detailed CSRF token analysis and a complete CSRF exploitation test were not performed.



\*\*Result:\*\* CSRF testing was partially explored but remains inconclusive. No CSRF vulnerability is claimed.



\### 6.4 Mitigation



\- Implement anti-CSRF tokens.

\- Validate request origin using Origin and Referer headers where appropriate.

\- Configure secure SameSite cookie attributes.

\- Require re-authentication or additional verification for sensitive operations.

\- Avoid relying only on client-side validation.



\## 7. Burp Suite Request Interception and Repeater



\### 7.1 Objective



To understand how HTTP requests can be intercepted, inspected, and manually tested.



\### 7.2 Activities Performed



\- Configured Burp Suite Proxy interception.

\- Captured HTTP requests generated by the local web application.

\- Forwarded a captured request to Repeater.

\- Inspected the request and its corresponding response.

\- Explored the request-response workflow.



\### 7.3 Observation



Burp Suite provided visibility into HTTP communication between the browser and the application. The Repeater tool allowed the captured request to be sent again for further analysis. Successful request modification was not confirmed.



\## 8. Burp Suite Intruder Fuzzing



\### 8.1 Objective



To understand how automated payload testing can help identify unexpected application responses.



\### 8.2 Activities Performed



\- Selected an HTTP request for Intruder testing.

\- Configured payload positions.

\- Added a payload list.

\- Started the Intruder attack.

\- Inspected the generated attack results and response information.



\### 8.3 Observation



Intruder generated multiple requests using the configured payloads. The response information was inspected to understand how an application may respond to different inputs.



\## 9. Advanced Burp Suite Analysis



The following advanced features were explored:



\*\*Site Map:\*\* Inspected the application structure and identified available application endpoints.



\*\*HTTP History:\*\* Reviewed requests and responses generated during application interaction.



\*\*Request and Response Analysis:\*\* Examined HTTP communication to understand the information exchanged between the browser and the application.



These features helped improve understanding of application mapping and HTTP traffic analysis.



\## 10. HTTP Security Headers and Apache Configuration



\### 10.1 Objective



To configure additional HTTP security headers in Apache to improve browser-side security protections.



\### 10.2 Configuration



Enabled the Apache headers module:



```bash

sudo a2enmod headers

```



Added the following configuration to the Apache security configuration:



```apache

<IfModule mod\_headers.c>

&#x20;   Header always set X-Content-Type-Options "nosniff"

&#x20;   Header always set X-Frame-Options "SAMEORIGIN"

&#x20;   Header always set Referrer-Policy "strict-origin-when-cross-origin"

&#x20;   Header always set Permissions-Policy "geolocation=(), microphone=(), camera=()"

</IfModule>

```



\### 10.3 Configuration Validation



Executed:



```bash

sudo apache2ctl configtest

sudo systemctl restart apache2

sudo systemctl status apache2

```



\*\*Observation:\*\* Apache configuration validation reported that the syntax was OK, and the Apache service was confirmed running after the configuration change.



The actual HTTP response headers still require verification using:



```bash

curl -I http://localhost/mutillidae/

```



\### 10.4 Purpose of Configured Headers



| Header | Security Purpose |

|---|---|

| X-Content-Type-Options | Helps prevent MIME-type sniffing. |

| X-Frame-Options | Restricts framing to help mitigate clickjacking. |

| Referrer-Policy | Controls how much referrer information is shared. |

| Permissions-Policy | Restricts access to selected browser features. |



\## 11. Summary of Testing Results



| Test / Activity | Result |

|---|---|

| SQL Injection | Explored; successful exploitation not confirmed |

| Reflected XSS | Successfully demonstrated |

| Stored XSS | Successfully demonstrated |

| CSRF | Partially explored; inconclusive |

| Burp Proxy Interception | Performed |

| Burp Repeater | Request replay and response inspection performed |

| Burp Intruder | Payload testing performed |

| Advanced Burp Suite | Site Map and HTTP History explored |

| Apache Security Headers | Configuration added and Apache validation passed |

| HTTP Header Verification | Pending response-header verification |

| SecurityHeaders.com Online Scan | Not completed |



\## 12. Recommendations



1\. Use prepared statements to prevent SQL Injection.

2\. Apply context-aware output encoding to prevent XSS.

3\. Implement anti-CSRF tokens and secure cookie attributes.

4\. Validate and sanitise user input on the server side.

5\. Configure and verify appropriate HTTP security headers.

6\. Perform regular vulnerability assessments and security testing.

7\. Monitor application logs for unusual requests and suspicious activity.



\## 13. Conclusion



This task provided practical exposure to web application security testing using OWASP Mutillidae II and Burp Suite. Reflected and Stored XSS were successfully demonstrated in the local training environment. Burp Suite was used for request interception, Repeater analysis, Intruder fuzzing, and application mapping.



Apache security headers were configured, and the configuration was validated successfully. SQL Injection and CSRF activities were explored, but successful exploitation was not established. The exercise improved understanding of common web vulnerabilities, HTTP request analysis, defensive configurations, and security testing documentation.



\*\*Note:\*\* All activities were conducted in a controlled local lab environment for educational purposes.

