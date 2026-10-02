# Task 2 — Exploit a Vulnerable Web Application

## Overview

This task focused on identifying and demonstrating security vulnerabilities within a deliberately vulnerable web application in an authorized laboratory environment.

The assessment was performed against OWASP Juice Shop, an intentionally insecure application designed for security training and practical web application security testing.

## Objective

The objective was to:

* Identify exploitable web application vulnerabilities
* Demonstrate controlled exploitation
* Document the security impact of each vulnerability
* Capture evidence of successful testing
* Provide appropriate security recommendations

## Target

**Application:** OWASP Juice Shop

**Environment:** Controlled cybersecurity laboratory

## Tools Used

* Kali Linux
* Burp Suite
* Web browser
* OWASP Juice Shop
* HTTP requests and browser developer tools

## Vulnerabilities Demonstrated

### 1. SQL Injection — Login Admin

#### Description

SQL Injection occurs when untrusted user input is incorporated into database queries without adequate validation or parameterization.

During testing, the application's authentication functionality was assessed for SQL injection vulnerabilities.

A successful test resulted in access to the administrator account, demonstrating the security impact of insufficiently protected database queries.

#### Impact

Successful SQL injection against an authentication mechanism can allow unauthorized access and potentially expose or manipulate application data.

#### Evidence

Supporting screenshots are available in the `screenshots/` directory.

---

### 2. Cross-Site Scripting (XSS)

#### Description

Cross-Site Scripting occurs when an application processes and renders attacker-controlled input without appropriate output encoding or sanitization.

The application was tested for XSS by supplying controlled input and observing how the application processed the input.

#### Impact

A successful XSS vulnerability can allow malicious scripts to execute in a victim's browser within the security context of the vulnerable application.

Potential consequences include:

* Session compromise
* Unauthorized actions
* Sensitive information exposure
* Manipulation of displayed content

#### Evidence

Supporting screenshots are available in the `screenshots/` directory.

---

### 3. IDOR / Broken Object-Level Authorization

#### Description

Insecure Direct Object Reference (IDOR), also referred to as Broken Object-Level Authorization, occurs when an application exposes references to objects without properly verifying whether the requesting user is authorized to access them.

Testing was performed by examining application requests and modifying object references to determine whether access controls were properly enforced.

#### Impact

If authorization checks are missing or improperly implemented, users may be able to access resources belonging to other users.

#### Evidence

Supporting screenshots and testing evidence are available in the `screenshots/` directory.

---

### 4. Broken Access Control

#### Description

Broken Access Control occurs when an application fails to properly enforce restrictions on what authenticated users are allowed to access or perform.

During testing, a normal user account was used to examine restricted application functionality.

A request to:

`/rest/admin/application-configuration`

returned a successful `200 OK` response and exposed application configuration information.

#### Impact

Improper access-control enforcement can allow lower-privileged users to access functionality or information intended for administrators.

Potential consequences include:

* Unauthorized information disclosure
* Privilege escalation
* Exposure of sensitive application configuration
* Unauthorized administrative actions

#### Evidence

Supporting screenshots are available in the `screenshots/` directory.

---

## Testing Methodology

The assessment followed a controlled workflow:

1. Identify the application's attack surface.
2. Examine authentication and authorization mechanisms.
3. Identify potentially vulnerable input points and application endpoints.
4. Perform controlled security testing.
5. Verify the observed behavior.
6. Capture screenshots as evidence.
7. Document the security impact.
8. Provide recommendations for remediation.

## Security Recommendations

Recommended defensive measures include:

* Use parameterized queries and prepared statements to prevent SQL injection.
* Validate and sanitize user input.
* Apply context-aware output encoding to prevent XSS.
* Implement strict server-side authorization checks.
* Verify object ownership before returning requested resources.
* Apply least-privilege principles.
* Restrict administrative endpoints to authorized roles.
* Avoid exposing sensitive application configuration through publicly accessible endpoints.
* Perform regular security testing and code reviews.

## Evidence

Supporting screenshots from the practical exercises are available in:

`screenshots/`

The complete formal report is available in:

`findings/`

## Conclusion

The assessment demonstrated several common web application security weaknesses, including injection, cross-site scripting, insecure object access, and broken access control.

The practical exercises provided hands-on experience with identifying vulnerabilities, validating their behavior, documenting evidence, and understanding their potential security impact.

## Disclaimer

All testing documented in this repository was performed in a controlled and authorized internship/laboratory environment for educational and cybersecurity training purposes.
