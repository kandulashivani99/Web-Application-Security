### Reflected XSS Testing



\*\*Test performed:\*\* JavaScript injection through the Echo Message functionality.



\*\*Payload used:\*\*

```html

<script>alert('XSS Test')</script>

```



\*\*Observed result:\*\* The browser displayed a JavaScript alert containing "XSS Test" after the input was submitted.



\*\*Result:\*\* Reflected Cross-Site Scripting was successfully demonstrated in the local OWASP Mutillidae II application.



\*\*Security impact:\*\* An attacker may execute malicious JavaScript in a victim's browser if untrusted input is reflected without proper output encoding.



\*\*Mitigation:\*\*

\- Apply context-aware output encoding.

\- Validate user input on the server side.

\- Use a restrictive Content Security Policy.

\- Avoid inserting untrusted input into executable HTML or JavaScript contexts.

