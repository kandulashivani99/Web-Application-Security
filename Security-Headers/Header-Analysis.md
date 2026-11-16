# HTTP Security Header Analysis



## 1. Objective

To understand HTTP security headers and examine how they improve web application security.



## 2. Tools Used

\- Kali Linux

\- Apache2

\- curl

\- OWASP Mutillidae II



## 3. Headers Configured



| HTTP Header | Security Purpose |

|---|---|

| X-Content-Type-Options | Prevents MIME-type sniffing |

| X-Frame-Options | Helps prevent clickjacking |

| Referrer-Policy | Controls referrer information |

| Permissions-Policy | Restricts browser features |



## 4. Implementation

Apache's mod\_headers module was enabled. The security headers were added to Apache's security configuration file.



## 5. Verification

The Apache configuration was validated using apache2ctl configtest and the server was restarted.



The following command was used to inspect the HTTP response:



`curl -I http://localhost/mutillidae/`



Record the headers actually returned by the server as verification evidence.



## 6. Conclusion

The activity demonstrated how HTTP security headers can be configured at the Apache web server level to add browser-side security protections.

