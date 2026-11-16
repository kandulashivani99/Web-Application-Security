\# Apache Security Header Configuration



\## Objective

To configure HTTP security headers in Apache to improve web application security.



\## Environment

\- Operating System: Kali Linux

\- Web Server: Apache2

\- Practice Application: OWASP Mutillidae II



\## Procedure

1\. Enabled the Apache headers module using `sudo a2enmod headers`.

2\. Opened `/etc/apache2/conf-available/security.conf`.

3\. Added the security header directives.

4\. Validated the configuration using `sudo apache2ctl configtest`.

5\. Restarted Apache using `sudo systemctl restart apache2`.

6\. Used curl to inspect the HTTP response headers.



\## Security Headers Implemented

\- X-Content-Type-Options

\- X-Frame-Options

\- Referrer-Policy

\- Permissions-Policy



\## Conclusion

Apache was configured to return additional HTTP security headers. These settings provide security improvements when appropriately configured and verified.

