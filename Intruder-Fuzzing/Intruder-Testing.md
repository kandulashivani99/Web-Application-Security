\# Intruder Fuzzing



\## Objective

To understand how Burp Suite Intruder can automate the testing of HTTP request parameters using a predefined list of payloads.



\## Tools

\- Burp Suite Community Edition

\- OWASP Mutillidae II (local practice application)



\## Procedure

1\. Selected a previously captured Mutillidae HTTP request.

2\. Sent the request to Burp Suite Intruder.

3\. Configured the payload position in the username parameter.

4\. Added test payloads.

5\. Executed the Intruder attack.

6\. Compared HTTP status codes, response lengths, and response contents.



\## Observations

The Intruder tool automated the submission of multiple test inputs. The responses were compared to identify differences in server behaviour.



\*\*Actual results:\*\* Record the observed status codes, response lengths, and any meaningful response differences from the Intruder results window.



\## Security Recommendations

\- Validate user input on the server side.

\- Use parameterized SQL queries.

\- Apply rate limiting to authentication endpoints.

\- Implement account lockout or progressive delays where appropriate.

\- Log and monitor repeated failed login attempts.



\## Conclusion

The exercise demonstrated automated HTTP parameter testing with Burp Suite Intruder and the importance of analysing server responses during security testing.

