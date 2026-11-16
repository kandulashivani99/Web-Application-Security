# Task 3 – Web Application Security

## 8-Minute Video Demonstration Script



\*\*Duration:\*\* Approximately 8 minutes  

\*\*Application:\*\* OWASP Mutillidae II  

\*\*Tools:\*\* Burp Suite, Apache, Kali Linux



### 0:00–0:45 | Introduction



"Hello, this is my demonstration for Task 3 – Web Application Security, completed as part of the ApexPlanet Cybersecurity Internship.



In this task, I explored common web application vulnerabilities using OWASP Mutillidae II and performed HTTP traffic analysis using Burp Suite. I also configured security headers in Apache."



### 0:45–1:30 | Testing Environment



\- Show the Mutillidae application in the browser.

\- Show the local application URL.

\- Briefly introduce the testing environment and tools.



"All vulnerability testing was conducted in a controlled local lab environment."



### 1:30–2:30 | Reflected XSS



\- Navigate to the Echo Message functionality.

\- Show the reflected XSS payload used.

\- Demonstrate the JavaScript alert if the lab is still available.



"The application reflected the submitted input without appropriate output encoding, allowing JavaScript execution in the browser."



### 2:30–3:30 | Stored XSS



\- Navigate to Add to Your Blog under Persistent XSS.

\- Show the stored payload.

\- Refresh the page and demonstrate that the alert appears again.



"This demonstrated Stored XSS because the submitted payload remained in the application and executed again when the stored content was displayed."



### 3:30–4:30 | Burp Suite



\- Show Proxy interception.

\- Show the captured request.

\- Open Repeater and show the request and response.

\- Briefly explain how Burp helps inspect HTTP communication.



### 4:30–5:15 | Intruder and Advanced Features



\- Show Intruder payload positions and attack results.

\- Show the Site Map and HTTP History.



"Intruder helps automate input testing, while Site Map and HTTP History provide visibility into application endpoints and requests."



### 5:15–6:00 | SQL Injection and CSRF



\- Show the SQL Injection testing page and explain the testing objective.

\- Show the CSRF Add Your Blog page.



"These activities were explored, but successful SQL Injection or CSRF exploitation was not confirmed during this exercise."



### 6:00–7:15 | Apache Security Headers



\- Show the Apache security configuration.

\- Show the enabled headers module.

\- Show the configuration validation and Apache service status.

\- If available, show the `curl -I` output verifying the response headers.



"These headers provide additional browser-side protections, including MIME-type sniffing restrictions, framing restrictions, referrer control, and browser feature restrictions."



### 7:15–8:00 | Conclusion



"This task helped me gain practical experience in web application security testing, XSS vulnerability demonstration, HTTP request analysis, automated fuzzing, and Apache security configuration.



I also learned how to document vulnerabilities, understand their impact, and identify appropriate mitigation techniques.



Thank you."

