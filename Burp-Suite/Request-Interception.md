\## 🔍 HTTP Request Interception and Modification



\### Objective

To intercept, inspect, and modify HTTP login requests using Burp Suite Community Edition.



\### Methodology

1\. Configured the Burp Suite built-in browser.

2\. Accessed the local Mutillidae application.

3\. Intercepted a login request through Burp Proxy.

4\. Examined HTTP methods, headers, and form parameters.

5\. Forwarded the request to Burp Repeater.

6\. Modified a test username parameter.

7\. Sent the modified request and analyzed the server response.

8\. Reviewed captured traffic through HTTP History.



\### Observations

The exercise demonstrated how HTTP requests can be inspected and modified before reaching a web application.



\### Security Significance

Applications must validate requests on the server side and enforce proper authentication and authorization controls.



\### Conclusion

Burp Suite provides useful capabilities for analyzing web application traffic and identifying weaknesses in request handling.

